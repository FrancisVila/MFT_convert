{
    "title": "Troubleshoot the user interface",
    "linkTitle": "Troubleshoot the user interface",
    "weight": "190"
}The Copilot server is running, but cannot connect to the user interface

After a successful installation you can start the Transfer CFT Copilot server, but cannot connect to the user interface. Check the following:

Check task manage and verify that the copilot "copxxx" processes are running (as shown below on a Windows platform). For example, Coprestw.\* must be running.

<img src="/Images/TransferCFT/copui_process.png" class="mediumWidth" />

In the Transfer CFT installation, access the <span class="code">&lt;install\_directory>/runtime/run</span> folder &gt; and check the following files for errors or failed steps:

-   copmsg.out file
-   copui.trc file

Type of messages can include:

**Certificate issues**:

copsrestw\[10986\] CFT.REST.API \[0\] TRACE From restsslw\_get\_config\_from\_uconf (restsslw.c:457)

copsrestw\[10986\] CFT.REST.API \[0\] \* Error: copilot.ssl.SslKeyFile is not set

copsrestw\[10986\] CFT.REST.APITCP\[0\] TRACE From rest\_worker\_server\_grab\_cb\_dispatch (restwrk.c:2163)

copsrestw\[10986\] CFT.REST.APITCP\[0\] \* Warning could not get Secure Configuration. Please check CG registration or copilot.ssl.\* uconf parameters

Check:

Check for incorrect certificate.

If using a certificate that requires a private key, ensure that you have provided .

**Incorrect path or name**:

00000007 copsrestw\[11468\] CFT.REST.API \[0\] \* Can't parse Certificate file /home/cftqa64/CFT/CFTQAuser.p12

00000008 copsrestw\[11468\] CFT.REST.API \[0\] \* ===> Failed to open certificate file: fname=/home/cftqa64/CFT/CFTQAuser.p12, size=0, errno=2.

00000009 copsrestw\[11468\] CFT.REST.APITCP\[0\] TRACE From rest\_worker\_server\_grab\_cb\_dispatch (restwrk.c:2163)

00000010 copsrestw\[11468\] CFT.REST.APITCP\[0\] \* Warning could not get Secure Configuration. Please check CG registration or copilot.ssl.\* uconf parameters

Check:

An error in the name or path to the certificate (in UNIX also check for case sensitivity).

**Password issues**:

00000006 copsrestw\[12013\] CFT.REST.API \[0\] TRACE From restsslw\_get\_config\_from\_uconf (restsslw.c:396)

00000007 copsrestw\[12013\] CFT.REST.API \[0\] \* Can't parse Certificate file /home/cftqa64/CFT/CFTQAUSER.p12

00000008 copsrestw\[12013\] CFT.REST.API \[0\] \* ===> PKCS12 parse error: error:23076071:PKCS12 routines:PKCS12\_parse:mac verify failure.

00000009 copsrestw\[12013\] CFT.REST.APITCP\[0\] TRACE From rest\_worker\_server\_grab\_cb\_dispatch (restwrk.c:2163)

00000010 copsrestw\[12013\] CFT.REST.APITCP\[0\] \* Warning could not get Secure Configuration. Please check CG registration or copilot.ssl.\* uconf pa

Check that the password is correct for the used certificate.

**Certificate has expired**:

00000006 copsrestw\[14805\] CFT.REST.API \[0\] TRACE From restsslw\_get\_config\_from\_uconf (restsslw.c:396)

00000007 copsrestw\[14805\] CFT.REST.API \[0\] \* Can't parse Certificate file /home/cftqa64/cft36/runtime/XPP\_Sample\_User1.p12

\+ 2020/06/11 18:09:19.048918 00000008 copsrestw\[14805\] CFT.REST.API \[0\] \* ===> PKCS12 parse error: error:23076071:PKCS12 routines:PKCS12\_parse:mac verify failure.

00000009 copsrestw\[14805\] CFT.REST.APITCP\[0\] TRACE From rest\_worker\_server\_grab\_cb\_dispatch (restwrk.c:2163)

00000010 copsrestw\[14805\] CFT.REST.APITCP\[0\] \* Warning could not get Secure Configuration. Please check CG registration or copilot.ssl.\* uconf pa

Check the expiration date and replace as needed.

Access management issue

A connection error message displays in the <span class="code">$CFTDIRRUNTIME/run/copsmng.out</span> file:

CONNECT action for SERVICE:UI resource not allowed for user: &lt;username>

To troubleshoot:

-   Check the values in the [User interface connection](../#Configur2) diagram.
-   Check that the user has the appropriate privileges.

## Transfer CFT is locked and you cannot log on the user interface

If you are using a third party application such as SQLite Expert Personal and you perform, for example, a transaction on the CFTPARM database for a SQL request, the database and user interface may lock up.

Begin Transaction option

![](/Images/TransferCFT/sql1.png)

To unlock the database and correct related issues, you must either perform a **Rollback** or a **Commit** on the third party application.

Rollback option

![](/Images/TransferCFT/sql2.png)

Commit option

![](/Images/TransferCFT/commit_sqlite.png)

Other issues

If the sends an **404 not found** reply when connecting to the URL, please check that the <span class="code">cftui </span>alias parameters are set in UCONF as follows:

-   copilot.http.aliases.cftui.alias=/cft/ui
-   copilot.http.aliases.cftui.path=&lt;installation\_path>/Transfer\_CFT/home/distrib/cftui

Check:

-   If the server sends an **invalid credential** reply, check that the UCONF <span class="code">copilot.restapi.authentication\_method</span> and <span class="code">am.type</span> parameters are consistent with the **REST API server authentication method** diagram. Please see <a href="../#Authentication_methods" class="MCXref xref">Authentication methods</a>
-   If the server sends an **insufficient rights** reply, this indicates that access management is enabled (either <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> or internal AM) and that you do not have the CONNECT privilege on the SERVICE:UI resource.
-   If you are using the **predefined filters** and there seem to be missing transfers or messages, it is possible that they are not displaying due to a difference in time between the client and the server. This is because the predefined filters use the client time and not the server time.

 