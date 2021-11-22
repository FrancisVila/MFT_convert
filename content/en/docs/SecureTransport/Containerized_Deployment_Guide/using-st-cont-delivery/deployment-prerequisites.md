{
    "title": "Deployment prerequisites",
    "linkTitle": "Deployment prerequisites",
    "weight": "70"
}Before you proceed, carefully review prerequisites for SecureTransport Containerized deployments.

## Download SecureTransport Docker Images

Download the respective Edge and Server image files from [Axway Support Portal](https://support.axway.com/ "Axway Support").

Upload the files to each of the Kubernetes Nodes host machines. Enter the following commands to load the images:



    $ docker load -i SecureTransport_5.5_DockerImage_edge_linux-x86-64_<build number>.tar.gz
    $ docker load -i SecureTransport_5.5_DockerImage_server_linux-x86-64_<build number>.tar.gz

## Licenses

Make sure you have valid SecureTransport license files ready (`filedrive.license` and `st.license`) for the correct external database that you will be using.

> **Note:**
>
> The licenses must not be bound to a specific IP address or hostname.

## Kubernetes requirements

### Kubernetes nodes requirements

In order to prepare your Kubernetes Cluster(s) for deploying SecureTransport Edge/Server containers, there are certain `sysctl` options that must be configured. The `sysctl` options mentioned in this guide are considered "unsafe" by Kubernetes and cannot be applied specifically to each pod via PodSecurityPolicy by default.

Axway recommends the safe approach of setting the `sysctl` options on every Kubernetes node that you want to deploy SecureTransport containers on and use the "Taints and Tolerations" feature of Kubernetes to schedule the SecureTransport pods on specific Kubernetes nodes or just set the above `sysctls` on all Kubernetes nodes in your clusters.

The other approach is to enable "unsafe sysctls" on your Kubernetes cluster nodes, but this option should be used carefully (use-at-your-own-risk).

See the [Kubernetes documentation](https://kubernetes.io/docs/tasks/administer-cluster/sysctl-cluster/) on using `sysctl` cluster for more info.

### Kubernetes DNS resolution

The Kubernetes DNS (Kube-DNS) plays big part of the Edge scaling process as it determines how fast new pods are resolved when querying the StatefulSet's headless service. The Default TTL (time-to-live) of the Kube-DNS is 5 seconds, therefore you must make sure that the TTL is *not* set to a higher value as this will affect the resolution.

You can check the current Kube-DNS TTL by executing the following command several times:



    docker run --rm gcr.io/kubernetes-e2e-test-images/dnsutils:1.3 /bin/sh - c "dig +nocmd +noall +answer +ttlid @10.96.0.10 A <headless service name>.<namespace>.svc.cluster.local"
    nz1-svc.securetransport.svc.cluster.local. 5 IN A 10.32.0.35
    nz1-svc.securetransport.svc.cluster.local. 5 IN A 10.40.0.15
    nz1-svc.securetransport.svc.cluster.local. 5 IN A 10.43.0.12

> **Note:**
>
> The TTL is the value displayed after the headless service name: '5' as in the example above.

## Docker Engine requirements

### Set Default Container Memory and Open Files limits

As the SecureTransport processes inside the container run as a non-root user, it is important to make sure that the limits for "Max Open Files" and "Max User Processes" are both set to at least 65536. See the <a href="https://docs.axway.com/bundle/SecureTransport_55_InstallationGuide_allOS_en_HTML5/page/Content/InstallationGuide/prereqs/Prerequisites_for_non_root_installations.htm" class="MCXref xref">Prerequisites for non-root installations</a> in the *SecureTransport {{< SecureTransport/releasenumber  >}}. Installation guide* for more information.

In a containerized environment these limits are best configured globally, for all containers, in the Docker Engine configuration file (by default `/etc/docker/daemon.json`).

Before making any changes, verify the current values by executing the following command:



    $ docker run --rm --entrypoint '' <st_server_or_edge_image_tag>  /bin/bash -c 'ulimit -n -u'
    open files (-n) 65536
    max user processes (-u) 65536

If needed update the `/etc/docker/daemon.json` file and restart the Docker Engine on each of the Kubernetes cluster nodes.



    {
      "default-ulimits": {
      "nofile": {
        "Name": "nofile",
        "Hard": 65536,
        "Soft": 65536
        },
      "nproc": {
        "Name": "nproc",
        "Hard": 65536,
        "Soft": 65536
      }
    },....
    }

### Increase the maximum number of file descriptors

SecureTransport requires more than the default number of file descriptors. Add the following line to the `/etc/sysctl.conf` (or `/etc/sysctl.d/99-sysctl.conf`) file on each Kubernetes Node:



    fs.file-max = 65536

Then run the following command to immediately apply the settings:



    $ sysctl -p

### Configure larger socket buffers

For Enterprise Clustering, SecureTransport Server requires larger socket buffers than the default. Add the following lines to the `/etc/sysctl.conf` (or `/etc/sysctl.d/99-sysctl.conf`) file on each Kubernetes Node:



    net.core.rmem_max=2096304
    net.core.wmem_max=2096304
    net.ipv4.tcp_moderate_rcvbuf=1

Then run the following command to immediately apply the settings:



    $ sysctl -p

### Synchronize the time

Make sure the time is synchronized across all Kubernetes nodes (ideally using NTP service). Big time differences may affect the forming of the Enterprise Cluster, as well as produce misaligned log entries in the Server Log (for Enterprise Cluster nodes).

<span id="SecretFile"></span>

## Secret file

The secret file (also called *taeh* file) contains randomly-generated data used by the SecureTransport system for encryption.

In a classic {{< SecureTransport/componentshortname  >}} deployment, the secret file is generated during installation and must be copied between servers before installing additional cluster nodes. When deploying the containerized version of {{< SecureTransport/componentshortname  >}} there is no formal "installation process" as the docker image is already built that's why the secret file must be generated upfront and supplied during deployment.

In order to generate a secret file, you need to use a command that is embedded in the {{< SecureTransport/componentshortname  >}} Docker images.



    $ mkdir /tmp/secret_folder
    $ chmod 770 /tmp/secret_folder
    $ touch /tmp/secret_folder/pass - Insert the database password in the file
    $ docker run --rm --entrypoint '' -v /tmp/secret_folder/:/tmp/secret_folder <st-image> /bin/bash -c '$ST_HOME/bin/createTaehFile /tmp/secret_folder ; cp /tmp/secret_folder/taeh $ST_HOME/bin/taeh ; $ST_HOME/bin/utils/aesenc "$(< /tmp/secret_folder/pass)" > /tmp/secret_folder/encpass' ; rm -f /tmp/secret_folder/pass
    $ ls -l /tmp/secret_folder/
    total 8
    -rw-r--r-- 1 1001 root   33 May 12 15:10 encpass
    -rw------- 1 1001 root 1024 May 12 15:10 taeh

This must be executed both for SecureTransport Servers and Edges using their respective images.

After running the above command, the secret file and the encrypted database password used later in `db.conf`, will be available in the `/tmp/secret_folder/` location for later use.

The generated `taeh` file is passed on startup of the container. The file must be present in the mounted directory in `ST_CONTAINER_CONFIG_PATH` defined in the Kubernetes configuration files.

> **Note:**
>
> After you deploy a SecureTransport StatefulSet with a given taeh file, it cannot be changed later. Attempts to change the secret file corrupt certain encrypted configuration elements (local certificates, passwords, etc.).

<span id="ExternalDB"></span>

## External Database Requirements

The requirements for the External Oracle/MSSQL/PostgreSQL databases are the same as mentioned in the <a href="https://docs.axway.com/bundle/SecureTransport_55_InstallationGuide_allOS_en_HTML5/page/Content/InstallationGuide/prereqs/Database_installation_prerequisites.htm" class="MCXref xref">Database requirements</a> in the *SecureTransport 5.5 Installation guide* with some database-specific exceptions.

### Requirements for Oracle Databases

When installing the non-containerized version of SecureTransport Server the user has the option to disable the usage of the "Data Pump" feature by setting an environment variable. The containerized version of SecureTransport does not have that option and the usage of Data Pump is always enabled.

### Requirements for MariaDB Databases

SecureTransport Edges requires an external MariaDB database in order to store the shared configuration. In order to set up the database, the following must be created - database and user with the correct permissions to manage the database.

-   Create your MariaDB database
-   Create your database user
-   Create your database user password
-   Grant all privileges to the database user
-   Configure your database encoding: UTF-8
-   Configure max connections according to the formula: `(edgeCount * 300)`

For fine tuning, use the following [example configuration](https://github.com/Axway/docker-st/blob/master/edge/example-configuration/MySQL/my.cnf) on the SecureTransport GitHub repo to apply to the MariaDB database in `my.cnf` file.

<span id="dbConfig"></span>

## Prepare database configuration file (db.conf)

The "installation procedures" for classic and containerized SecureTransport deployments are very different in their nature:

-   Hardware/Virtual SecureTransport installation
    -   The installation procedure involves downloading a package that, once unzipped, contains an installer that guides you throughout the process
    -   The SecureTransport installer performs two main tasks - installs the SecureTransport Binaries and initializes the embedded (Edge) or external (Server) database
-   Containerized SecureTransport "installation"
    -   Instead of downloading an "installation package", you download a Docker Image(s)
    -   The Docker Image already contains the SecureTransport binaries (Edge/Server)
    -   The external database initialization is performed during the container startup (only if the database has not been initialized yet). This is why the external database configuration must be supplied to the container when it is deployed.

The external database configuration must be supplied to the container in a file (called `db.conf`). This file follows strict format and must be prepared before deploying the container (more on that in the Initial deployment section). The database password must be encrypted using the secret file, as explained in section <a href="#SecretFile" class="MCXref xref">Secret file</a>.

#### External database sample configuration files

*Plain connection*



    db.type= < Database Type: oracle, mssql, postgresql or internaldb >
    db.host= < The FQDN or IP address of the Database system or cluster >
    db.port= < The number of the port used to access the server or cluster >
    db.user= < The name of the user authorized to create the SecureTransport schema and populate it >
    db.password= < The password for the user >
    db.name= < Service Name (Oracle) or Database Name (MSSQL/PostgreSQL/MariaDB) >
    db.use.secure.connection=false < Whether to use secure connection or not; the default if not specified is 'false' >

*Secure connection*



    db.type= < Database Type: oracle, mssql, postgresql or internaldb >
    db.host= < The FQDN or IP address of the Database system or cluster >
    db.port= < The number of the port used to access the server or cluster >
    db.user= < The name of the user authorized to create the SecureTransport schema and populate it >
    db.password= < The password for the user >
    db.name= < Service Name (Oracle) or Database Name (MSSQL/PostgreSQL/MariaDB) >
    db.use.secure.connection=true < Whether to use secure connection or not; when not specified, it is 'false' by default >
    db.certificate.name= < Server certificate DN value. If provided, the value will be matched against the certificate provided by the database server: for Oracle - DN of the certificate; for MSSQL - Server name; for MariaDB - Certificate name; Not applicable for PostgreSQL >
    db.certificate.filename= < PEM or DER file, containing the trusted certificates needed to establish a chain of trust >
    db.oracle.tls.version= < Specifies the TLS version used during the connection. Possible values: 1(default) and 1.2. Required only with Oracle databases. >

## Container resource configuration guidelines

The minimum requirements for {{< SecureTransport/componentshortname  >}} running in container are: 4 CPUs and 8 GB of RAM. Depending on the services that run in the containers and their configuration, this requirement may vary.

It is recommended to have one service running in a pod for more accurate scaling of the StatefulSets.

For example:

-   On SecureTransport Servers only Transaction manager service. Note that the Admin service is mandatory.
-   On SecureTransport edges one of the protocol daemons. Note that Admin and SOCKS services are mandatory.

<span id="StartScript"></span>

### Startup scripts configuration options

When deploying an application as a container, it is important to align the resource limits of the application with the resources that are configured on the container runtime level. For example, if the application is allowed to use more memory than the limits set in the Kubernetes manifest files, the Docker engine will kill the container as soon as the application usage exceeds them.

In order to control the resource usage on application level, SecureTransport uses a file called `STStartScriptsConfig` that allows specifying the minimum and maximum JAVA Memory limits or add Java arguments for each SecureTransport Service.

Path to the file containing start scripts properties is configured using the `ST_START_SCRIPTS_CONF_PATH` operating system environment variable and should be mounted as Kubernetes secret in the location as declared in the Kubernetes configuration files (for example: `/tmp/STStartScriptsConfig`).

Unless specified via the corresponding system properties, the number of established streaming connections from Transaction Manager to a single protocol daemon (Admin, FTP, HTTP, etc.) is calculated by the formula: `min(20, 2*CPUs)`.

If you have 4 CPUs, by default 8 streaming connections will be opened per protocol. If you have 12 CPUs, then 20 streaming connections will be opened (the max number of connections). You can explicitly set them to a selected integer value `'X'` by placing the following line in `STStartScriptsConfig` file:

`-TM_JAVA_OPTS="${TM_JAVA_OPTS} -DStreaming.numberOfConnections=X"`

`STStartScriptsConfig` *example*



    # Start scripts configuration should be specified here in the following format:
    # PROTOCOL_NAME]_[OPTION_NAME]=[value]
    # SSH_JAVA_MEM_MIN=256M
    # SSH_JAVA_OPTS="${SSH_JAVA_OPTS} -Dcom.sun.management.jmxremote.port=2997
    -Dcom.sun.management.jmxremote.authenticate=false -
    Dcom.sun.management.jmxremote.ssl=false"
    TM_JAVA_MEM_MIN=512M
    TM_JAVA_MEM_MAX=512M
    TM_JAVA_OPTS="${TM_JAVA_OPTS} -DStreaming.numberOfConnections=10"
    ADMIN_JAVA_MEM_MIN=512M
    ADMIN_JAVA_MEM_MAX=512M

> **Note:**
>
> You can add different shell script commands to the start script. Act with caution as your input will be executed each time the start script runs.

#### Transaction Manager Specifics

Additionally, few more options, available in the `start_tm_console` are configurable through the `STStartScriptsConfig` file. The following sample script shows these options with example values:



    disableHeapDumpOnOutOfMemoryError=true
    generate_heap_dump=true
    GC_LOGGING=true
    NumberOfGCLogFiles=30
    GCLogFileSize=5000K

<span id="PerfTuning"></span>

## Performance tuning

Using configuration files, performance tuning can be applied to the following files: `configuration.xml` options, `hibernate-cache-config.xml`, `scheduler.properties`, `coherence-cache-config-tm.xml`

Configuring the Min/Max memory that a given service can allocate is a mandatory step to ensure that the containers will even start. More fine grained performance tuning is available using additional configuration files.

The process is summarized in the following steps:

1.  Get the default files
2.  Modify them
3.  Create a Kubernetes secret that contains the modified files
4.  Update the Kubernetes manifests file to mount the files from the secret

> **Note:**
>
> On SecureTransport Edges, only the configuration.xml options can be applied. As no other tuning of the configuration files is required.

Before modifying the files you must obtain them from the Docker image using the following command (applicable for SecureTransport Servers only)



    $ mkdir /tmp/secret_folder
    $ chmod 777 /tmp/secret_folder
    $ docker run --rm --entrypoint '' -v /tmp/secret_folder/:/tmp/secret_folder <st-server-image> /bin/bash -c 'cp $ST_HOME/conf/hibernate-cache-config.xml /tmp/secret_folder ; 
    cp $ST_HOME/conf/scheduler.properties /tmp/secret_folder ; 
    cp $ST_HOME/conf/coherence-cache-config-tm.xml /tmp/secret_folder'

The `hibernate-cache-config.xml`, `scheduler.properties`, `coherence-cache-config-tm.xml` are replaced on container start overwriting the default files, if they are present in the `**ST_CONTAINER_CONFIG_PATH**` mounted secret volume.

In order to perform changes to the `configuration.xml` options, a file named `database_configuration_components.xml` must be present in the `**ST_CONTAINER_CONFIG_PATH**`. The `configuration.xml` file is generated during container startup, therefore it cannot be replaced. After the file is created and populated with the information present in `db.conf`, its options are modified per component as specified in the supplied `database_configuration_components.xml`.

The options in `database_configuration_components.xm` are supplied in key-value pairs. If an option does not exist yet, it will be added to the list of options of the specified component. If already present, its value will be changed. The file is in the following format:

`database_configuration_components.xml` *example*



    <Components>
      <Component name="TransactionManager">
        <Option name="hibernate.c3p0.max_size" value="32" />
        <Option name="hibernate.c3p0.min_size" value="5" />
      </Component>
      <Component name="HTTPD">
        <Option name="hibernate.show_sql" value="false" />
      </Component>
    </Components>

Valid components are: `"Database", "Admin", "AS2", "SSHD", "FTPD", "HTTPD", "Tools", "Installer", "Pesit", "TransactionManager", "TransferLog", "ServerLog"`.

*next topic:* <a href="../initial-deployment" class="MCXref xref">Initial deployment</a>
