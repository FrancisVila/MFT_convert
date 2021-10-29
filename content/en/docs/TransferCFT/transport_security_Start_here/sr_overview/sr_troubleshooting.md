{
    "title": "Troubleshoot Secure Relay ",
    "linkTitle": "Troubleshoot Secure Relay ",
    "weight": "290"
}Should you incur an issue, you can begin by checking for information in the following files:

-   Secure Relay Master Agent log file: secure\_relay.ma.log\_fname = C:\\cft35\\runtime\\log\\xsrMaster.log
-   Secure Relay Router Agent log file: located by default in the &lt;install\_dir>/SecureRelayRA/log/router.log
-   Transfer CFT log messages: check for the messages CFTS63F and CFTS64I, which provide information about the SecureRelay status

You can refer to the [Secure Relay documentation](https://docs.axway.com/bundle/SecureRelay_271_AdministratorsGuide_allOS_en_HTML5/page/Content/AxwayStartPageRA_admin.htm) for additional information.

## Check Transfer CFT log messages...

If you find the following messages in the Transfer CFT log, you may want to check the **Possible cause**:

Possible cause: No Router Agent available

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTS63F Secure Relay fatal error _ Secure Relay register error 2 (Error sending listen request to RA DMZ0: CFTS63F+com.axway.xsr.agent.master.context.router.RouterAgentContextException: MPX channel is currently not available)</p>         </td>
      </tr>
   </tbody>
</table>

Possible cause: Java not set

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTS63F Secure Relay fatal error _ Java binary file not found:</p>
            <p>CFTS63F Secure Relay fatal error _ Please set uconf:cft.jre.java_binary_path parameter</p>
            <p>CFTI10F Init error _ failed to start the Secure Relay Master Agent CFTS63F Secure Relay fatal error _ (13) Permission denied (in UNIX environments)</p>         </td>
      </tr>
   </tbody>
</table>

Possible cause: Problem related to secure\_relay.ma.ca\_cert\_fname

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTI09F Init error _ Communication process CFTI10F Init error _ failed to start the Secure Relay Master Agent</p>         </td>
      </tr>
   </tbody>
</table>

Possible cause: Firewall or SAP overlap issue

The following messages may display indicating a SAP overlap (SAP is already used) or that there is a firewall issue:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTCFTS63F Secure Relay fatal error _ Secure Relay register error 2 (Error sending listen request to RA DMZ0:</p>
            <p>CFTS63F+com.axway.xsr.agent.master.context.router.RouterAgentContextException: MPX channel is currently not available)</p>
            <p>CFTI22F CFTPROT=PESIT Register request failure CS=00000098</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer CFT and the Master Agent fail to start

Possible cause: After changing the MA certificate, the secure\_relay.ma.cert\_fname parameter points to an invalid file

Transfer CFT fails to start and displays a message similar to the following in the cft.out file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Error accessing user certificate keystore file &lt;certificate name&gt; (password might be wrong): java.io.IOException: keystore password was incorrect</p>         </td>
      </tr>
   </tbody>
</table>

To  correct, delete or rename the file referenced by the secure\_relay.ma.cert\_password\_fname parameter (by default, XsrPwd.dat) prior to restarting Transfer CFT.
