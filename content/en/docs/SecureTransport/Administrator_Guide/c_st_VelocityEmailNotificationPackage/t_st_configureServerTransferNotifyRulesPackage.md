{
    "title": "Configure the ServerTransferNotify rules package",
    "linkTitle": "Configure the ServerTransferNotify rules package",
    "weight": "330"
}The `ServerTransferNotify` package rule, when enabled, handles only cases where the transfer fails after it is started. The `ServerTransferNotify` rules package ships with one rule, also named `ServerTransferNotify`. This rule is configured to send an email if the server initiated upload or download operation exhausts the last retry or encounters a permanent failure.

If the SecureTransport administrator needs a way to handle all cases like wrong login credentials and both permanent and temporary failures, the following modifications can to be done:

1.  Select **Setup > TM Settings** to display the *TM Settings* page.

2.  Locate and disable the `ServerTransferNotify` rule package by selecting it and clicking **Disable**.

3.  Locate the `FTPTransfer` rule package, select it, and click **Export** to export the package to modify it.

4.  Using an external XML editor, modify the `FTPTransfer` rule package to include the following:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>IF ( ( EventType &lt;equal&gt; Server Transfer - Pull OR EventType &lt;equal&gt; Server Transfer - Push ) AND DXAGENT_SITE_PROTOCOL &lt;equal&gt; ftp ) THEN { 
 id=1 streaming(none) 
 </p>
            <p>In-process&gt; com.tumbleweed.st.server.ftp.agent.FtpTransferAgent ( Impersonation="true" )
 id=2 executeafter(1) streaming(none)
 </p>
            <p>In-process&gt; com.tumbleweed.st.server.tm.agents.RetryAgent ( Impersonation="true", dontretry="0 1 2 4 5", internalretry="6" )
id=3 executeafter(2) streaming(none)
 </p>
            <p>In-process&gt; com.tumbleweed.st.server.tm.agents.Continue ( continue="2 3 4 5" )
 id=4 executeafter(3) streaming(none) 
 </p>
            <p>In-process&gt; com.tumbleweed.st.server.mailer.agent.EmailNotification ( messagetemplate:-PushDeliveryFailure.xhtml, mailserver=&lt;mailserver&gt;, mailfrom=&lt;sender_email&gt;, mailto=&lt;recipient_email&gt; ) 
 } </p>
         </td>
      </tr>
   </tbody>
</table>

5.  Save the modified `FTPTransfer` rule package.

6.  Import the modified `FTPTransfer` rule package into the *TM Settings* page by clicking **Import**.

7.  Browse to the select the modified `FTPTransfer` rule package.

8.  Select **Overwrite existing**.

9.  Click **Import**.

10. Select the modified `FTPTransfer` rule package, and click **Enable**.

This procedure can be repeated on the `HttpTransfer`, `PesitTransfer`, and `SSHTransfer` rule packages.
