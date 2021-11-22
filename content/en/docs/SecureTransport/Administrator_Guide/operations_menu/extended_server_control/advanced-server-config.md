{
    "title": "Advanced protocol server configuration",
    "linkTitle": "Advanced protocol server configuration",
    "weight": "150"
}{{< SecureTransport/componentshortname  >}} 5.5 and later allows you to configure protocol servers using configuration files. The underlying concept is to supply unified daemon configuration by adding a dedicated start scripts configuration per server daemon.

> **Note:**
>
> The start scripts configuration overrides any other configuration.

## Add start scripts global configuration

The *start scripts configuration* will be placed in `STStartScriptsConfig` which is located in `FILEDRIVEHOME/conf` by default. Path to the file containing start scripts properties will be configured with the operating system environment variable `ST_START_SCRIPTS_CONF_PATH` (e.g `/tmp/STStartScriptsConfig`).

Server start script example:



    # Start scripts configuration should be specified here in the following format:

    # [PROTOCOL_NAME]_[OPTION_NAME]=[value]

    # SSH_JAVA_MEM_MIN=256M

    # SSH_JAVA_OPTS="${SSH_JAVA_OPTS} -Dcom.sun.management.jmxremote.port=2997 

    -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false"

> **Note:**
>
> You can add different shell script commands to the start script. Act with caution as your input will be executed each time the start script runs.

### Transaction Manager Specifics

Additionally, few more options, available in the `start_tm_console` are configurable through the `STStartScriptsConfig` file.

The following sample script shows these options with example values:



    disableHeapDumpOnOutOfMemoryError=true
    generate_heap_dump=true
    GC_LOGGING=true
    NumberOfGCLogFiles=30
    GCLogFileSize=5000K

## Import Certificates

User will be able to use the default certificate (admind) or to import one certificate and use it for daemon configuration. Certificate will be imported on admin startup.

Operating system environment variables needed for certificate import:

-   `ST_CA_PATH` - Path to the Certificate Authority
-   `ST_CA_ALIAS` - Certificate Authority alias
-   `ST_CERT_PATH` - Local certificate path
-   `ST_CERT_PASS` - Password for the local certificate
-   `ST_CERT_ALIAS` - Local certificate alias
