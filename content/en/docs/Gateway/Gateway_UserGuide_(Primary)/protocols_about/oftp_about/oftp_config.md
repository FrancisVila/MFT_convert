{
    "title": "Configuring Gateway for OFTP",
    "linkTitle": "Configuring for OFTP",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Protocols

[Activating OFTP protocol](#activating)

[Gateway objects required for OFTP](#required_objects)

[Creating a Local Site](#creating_local_site)

[Creating a Remote Site](#creating_remote_site)

[Creating an Application](#creating_appli)

[Creating Trading Partners](#creating_trading_partner)

<span id="activating"></span>

## Activating OFTP protocol

Before you can use Gateway to transfer files using OFTP, you must activate the protocol in the configuration menu.

Select **Connectivity &gt; Legacy protocols &gt; OFTP (Odette)**. Then select either <span style="font-weight: bold;">TCP/IP</span>.

Follow the procedure given in [Configuring protocols](../../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_legacy_odette_tcp).

<span id="required_objects"></span>

## Gateway objects required for OFTP

Before you submit a Transfer Request, you must create and configure the following Gateway objects:

-   <span style="font-weight: bold;">Local Site</span>  
    When you install Gateway, it creates a default Local Site for all protocols, including OFTP. However, you can create as many Local Sites as necessary.
-   <span style="font-weight: bold;">Remote Site</span>  
    Define your partner Site and communication attributes in the Remote Site object.
-   <span style="font-weight: bold;">Application</span>  
    Define at least one Application.

If you use any of the OFTP R2.0 file security services (file signature, encryption, compression, signed EERP or NERP), you also require Trading Partner objects.

-   <span style="font-weight: bold;">Trading Partners</span>  
    Define at least one local Trading Partner and one or more remote Trading Partners.

Use either the GUI or the <span class="code" style="font-weight: bold;">peladm</span> online command to create these objects. The following examples use the <span class="code" style="font-weight: bold;">peladm</span> online command.

<span id="creating_local_site"></span>

## Creating a Local Site

#### Example:

The following command creates a Local Site with protocol ident O1207SOPRA-PARIS UNIX1:


    peladm create_loc_site  -alias loc_odette
                            -pi O1207SOPRA-PARIS UNIX1
                            -comments "Local Site Odette"
                            -auth_obj_type SECS_ALIAS
                            -auth_obj_name mycert
                            -auth_obj_password mypass

An authentication certificate is required if you use any of the OFTP R2.0 file security services (file signature, file encryption, file compression or signed EERP/NERP).

<span id="creating_remote_site"></span>

## Creating a Remote Site

You must create Remote Sites for your partners before you can make a file transfer.

If you do not explicitly supply attributes, Gateway uses default values. If you do not specify a group when creating a Remote Site, Gateway assigns the default group name GDEFAULT.

An authentication certificate is required if you use any of the OFTP R2.0 file security services (file signature, file encryption, file compression or signed EERP/NERP).

### RFC5024 compliancy with OFTP 1.3

When contacting a partner using OFTP 1.3, by default Gateway assumes that the partner is RFC2204 compliant. Gateway sends the protocol release level SSIDLEV=1 when contacting the partner.

If you want to define a partner as being RFC5024 compliant, you must add the string "R1.4" in the Remote Site <span class="code">comments</span> field. In this case, Gateway sends SSIDLEV=2 when contacting the partner.

### Example 1: Remote Site for TCP/IP

The following command creates a Remote Site that uses TCP/IP and has the following characteristics:

-   IP address: 193.56.234.20
-   Port: 22222
-   Block size: 3500
-   Number of data blocks between two acknowledgments: 5
-   Maximum number of simultaneous server connections: 10
-   Protocol ident (non-prefixed notation): <span style="font-style: italic;">SOPRA-PARIS UNIX12</span>
-   Password to send: <span style="font-style: italic;">UNIX12</span>
-   Password to check: <span style="font-style: italic;">UNIX1</span>
-   Local Site used for identification: <span style="font-style: italic;">LOC\_Odette</span>
-   Protocol field used to transmit Gateway Application name: <span style="font-style: italic;">FILE DATASET NAME</span>
-   EERP style: International
-   Acknowledgment option: Automatically send an acknowledgement request


    peladm create_site  -alias TCP_odette
                        -comments "Remote Site: Odette on TCP/IP"
                        -protocol Odette
                        -pi SOPRA-PARIS UNIX12
                        -passwd UNIX12
                        -check_password UNIX1
                        -partner_loc_alias LOC_Odette
                        -get_appli_method AIF
                        -comm_type TCP
                        -dest_address 193.56.234.20/22222
                        -data_size_max 3500
                        -check_window 5
                        -resp_conn_max 10
                        -version R2.0
                        -auth_obj_type SECS_ALIAS
                        -auth_obj_name yourcert
                        -eerp_style IN 
                        -acknowledgment_option ack_by_monitor 


<span id="creating_appli"></span>

## Creating an Application

You must define an Application to send or receive OFTP files.

The only Application parameter specific to the OFTP protocol is the ability to set the Transfer Attribute <span style="font-weight: bold;">Record format</span> (<span class="code">-x\_rec\_fmt</span>) to <span style="font-style: italic;">Text</span>.

#### Example 1: Application to transfer ASCII files

The following command creates an Application to transfer ASCII files of 255-byte fixed-length records, using the default group name:


    peladm create_appli  -name fix255
                         -comments "fixed record length: 255"
                         -rec_fmt F
                         -rec_len 255
                         -data_code A
                         -x_rec_fmt F
                         -x_rec_len 255
                         -x_data_code A
                         -dir_path <your received files directory>

#### Example 2: Application to transfer EBCDIC files

The following command creates an Application to transfer EBCDIC files of variable record length, with maximum record length of 255 bytes, and the group name GRVAR:


    peladm create_appli -name var255
                        -group GRVAR
                        -comments "variable record length: 255"
                        -rec_fmt V
                        -rec_len 255
                        -data_code E
                        -x_rec_fmt V
                        -x_rec_len 255
                        -x_data_code E
                        -dir_path <your received files directory>

<span id="creating_trading_partner"></span>

## Creating Trading Partners

If you use any of the file security services (file signature, encryption, compression, signed EERP or NERP), you must create both local and remote Trading Partners. Define at least one local Trading Partner. You must also define one or more remote Trading Partners.

#### Example 1: Local Trading Partner


    peladm create_tradepart  -name  "my OFTP SSID"
                             -alias myoftp
                             -format CMS
                             -is_local Y
                             -encryption_obj_type { SECS_ALIAS | XPP_ENTITY | XPP_CERTIFICATE }
                             -encryption_obj_name "Sopra Sample User 1"
                             -sign_obj_type { SECS_ALIAS | XPP_ENTITY | XPP_CERTIFICATE }
                             -sign_obj_name "Sopra Sample User 1"
                             -sign_obj_password user1

#### Example 2: Remote Trading Partner


    peladm create_tradepart  -name "your OFTP SSID"
                             -alias youroftp
                             -format CMS
                             -is_local N
                             -remote_site r_odette
                             -sign N
                             -signing_algo SHA1withRSA
                             -encrypt N
                             -encryption_algo { AES256 | 3DES }
                             -compress N
                             -compress_algo zlib
                             -encryption_obj_type { SECS_ALIAS | XPP_ENTITY | XPP_CERTIFICATE }
                             -encryption_obj_name "Sopra Sample User 2"
                             -sign_obj_type { SECS_ALIAS | XPP_ENTITY | XPP_CERTIFICATE }
                             -sign_obj_name "Sopra Sample User 2"
                             -force_signed { Y | N }
                             -force_encrypted { Y | N }

Related topics

[About OFTP](../)

[Configuring protocols](../../../configuration_start_here/config_protocols_about/config_protocols)

[Working with Local Sites](../../../managing_partners_start_here/sites_start_here/managing_local_sites)

[Working with Local Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Site objects: Parameters List](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list)

[Working with Applications](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_(gui))

[Working with Applications (command line)](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli)

[Application objects: Parameters List](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli/application_object_parameter_list)

[Working with Trading Partners](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui))

[Working with Trading Partners (command line)](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli)

[Submitting an OFTP Transfer Request](../oftp_submitting_transfer)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
