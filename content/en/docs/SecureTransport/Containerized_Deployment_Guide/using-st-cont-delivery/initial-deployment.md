{
    "title": "Initial deployment",
    "linkTitle": "Initial deployment",
    "weight": "80"
}The following section highlights the steps that must be performed to configure and run SecureTransport Servers and Edges in Kubernetes. The outline of these steps is as follows:

1.  Deploy the Edge
2.  Deploy the Server
3.  Set up Streaming  
4.  Create a user and login to validate the streaming setup

## Deploying SecureTransport Edge

1.  Complete the relevant tasks as described in section <a href="../deployment-prerequisites" class="MCXref xref">Deployment prerequisites</a>.
2.  Obtain the example configuration by cloning the <a href="https://github.com/Axway/docker-st" class="MCXref xref">SecureTransport GitHub Repo</a>.
3.  Prepare the external database as described in <a href="../deployment-prerequisites#ExternalDB" class="MCXref xref">External Database Requirements</a>.
4.  Configure the load balancer:  
    1.  Create Kubernetes namespace using the following command: `kubectl create namespace <namespace>`
    2.  Configuring the client connections load balancer:
        1.  Modify the `haproxy.cfg` located in `/edge/example-configuration/HaProxy/client/haproxy.cfg`. Set the `<Headless service FQDN of ST server>` to the headless service FQDN of the SecureTransport Edge for all the services that will be used, others must be removed. If FTP is configured, please see secton <a href="../initial-config#ftpPassive" class="MCXref xref">FTP Passive Mode</a>.  
            Example: `st-edge.<namespace>.svc.cluster.local`
        2.  Modify the `haproxy.yaml` file located in `/edge/example-configuration/HaProxy/client/haproxy.yaml`. Set the `<namespace>` to the namespace created in step 4.a. Set ports for nodePort parameters for the services that will be used, others must be removed.
    3.  Configuring the streaming connections load balancer:
        1.  Modify the `haproxy.cfg` located in `/edge/example-configuration/HaProxy/streaming/haproxy.cfg`. Set the `<Headless service FQDN of ST edge>` to the headless service FQDN of the SecureTransport Edge for all the services that will be used, others must be removed.  
            Example: `st-edge.<namespace>.svc.cluster.local`
        2.  Modify the `haproxy.yaml` located in `/edge/example-configuration/HaProxy/streaming/haproxy.yaml`. Set the `<namespace>` to the namespace created in step 4.a. Set ports for nodePort parameters for the services that will be used, others must be removed.  
    4.  Create secrets containing the haproxy.cfg file for both HAProxies:
        1.  Navigate to `/edge/example-configuration/HaProxy/client/` and execute the following command:  
            `kubectl create secret generic haproxy-client-secret -n <st-namespace> --from-file=./haproxy.cfg`
        2.  Navigate to` /edge/example-configuration/HaProxy/streaming/` and execute the following command:  
            `kubectl create secret generic haproxy-streaming-secret -n <st-namespace> --from-file=./haproxy.cfg`
    5.  The external HaProxy must be set up in order to preserve the client IP address and benefit from correct load distribution while using the sticky sessions. If a HAProxy is not set up outside of the Kubernetes cluster the client connections will not be distributed across the nodes and will only be redirected to the first SecureTransport Edge. To achieve this, the external HAProxy must be forwarding the traffic to the Kubernetes internal load balancer using the proxy protocol and preserve the client IP. Otherwise the client IP is not visible to the proxy due to the Kubernetes NodePort service. 
        1.  Install HAProxy on any Linux machine outside the Kubernetes cluster. It can also be ran in Docker.
        2.  Modify the `haproxy.cfg` located in `/edge/example-configuration/HaProxy/onPremises/haproxy.cfg` - Set the `<Kubernetes-IP>:<NodePort>` in "server" configuration to the Kubernetes nodes IP/FQDNs and NodePort port for the services that you want to use, others must be removed. Set the `<PORT>` in "bind" configuration to the port which will be visible externally for the services.  
            **Note** It is important to have the `send-proxy` option appended to all "server" configurations. In the internal client load balancer the "bind" configuration must have the `accept-proxy` option. This way the proxy protocol will be used to preserve the client IP address.  
        3.  Place the `haproxy.cfg` file in `/etc/haproxy`  
              
    6.  Deploy the HAProxy servers:
        1.  Navigate to `/edge/example-configuration/HaProxy/client` and execute the following command: `kubectl create -f haproxy.yaml`
        2.  Navigate to `/edge/example/configuration/HaProxy/streaming` and execute the following command: `kubectl create -f hapyoxy.yaml`
        3.  On the Linux machine where HaProxy was setup execute the following command `systemctl start haproxy`. It can also be deployed in docker using the following command:  
            `docker run --rm -d -v <folder-containing-haproxy.cfg>:/usr/local/etc/haproxy/ -p <port>:<port> haproxy`
5.  Prepare the configuration files for SecureTransport Edge:  
    1.  Create the secret file and encrypted password for the database (see <a href="../deployment-prerequisites#SecretFile" class="MCXref xref">Secret file</a>).
    2.  Upload a copy of the `taeh` file a dedicated location, e.g. `edge/runtime/secrets`.
    3.  Prepare `db.conf` file using the encrypted database password from step 3. and all the database info (see <a href="../deployment-prerequisites#dbConfig" class="MCXref xref">Prepare database configuration file (db.conf)</a>) and upload it to a dedicated location, e.g. `/edge/runtime/secrets/`
    4.  *Optional step:* - prepare `STStartScriptsConfig` file (see <a href="../deployment-prerequisites#StartScript" class="MCXref xref">Startup scripts configuration options</a>) and upload it a dedicated location, e.g. `/edge/runtime/secrets/`.
    5.  Prepare SecureTransport feature and core licenses as per your database and put them respectively in `st.license` and `filedrive.license` files and upload them a dedicated location, e.g. `/edge/runtime/secrets/`
    6.  Create Kubernetes secret with the needed files using the command:  
        `kubectl create secret generic st-edge-secret -n <st-namespace> --from-file=./taeh --from-file=./db.conf --from-file=./st.license --from-file=filedrive.license`  
        **Note** If SSL connection to the database is used the, certificate file should be supplied in the Kubernetes secret. Add at the end of the command: `--from-file=./<certificate>`  
        **Note** If you are using the start script in the Kubernetes secret as prepared in the optional step, then add at the end of the command: `--from-file=./STStartScriptsConfig`  
        If performance tuning is applied, the following files should be also added to the command: `--from-file=./database_configuration_components.xml`
    7.  Modify the `st-edge-kubernetes.yml` located in `/edge/example-configuration/Kubernetes/`:
        1.  Replace every occurrence of `<namespace>` with the namespace created in 4.a.
        2.  Set a port for the SOCKS proxy NodePort service. If not used remove the service.
        3.  Set the image to `securetransport-edge:<tag>`
        4.  Remove the `ST_START_SCRIPTS_CONF_PATH` environment variable description if `STStartScriptsConfig` is not used.
        5.  Comment the Liveness and Readiness probes by placing `#` in front of each respective line.
    8.  Deploy the SecureTransport edge: `kubectl create -f st-edge-kubernetes.yml` (from the folder where the `st-edge-kubernetes.yml` file is located)
    9.  Verify container is started: `kubectl get pods -n <st-namespace>`
6.  After finishing all the configuration remove the comments from the Liveness and readiness checks and apply the changes to the StatefulSet: `kubectl apply -f st-edge-kubernetes.yml`

## Deploying SecureTransport Server

1.  Complete the relevant tasks as described in section <a href="../deployment-prerequisites" class="MCXref xref">Deployment prerequisites</a>.
2.  Obtain the example configuration by cloning the [SecureTransport GitHub Repo](https://github.com/Axway/docker-st).
3.  Prepare the <a href="../deployment-prerequisites#ExternalDB" class="MCXref xref">External Database Requirements</a>.
4.  Configure the load balancer for Administration Tool and client connections to protocol daemons, if any.
    1.  Create Kubernetes namespace using the following command `kubectl create namespace <namespace>`.
    2.  Configuring the client connections load balancer:
        1.  Modify the `haproxy.cfg` located in `/server/example-configuration/HaProxy/haproxy.cfg`. Set the `<Headless service FQDN of ST server>` to the headless service FQDN of the SecureTransport server for all the services that will be used, others must be removed. If FTP is configured please see the <a href="../initial-config#ftpPassive" class="MCXref xref">FTP Passive Mode</a> section.  
            Example: `st-server.<namespace>.svc.cluster.local`
        2.  Modify the `haproxy.yaml` located in `/server/example-configuration/HaProxy/haproxy.yaml`. Set the `<namespace>` to the namespace created in step 4.a. Set ports for nodePort parameters for the services that will be used, others must be removed.
    3.  Create secret containing the `haproxy.cfg` file for HAProxy:
        1.  Navigate to `/server/example-configuration/HaProxy/` and execute the following command:  
            `kubectl create secret generic haproxy-secret -n <st-namespace> --from-file=./haproxy.cfg`
    4.  Perform steps 4.d.i - 4.d.iii only if any daemons will be set up on the SecureTransport Servers. External load balancer is not needed for the Administration tool, only sticky sessions. Since all the configuration is shared it does not matter which Administration tool is accessed. If daemons are running on the SecureTransport servers an external HAProxy must be set up to preserve the client IP address and benefit from correct load distribution while using the sticky sessions. If a HAProxy is not set up outside of the Kubernetes cluster, the client connections will not be distributed across the nodes and will only be redirected to the first SecureTransport Server. To achieve this, the external HAProxy must be forwarding the traffic to the Kubernetes internal load balancer using the proxy protocol and preserve the client IP. Otherwise the client IP is not visible to the proxy due to the Kubernetes NodePort service.
        1.  Install HAProxy on any Linux machine outside the Kubernetes cluster. You can also run it in Docker.
        2.  Modify the `haproxy.cfg` located in `/edge/example-configuration/HaProxy/onPremises/haproxy.cfg` - Set the `<Kubernetes-IP>:<NodePort>` in "server" configuration to the Kubernetes nodes IP/FQDNs and NodePort port for the services that you want to use, others must be removed. Set the `<PORT>` in "bind" configuration to the port which will be visible externally for the services.  
            **Note** It is important to have the `"send-proxy"` option appended to all "server" configurations. In the internal client load balancer the "bind" configuration must have the `"accept-proxy"` option. This way the proxy protocol will be used to preserve the client IP address.  
        3.  Place the `haproxy.cfg` file in `/etc/haproxy`  
              
    5.  Deploy the HAProxy servers:
        1.  Navigate to `/server/example-configuration/HaProxy/` and execute the following command: `kubectl create -f haproxy.yaml`
        2.  On the Linux machine where HaProxy was setup execute the following command `systemctl` start haproxy. It can also be deployed in docker using the following command:  
            `docker run --rm -d -v <folder-containing-haproxy.cfg>:/usr/local/etc/haproxy/ -p <port>:<port> haproxy`.
5.  Prepare the configuration files for SecureTransport Server:  
    1.  Create the secret file and encrypted password for the database (see section <a href="../deployment-prerequisites#SecretFile" class="MCXref xref">Secret file</a>)
    2.  Upload a copy of the `taeh` file in a dedicated location, e.g. `/server/runtime/secrets`
    3.  Prepare `db.conf` file using the encrypted database password from step 3.a and all the database info (see <a href="../deployment-prerequisites#dbConfig" class="MCXref xref">Prepare database configuration file (db.conf)</a>) and upload it to a dedicated location, e.g. `/server/runtime/secrets/`
    4.  *Optional step:* Prepare the `STStartScriptsConfig` file (see <a href="../deployment-prerequisites#StartScript" class="MCXref xref">Startup scripts configuration options</a>) and upload it to a dedicated location, e.g. `/server/runtime/secrets`
    5.  Prepare SecureTransport feature and core licenses as per your database and put them respectively in the `st.license` and `filedrive.license` files and upload them to a dedicated location, e.g. `/server/runtime/secrets`
    6.  Create Kubernetes secret with the needed files:  
        `kubectl create secret generic st-server-secret -n <st-namespace> --from-file=./taeh --from-file=./db.conf --from-file=./st.license --from-file=filedrive.license`  
        Note that the command should be executed where the files are located (e.g. `runtime/secrets`)  
        If SSL connection to the database is used, the certificate file should be supplied in the Kubernetes secret and add at the end of the command: `--from-file=./<certificate>`  
        **Note** If you are using the start script in the Kubernetes secret as prepared in the optional step, then add at the end of the command: `--from-file=./STStartScriptsConfig`  
        **Note** If performance tuning is applied, the above mentioned files should be also added to the command `(--from-file=./database_configuration_components.xml --from-file=./hibernate-cache-config.xml --from-file=./scheduler.properties --from-file=./coherence-cache-config-tm.xml)`. See <a href="../deployment-prerequisites#PerfTuning" class="MCXref xref">Performance tuning</a>.
    7.  Modify the `st-server-kubernetes.yml` located in `/server/example-configuration/Kubernetes/`:
        1.  Replace all occurances of `<namespace>` with the namespace created in 2.b.
        2.  Set the image to `securetransport-server:<tag>`
        3.  In the volumes section add the IP and shared folder for the persistent storage.
        4.  Remove the `ST_START_SCRIPTS_CONF_PATH` environment variable description if `STStartScriptsConfig` is not used.
        5.  Comment the Liveness and Readiness probes by placing `#` in front of each respective line.
    8.  Deploy the SecureTransport server - `kubectl create -f st-server-kubernetes.yml` (from the folder where `st-server-kubernetes.yml` file is located)
    9.  Verify that the container is started - `kubectl get pods -n <st-namespace>`.
    10. After successful start of the SecureTransport Server, log in to the Administration Tool and configure the streaming network zone for all enabled protocols pointing to the SecureTransport Edge load balancer IP/FQDN. For more information on setting up a network zone, see the <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/c_st_networkZones.htm" class="MCXref xref">SecureTransport <span class="mc-variable axway_variables.Component_Version variable">5.5</span> Administrator guide</a>.
6.  After finishing all the configuration remove the comments from the Liveness and readiness checks and apply the changes to the `StatefulSet - kubectl apply -f st-server-kubernetes.yml`.

## Kubernetes readiness and liveness checks

Liveness and readiness checks are implemented for monitoring the status and health of the SecureTransport services in Kubernetes. The scripts are executed by Kubernetes on configurable schedule setup in `st-server-kubernetes.yml` and `st-edge-kubernetes.yml`.

    Readiness probe example



    readinessProbe:
    exec:
    command:
    - /home/stuser/Axway/SecureTransport/bin/readiness_check.sh
    initialDelaySeconds: 10
    periodSeconds: 20

 

    Liveness probe example



    livenessProbe:
    exec:
    command:
    - /home/stuser/Axway/SecureTransport/bin/liveness_check.sh
    initialDelaySeconds: 300
    failureThreshold: 1
    periodSeconds: 15

> **Note:**
>
> The Kubernetes manifest padding format must be followed with both Readiness and Liveness checks.

The container is considered ready when:

-   For SecureTransport Servers, the container is considered ready when the admin service is started. The readiness check must be configured on small interval as issues forming an cluster can be experienced.
-   For SecureTransport Edges, the container is considered ready when all enabled services have started their streaming server.

Container is considered healthy/live when:

-   The container is considered live when all the enabled services have streaming connections established with the SecureTransport server. If any of the enabled services has no streaming connections or the Transaction Manager of SecureTransport servers is not running the pod is considered unhealthy and it is restarted.

> **Note:**
>
> In order to perform the initial configuration and configure streaming, the liveness check should be commented (# before every line), so that the containers are not restarted.

> **Note:**
>
> On SecureTransport Edges, it is mandatory to have admin daemon streaming established and SOCKS proxy running.

## Graceful shutdown of SecureTransport services

Graceful shutdown of protocol daemons is supported for SecureTransport Edges, when scaling down or stopping a container. All the currently running transfers will be finished before the Edge container is terminated and no new connections will be accepted by the Edge pod. To configure the timeout before the container is killed forcefully, the following options can be set in the Kubernetes configuration file for SecureTransport Edges `terminationGracePeriodSeconds: X` (seconds): it is recommended that this setting exceeds the configured values for protocol daemons shutdown. After this timeout is reached, the container is stopped forcefully interrupting all the existing connections.

> **Note:**
>
> The graceful shutdown of protocol daemons is not supported for SecureTransport servers.

> **Note:**
>
> During the graceful shutdown of Edge container, the number of containers cannot be increased until the current terminating pod is stopped.

*next topic:* <a href="../initial-config" class="MCXref xref">Configure the deployment</a>
