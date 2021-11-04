{
    "title": "Transfer sites",
    "linkTitle": "Transfer sites",
    "weight": "160"
}A transfer site is a location such as a local folder or protocol server used when sending or receiving files during a server-initiated transfer. Supported protocol servers include AS2, Connect:Direct, Folder Monitor, FTP(S), Generic-HTTP(S), HTTP(S), PeSIT, SSH (SFTP), and System to Human. Transfer sites are specified and managed on a per-account basis.

When defining a transfer site as part of an account, you need to provide the information required for connecting to the site, authenticating the login and sending or receiving files. The transfer protocol you select dictates what information is required to define the transfer site.

In general, a site is used for AS2 transfers and server-initiated transfers. In the case of a server-initiated transfer, a file is either uploaded to the site when a subscription processes an uploaded file or downloaded from the site using a schedule in a subscription.

An account can have zero or more transfer sites. An account can subscribe to zero or more applications, and an application can be triggered when a file is transferred using a site.

## Common properties for all transfer sites

A transfer site in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is defined with various properties. To avoid repetition, the *common properties* for all Transfer Sites are briefly described here. Properties which are custom to each Transfer Site are described in the dedicated for each available transfer site type (scroll to the bottom of this page).

-   **Site Name** – the name of the site. This name must be unique for the account.  
    You cannot enter spaces-only values in the Site Name field.

-   **Site Type** – indicates whether transfers are internal (within a single organization) or partner (between organizations). Reported to <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Sentinel as `USERPARAMETER1` and displayed in the Sentinel event attributes.

-   **Access Level** - transfer site access level determines whether and which other accounts could reuse this transfer site in the Send To Partner step.
    -   **Private** – The access level is private. Only the current account is able to use this transfer site.
    -   **Business Unit** – Access to the transfer site is limited to the account's business unit. The current account and all accounts in the current account’s business unit can use this transfer site.
    -   **Public** – Access to the transfer site is public. All accounts are able use this transfer site.

-   **Maximum parallel transfers** – If you enter a value greater than zero, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> executes only the specified number of transfers in parallel. If the value is null or zero, the maximum number of parallel transfers is limited by system capacity.  
    The maximum number of parallel transfers limit is applied cluster wide. The limit for files transferred from the client will not be exceeded. Due to limitations in Standard Cluster communication mode, the parallel pulls limit can be exceeded when there are several connections. If you want to force the limit, then the `force.standard.cluster.sit.transfers.sync=true` system property should be added to the `start_tm_console`. Adding the property to the `start_tm_console` has a performance penalty due to increased cluster communication.  
    Note that the `force.standard.cluster.sit.transfers.sync` value overrides the value of the `force.standart.cluster.sit.pulls.sync` property, used in previous <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> versions for the same purposes.  
    You can configure **Maximum parallel transfers** with the following Transfer site protocols: AS2, FTP(S), HTTP(S), SSH, Generic-HTTP(S), SharePoint.  

    > **Note:**
    >
    > When multiple transfer limitations are set, all of them apply but the strictest limitation takes priority over the rest. The following limitations may affect server initiated transfers:
    > Maximum Parallel Transfers - the limit per Transfer Site, described here.Maximum number of parallel transfers - the limit for "Files Received from this Account or its Partners", specified in Basic Application or Advanced Routing SubscriptionsMaximum concurrent connections per host for outbound connections

<!-- -->

-   **Use Expression Language** - when checked, all possible checkboxes for boolean properties are switched to text fields. Applicable for Folder Monitor, FTP(S), HTTP(S), SSH (SFTP) and PeSIT Transfer Sites. In these text fields, you can type values or expressions for the required and the optional fields needed to define the transfer site.  
    You can use expressions in the fields indicated by a **vertical yellow bar**.
-   **Transfer Protocol** – one of the supported protocols: AS2, Connect:Direct, Folder Monitor, FTP(S), HTTP(S), SSH (SFTP), PeSIT, System to Human, or a protocol implemented using the file services interface. The protocol of an existing transfer site cannot be changed.
-   **Additional attributes** – a group of fields that allows you to add (or remove) custom attributes as *attribute:value* pairs to use with your Transfer sites. This functionality is available at the bottom of the page on the *Add Transfer Site* page, regardless of the Transfer site type. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.
-   **Custom properties** – these vary according to the protocol used for the transfer site. For more information about each protocol, see the respective subtopic for each protocol:<span id="transferSites"></span>
    -   <a href="r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
    -   <a href="r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
    -   <a href="r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
    -   <a href="r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
    -   <a href="transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
    -   <a href="transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
    -   <a href="transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
    -   <a href="transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
    -   <a href="transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
    -   <a href="transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>

**Related topics:**

-   <a href="t_st_transfersites" class="MCXref xref">Manage transfer sites</a> - create, edit or delete a transfer site
-   <a href="using_dxagent_transfersapi" class="MCXref xref">Using DXAGENT_TRANSFERSAPI variables in transfer sites</a>
