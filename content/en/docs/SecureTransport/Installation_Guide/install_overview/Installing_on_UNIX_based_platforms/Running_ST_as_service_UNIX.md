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
      
    

        # systemctl enable <service_name> 

7.  Enable `securetransport.target` to create the required links and set the SecureTransport services to start on boot.
      
    

        # systemctl enable securetransport.target

8.  Reload the `systemctl` daemon by running the following command:
      
    

        # systemctl daemon-reload

9.  Reboot the system and verify that the SecureTransport services start as expected.

### <span id="Service"></span>Service Unit File Example

    [Unit]Description=SecureTransport service unit# If this is an Enterprise Cluster core server, or  the  # securetransport_db service file, remove the lines Requires= and After=Requires=securetransport_db.serviceAfter=securetransport_db.service[Service]Type=forking# Replace the non-root user with the user used for installing ST# Replace <FILEDRIVEHOME> with the absolute path to the ST directory# Replace PIDFile with the corresponding PID file of the service, # e.g., tomcat.pid# Replace <service_start_script> with the ST start script for the # service being defined, e.g., start_admin# Replace <service_stop_script> with the ST stop script for the  # service being defined, e.g., stop_admin# If a service startup  takes longer than the default timeout of 
    # 90  seconds, increase the startup timeout by adding the 
    # TimeoutStartSec={time}option in the  service file.User=<non-root user>PIDFile=<FILEDRIVEHOME>/var/run/admin/tomcat.pidExecStart=<FILEDRIVEHOME>/bin/<service_start_script>ExecStop=<FILEDRIVEHOME>/bin/<service_stop_script>[Install]WantedBy=securetransport.target

### <span id="Target"></span>Target Unit File Example

    [Unit]Description=Target for all SecureTransport servicesAfter=multi-user.target[Install]WantedBy=multi-user.target

**Related topics:**

-   [Install SecureTransport to use the embedded database](../installing_securetransport_embedded_db_unix)
-   [Install SecureTransport Server on Unix with an external database](../installing_securetransport_server_external_db_unix)
