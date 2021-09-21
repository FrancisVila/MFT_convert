{
    "title": "Run SecureTransport as a service on UNIX-based platforms after non-root installation",
    "linkTitle": "Run SecureTransport as a service on UNIX-based platforms after non-root installation",
    "weight": "120"
}During a non-root SecureTransport installation, the installer cannot set up and configure SecureTransport to run out of `systemctl`. To allow the services to start during system boot, service files and a target file must be created in the appropriate location, and all files must be linked appropriately. This topic describes the process to configure SecureTransport services to start automatically during system boot.

1.  Log on as root.

2.  Create a service unit file for each SecureTransport service following the [Service Unit File Example](#service).
    Service units must be located in the `<FILEDRIVEHOME>/bin/utils/` directory.  
    
    1.  Create `securetransport_db.service`
    2.  Create `securetransport_admin.service`
    3.  Create `securetransport_as2d.service`
    4.  Create `securetransport_ftpd.service`
    5.  Create `securetransport_httpd.service`
    6.  Create `securetransport_pesitd.service`
    7.  Create `securetransport_sshd.service`
    8.  Create `securetransport_tm.service`

3.  In the same directory, create a target unit file `(securetransport.target`) for all SecureTransport services following the [Target Unit File Example](#target).

4.  Move or copy the service files and the target file to the `/etc/systemd/system` directory.

5.  In `/etc/systemd/system`, change the permissions of the  
    `securetransport_*.service` files and the `securetransport.target` file to “`644`”.

6.  Enable the service units (`securetransport_*.service`) by running the following command:
      
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p># systemctl enable &lt;service_name&gt; </p>
         </td>
      </tr>
   </tbody>
</table>

7.  Enable `securetransport.target` to create the required links and set the SecureTransport services to start on boot.
      
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p># systemctl enable securetransport.target</p>
         </td>
      </tr>
   </tbody>
</table>

8.  Reload the `systemctl` daemon by running the following command:
      
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p># systemctl daemon-reload</p>
         </td>
      </tr>
   </tbody>
</table>

9.  Reboot the system and verify that the SecureTransport services start as expected.

### <span id="Service"></span>Service Unit File Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>[Unit]</p>
            <p>Description=SecureTransport service unit</p>
            <p># If this is an Enterprise Cluster core server, or  the  </p>
            <p># securetransport_db service file, remove the lines Requires= and After=</p>
            <p>Requires=securetransport_db.service</p>
            <p>After=securetransport_db.service</p>
            <p>[Service]</p>
            <p>Type=forking</p>
            <p># Replace the non-root user with the user used for installing ST</p>
            <p># Replace &lt;FILEDRIVEHOME&gt; with the absolute path to the ST directory</p>
            <p># Replace PIDFile with the corresponding PID file of the service, </p>
            <p># e.g., tomcat.pid</p>
            <p># Replace &lt;service_start_script&gt; with the ST start script for the </p>
            <p># service being defined, e.g., start_admin</p>
            <p># Replace &lt;service_stop_script&gt; with the ST stop script for the  </p>
            <p># service being defined, e.g., stop_admin</p>
            <p># If a service startup  takes longer than the default timeout of <br># 90  seconds, increase the startup timeout by adding the <br># TimeoutStartSec={time}option in the  service file.</br></br></p>
            <p>User=&lt;non-root user&gt;</p>
            <p>PIDFile=&lt;FILEDRIVEHOME&gt;/var/run/admin/tomcat.pid</p>
            <p>ExecStart=&lt;FILEDRIVEHOME&gt;/bin/&lt;service_start_script&gt;</p>
            <p>ExecStop=&lt;FILEDRIVEHOME&gt;/bin/&lt;service_stop_script&gt;</p>
            <p>[Install]</p>
            <p>WantedBy=securetransport.target</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Target"></span>Target Unit File Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>[Unit]</p>
            <p>Description=Target for all SecureTransport services</p>
            <p>After=multi-user.target</p>
            <p>[Install]</p>
            <p>WantedBy=multi-user.target</p>
         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Install SecureTransport to use the embedded database](../installing_securetransport_embedded_db_unix)
-   [Install SecureTransport Server on Unix with an external database](../installing_securetransport_server_external_db_unix)
