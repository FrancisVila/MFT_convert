{
    "title": "Prerequisites for non-root installations",
    "linkTitle": "Prerequisites for non-root installations",
    "weight": "130"
}If you are installing {{< SecureTransport/componentshortname  >}} for a non-root execution, consider the following information before starting the installer:

-   The installation process should be started with the non-root user, defined in the `/etc/passwd` file and have a valid shell that allows login and command execution. For example, `/sbin/nologin` is not a valid shell, but `/bin/bash` is a valid shell.
-   Мake sure that the non-root user has a created home folder with the proper permissions:
    -   useradd stuser
    -   mkdir /home/stuser (default)
    -   chown -R stuser: /home/stuser

<!-- -->

-   Increase the resources available to the shell of the non-root user:
    -   open files
    -   max user process

      
    You can check the values of these limits by using `ulimit -a`. Set them to minimum **65536** or higher.

<!-- -->

-   The {{< SecureTransport/componentshortname >}} installation routine calls crontab to set up some entries for log rotation and process monitoring. To tell the installer to skip the calls to crontab:  
    `export INSTALL_CRON=false`

**Related topics:**

-   [Supported UNIX-based operating systems]()
-   [Minimum UNIX hardware requirements]()
-   [Host name resolution]()
-   [Requirements for specific operating systems](../requirements_for_specific_operating_systems)
-   [General prerequisites]()
