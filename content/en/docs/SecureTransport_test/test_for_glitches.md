{
    "title": "Test for glitches",
    "linkTitle": "Test for glitches",
    "weight": "30"
}-   
Enter the following commands to run the Axway Installer:



        ./setup.sh -m console

1. ttttttttttt
3. mmmmmmmmmmmmmm gggg hhhhvzersr vz'(z'()) 

-   Press Enter.  

    The installer will display the license agreement page by page.

    After each one there is a **Press ENTER to continue** prompt.

    After all license agreement pages are displayed, the installer displays the license agreement and the following prompt (for accepting or rejecting the license agreement):


        [1] I accept the terms of the license agreement.
        [2] I do not accept the terms of the license agreement.
        Enter a number [1-2] to select an option or (Previous, Quit).
        :>2


-   AAA Note: All certificates need to be regenerated and DB configuration updated prior to certificates' expiration.



-     

      



-   The installer displays the default SecureTransport ports, nightly log rotation, and import secret file configuration:



        ----------------------------------------

        Configuration

        ----------------------------------------

          Select the options that you want to enable:

          SecureTransport Ports

        1: SSL Admin UI Port:           444

        2: Tomcat Shutdown Port:        8005

        3: Enable Nightly Log Rotation: true

          Import Secret File

        To synchronize the configuration of this ST Server with another ST Server you

                                        must import the same secret file (located on the remote ST Server at:

                                        <installation path>/bin/taeh). Otherwise, leave the field empty

                                        to generate a new secret file.

        4: Secret File Path:



                  



                                    Enter a number [1-4] to select an option or (Next, Previous, Quit).

        :>Next



-   Accept or modify the default configuration.  

   The information required is:

    -   **SSL Admin UI Port** – The port used to connect to the Administration Tool. When you install SecureTransport as a non-root user, the default value for Admin port number is 8444.

    -   **Tomcat Shutdown Port** – The port used to shut down the Tomcat server

    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, SecureTransport Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation. For more information, see the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>, Server Log Rotation Scheduling.

    -   **Secret File Path** – The path to the secret file you copied from another SecureTransport Server installation to this system, if blank, the installer creates a secret file (See [Secret file](secret_file.htm#beforeinstallst_3365039947_1107715).)

