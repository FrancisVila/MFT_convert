{
    "title": "Set up FTP active mode",
    "linkTitle": "Set up FTP active mode",
    "weight": "120"
}You can configure {{< SecureTransport/componentshortname  >}} to use active mode connections for server-initiated transfers over FTP. Use the active mode options to configure the server-initiated transfer agents to initiate these requests. You can specify an active mode base port and a range of ports that can be used for active mode. Make sure the ports are accessible on the firewall.

The base port represents the first port number you want to assign. The number of ports specifies how many open ports you want to allow. For example, the base port is set to 10000 and the number of ports is set to 1024, active mode connections can use only the ports from 10000 to 11023. The end port should display 11023. Acceptable values are between 1024 and 65535. If the range is not specified, the server randomly selects an unused high port number greater than 1023 for active mode.

Active FTP mode can be used only for internal connections where there is no proxy between {{< SecureTransport/componentshortname  >}} and the remote server. You must select **Enable Active Connection Mode** to use Active FTP in an FTP transfer site.

1.  Select **Setup > FTP Settings** to open the *FTP Settings* page.
2.  Under *FTP Active Mode*:  
    1.  Type the appropriate port number for the **Base Port**. This is the first port used.
    2.  Type the **Number Of Ports**. This value sets the range of ports available for use.  
        The **Port End** field should display the appropriate port number for the last port in the range you want to use.
3.  Click **Save** to apply the changes.

> **Note:**
>
> To use Active FTP with an FTP(S) transfer site, by pass the proxy by setting the Network Zone field to none. See FTP(S) transfer sites.

**Related topics:**

-   <a href="../t_st_ftpservermessages" class="MCXref xref">FTP server messages</a>
-   <a href="../t_st_ftppassivemode" class="MCXref xref">Set up FTP passive mode</a>
-   <a href="../r_st_ftpserverlimitations" class="MCXref xref">FTP server limitations</a>
-   <a href="../t_st_improveftpperformance" class="MCXref xref">Improve FTP performance on a multi-homed system</a>
-   <a href="../t_st_increaseftptimeout" class="MCXref xref">Increase the timeout for large files using server-initiated transfer</a>
