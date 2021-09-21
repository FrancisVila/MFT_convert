{
    "title": "Advanced protocol server configuration",
    "linkTitle": "Advanced protocol server configuration",
    "weight": "160"
}SecureTransport 5.5 and later allows you to configure protocol servers using configuration files. The underlying concept is to supply unified daemon configuration by adding a dedicated start scripts configuration per server daemon.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The start scripts configuration overrides any other configuration.         </td>
      </tr>
</table>

## Add start scripts global configuration

The *start scripts configuration* will be placed in `STStartScriptsConfig` which is located in `FILEDRIVEHOME/conf` by default. Path to the file containing start scripts properties will be configured with the operating system environment variable `ST_START_SCRIPTS_CONF_PATH` (e.g `/tmp/STStartScriptsConfig`).

Server start script example:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
<p xml:space="preserve"># Start scripts configuration should be specified here in the following format:
</p>
<p xml:space="preserve"># [PROTOCOL_NAME]_[OPTION_NAME]=[value]
</p>
<p xml:space="preserve"># SSH_JAVA_MEM_MIN=256M
</p>
<p xml:space="preserve"># SSH_JAVA_OPTS="${SSH_JAVA_OPTS} -Dcom.sun.management.jmxremote.port=2997 
</p>
<p xml:space="preserve">-Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false"
</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can add different shell script commands to the start script. Act with caution as your input will be executed each time the start script runs.         </td>
      </tr>
</table>

### Transaction Manager Specifics

Additionally, few more options, available in the `start_tm_console` are configurable through the `STStartScriptsConfig` file.

The following sample script shows these options with example values:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
<p xml:space="preserve">disableHeapDumpOnOutOfMemoryError=true</p>
<p xml:space="preserve">generate_heap_dump=true</p>
<p xml:space="preserve">GC_LOGGING=true</p>
<p xml:space="preserve">NumberOfGCLogFiles=30</p>
<p xml:space="preserve">GCLogFileSize=5000K</p>
         </td>
      </tr>
   </tbody>
</table>

## Import Certificates

User will be able to use the default certificate (admind) or to import one certificate and use it for daemon configuration. Certificate will be imported on admin startup.

Operating system environment variables needed for certificate import:

-   `ST_CA_PATH` - Path to the Certificate Authority
-   `ST_CA_ALIAS` - Certificate Authority alias
-   `ST_CERT_PATH` - Local certificate path
-   `ST_CERT_PASS` - Password for the local certificate
-   `ST_CERT_ALIAS` - Local certificate alias
