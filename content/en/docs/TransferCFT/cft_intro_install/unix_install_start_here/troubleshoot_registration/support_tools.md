{
    "title": "Support tools and contacting Support",
    "linkTitle": "Support tools and contacting Support",
    "weight": "200"
}This section describes the tools available to help you collect information and contact support if you are unable to troubleshoot an error or issue.

## <span id="Contacting_the_Axway_support"></span>Accessing the Axway Support site

Visit the Axway [Support](https://support.axway.com/) site to view the knowledgebase, product articles, and browse existing cases. Or, to obtain the email address and phone number of your nearest Axway
support site, click **Contact
us**.

### <span id="Opening_a_support_case"></span>Opening a Support case

Before contacting Customer Support, we suggest that you start by using
the Axway online patch library to see if there is a patch available for
your problem, or by searching for a solution in the Knowledge Database.
If you still need to contact Support, have the following information available
if possible:

-   Product version
-   Operating system
-   cft\_support (see [Support tools](#))

To submit a Support request, you can do the following:

-   Submit and track
    your request through the Axway Support Web site [support.axway.com](https://support.axway.com/).
-   Each time you submit a support request, that request is assigned a unique
    number. Use this specific number when you contact Customer
    Support concerning that case.
-   You must have a user account to submit a Support request.

## Using cft\_support

The cft\_support tool collects all of the needed information from the customer's Transfer CFT installation environment, including the static configuration (PARM/PART), Unified Configuration parameters (UCONF), catalog information, communication media file status (CFTCOM), log files, execution environment (variables), disk space, and so on. This information is then packaged into a archive file called cft-support-&lt;date>(.tar.gz|.zip).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using the cft_support tool on other Operating Systems, refer to the OS-specific guide for the correct syntax.         </td>
      </tr>
</table>

### Using Copilot

From the Copilot UI, click the ![Debug command icon](debug_alt.gif)debug icon. The report is saved in the Transfer CFT runtime directory, after which you are prompted to download the report to your desktop.

### Using command line

In command line, enter: cft\_support collect \[options\]

Options:

-   --help: Display this help and exit.
-   --cat-filter: Filter the CFTUTIL LISTCAT output. See [LISTCAT](../../../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listcat_command), or enter CFTUTIL HELP CMD=LISTCAT, to view available parameters.
-   --cat-debug-filter: Filter the CFTUTIL LISTCAT CONTENT=DEBUG output. This option overrides --cat-filter.
-   --no-core-analysis-gdb: Do not use gdb to analyze the cores. *Unix only*
-   --no-core-analysis-dbx: Do not use dbx to analyze the cores. *Unix only*

Examples

Only collect information for a given transfer:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>cft_support collect --cat-filter="IDTU=A0000001"</span>
         </td>
      </tr>
   </tbody>
</table>

Collect information for all transfers in error for a given partner:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>cft_support collect --cat-filter="DIAGI=ERROR, PART=PARIS"</span>
         </td>
      </tr>
   </tbody>
</table>

Collect transfer information related to a given IDF for all transfers in a brief LISTCAT, and only those transfers in error in a debug LISTCAT:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>cft_support collect --cat-filter="IDF=BIN" --cat-debug-filter="IDF=BIN, DIAGI=ERROR"</span>
         </td>
      </tr>
   </tbody>
</table>

#### IBM i

The CFTSUPPORT command executes a program located in CFTPGM. This program generates a tar file in the IFS environment that includes information that is necessary for Axway support.

Additionally, two options are available for CFTSUPPORT:

-   `CATFIL('IDTU=A0000001')`: Filters the CFTUTIL LISTCAT output.
-   `DBGCATFIL('IDTU=A0000002')`: Filters the CFTUTIL LISTCAT CONTENT=DEBUG output.

Example

CFTSUPPORT IFSPATH('/home/cft/axway/cft/runtime/cftsupport')DBGCATFIL('IDTU=A0000002')

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">CFTSUPPORT is currently not supported with an independent ASP (IASP).         </td>
      </tr>
</table>

#### z/OS

Run the JCL XSUPPORA. You can transfer the resulting file to a Windows system, zip, and attach to an email request.

### <span id="Activating_CFT_traces"></span>Activating Transfer CFT traces when a problem occurs during the transfer

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">ATM traces are available only when using Transfer CFT <span>Local Administration</span>. However Central Governance managed Transfer CFT is the recommended version.         </td>
      </tr>
</table>

Transfer CFT traces are managed by the Advanced
Trace Manager
(ATM) component. ATM is a problem resolution assistance tool that is used to save Transfer CFT
information, and retrieve previously saved Transfer CFT information.

You may need to initiate tracing in order to assist Transfer CFT Support
service if an error occurs. The Transfer CFT Support service can analyze
the traces to better help you resolve the issue. See [How to use ATM traces](../../../../troubleshoot_intro/traces_in_cft)