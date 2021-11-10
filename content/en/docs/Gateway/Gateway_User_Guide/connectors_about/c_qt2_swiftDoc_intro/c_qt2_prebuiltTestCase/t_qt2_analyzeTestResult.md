{
    "title": "Analyzing test results",
    "linkTitle": "Analyzing test results",
    "weight": "330"
}To confirm the success or failure of the test transfer, first check the Mailbox screen in Gateway Navigator.

<img src="/Images/Gateway/03000022_661x152.png" class="maxWidth" />

In the preceding example, the initial test case transfer is 797.

For detailed results of the test case transfers, open the trace file for the transfer in the directory:

\[PATH\]\\Synchrony\_V4.x.x\\qt2\\tmp

Trace file numbers correspond to the Local TransferID number. For the transfer 797 displayed in the Mailbox screen, the corresponding trace file is 797.trace.

The following is an example of a trace file 111.trace result for a 0001 type test case.

<table>
   <tbody>
      <tr>
         <td><p>Gateway unknown. Assuming 6112.</p>
<p> </p>
<p>+++++ TRACE from /swiftrdq/users/swiftrdq/Axway/Synchrony_V4.1.1/qt2/scripts/tg2msg.sh TO_BO_QT2_OK1 TO_BO_QT2_FILEMSG_KO_P1</p>
<p> </p>
<p>InterAct Response received from the SSP. Begin Processing</p>
<p>Tuesday, October 14, 2008 6:05:31 PM CEST</p>
<p>Original Request ID: 797</p>
<p>Current Transfer ID: 801</p>
<p>QT2ROOT=/swiftrdq/users/swiftrdq/Axway/Synchrony_V4.1.1/qt2</p>
<p>GATEWAY=6112</p>
<p>MODE=SIM</p>
<p>FULLCMPENGINE=TRUE</p>
<p>MODEL_OK=TO_BO_QT2_OK1</p>
<p>MODEL_ERR=TO_BO_QT2_FILEMSG_KO_P1</p>
<p>QT2_TP_REMOTE_FILE_SSP=QT2_TP_REMOTE_FILE_SSP</p>
<p>RQT_GPD=camt.998.001.01</p>
<p>P_TRY_NO=3</p>
<p>P_TRY_DELAY=5</p>
<p>VCAMT=3</p>
<p>Setting Variables</p>
<p>Start Unpacking Section</p>
<p>x_ftp_command=dt="ZIP-Base64"</p>
<p>No decompression necessary</p>
<p>File to be Xalan-ed to extract the technical information, if any</p>
<p>~~~~~ TGOUT=/swiftrdq/users/swiftrdq/Axway/Synchrony_V4.1.1/qt2/tmp/801.TGOUT ~~~~~</p>
<p>&lt;SwInt:Gateway xmlns:SwInt="urn:swift:snl:ns.SwInt"&gt;</p>
<p> </p>
<p>&lt;SwInt:ResponsePayload dt="ZIP-Base64"&gt;</p>
<p>  &lt;AppHdr xmlns="urn:swift:xsd:$ahV10"&gt;</p>
<p>    &lt;From&gt;</p>
<p>      &lt;Type&gt;NAME&lt;/Type&gt;</p>
<p>      &lt;Id&gt;PM&lt;/Id&gt;</p>
<p>    &lt;/From&gt;</p>
<p>    &lt;MsgRef&gt;ABCDEFGHIJKLMNOPQRST1234567890&lt;/MsgRef&gt;</p>
<p>    &lt;CrDate&gt;2007-01-01T12:00:00&lt;/CrDate&gt;</p>
<p>   &lt;/AppHdr&gt;</p>
<p>   &lt;Document xmlns="ssp.pm.ReturnLimit$camt.010.001.03"&gt;</p>
<p>     &lt;camt.010.001.03&gt;</p>
<p>       &lt;MsgId&gt;</p>
<p>         &lt;Id&gt;ABC123456&lt;/Id&gt;</p>
<p>       &lt;/MsgId&gt;</p>
<p>       &lt;BizQryRef&gt;</p>
<p>         &lt;QryRef&gt;ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghi&lt;/QryRef&gt;</p>
<p>       &lt;/BizQryRef&gt;</p>
<p>       &lt;BizRpt&gt;  </p>
<p>         &lt;CurLmt&gt;</p>
<p>           &lt;LmtId&gt;</p>
<p>             &lt;BilLmtCtrPtyId&gt;</p>
<p>               &lt;BIC&gt;BANKNL2AXXX&lt;/BIC&gt;</p>
<p>             &lt;/BilLmtCtrPtyId&gt;</p>
<p>             &lt;Tp&gt;BILI&lt;/Tp&gt;</p>
<p>             &lt;AcctOwnr&gt;BANKNL2AXXX&lt;/AcctOwnr&gt;</p>
<p>           &lt;/LmtId&gt;</p>
<p>           &lt;Lmt&gt;</p>
<p>             &lt;Amt&gt;</p>
<p>                &lt;AmtWthtCcy&gt;123456.12&lt;/AmtWthtCcy&gt;</p>
<p>             &lt;/Amt&gt;   </p>
<p>             &lt;CdtDbtInd&gt;DBIT&lt;/CdtDbtInd&gt;</p>
<p>           &lt;/Lmt&gt;  </p>
<p>         &lt;/CurLmt&gt; </p>
<p>         &lt;DfltLmt&gt;</p>
<p>           &lt;LmtId&gt; </p>
<p>             &lt;BilLmtCtrPtyId&gt;</p>
<p>               &lt;BIC&gt;BANKNL2AXXX&lt;/BIC&gt;</p>
<p>             &lt;/BilLmtCtrPtyId&gt;  </p>
<p>             &lt;Tp&gt;MULT&lt;/Tp&gt;</p>
<p>             &lt;AcctOwnr&gt;BANKNL2AXXX&lt;/AcctOwnr&gt;</p>
<p>           &lt;/LmtId&gt;</p>
<p>           &lt;Lmt&gt;</p>
<p>             &lt;Amt&gt;  </p>
<p>               &lt;AmtWthtCcy&gt;123456.12&lt;/AmtWthtCcy&gt;</p>
<p>             &lt;/Amt&gt;</p>
<p>             &lt;CdtDbtInd&gt;DBIT&lt;/CdtDbtInd&gt;</p>
<p>           &lt;/Lmt&gt;   </p>
<p>          &lt;/DfltLmt&gt;</p>
<p>       &lt;/BizRpt&gt;</p>
<p>     &lt;/camt.010.001.03&gt;      </p>
<p>   &lt;/Document&gt;</p>
<p>&lt;/SwInt:ResponsePayload&gt;</p>
<p>&lt;/SwInt:Gateway&gt;</p>
<p>~~~~~ TGOUT=/swiftrdq/users/swiftrdq/Axway/Synchrony_V4.1.1/qt2/tmp/801.TGOUT ~~~~~</p>
<p>TG2_CODE=</p>
<p>TG2_DESC=Document received.</p>
<p>TG2_ALERT=FALSE</p>
<p>TG2_REF=ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghi</p>
<p>TG2_ID=ABC123456</p>
<p>Making Decision</p>
<p>Unknown status code. Calling RoutingData with ERROR_IA=FALSE</p>
<p>ENTER: routingdata</p>
<p>Variable ERROR_IA=FALSE</p>
<p>ENTER: dotrans</p>
<p>Try 1 of 3</p>
<p>peltrans -ml TO_BO_QT2_OK1 -fc /home/swiftrdq/Axway/Synchrony_V4.1.1/Gateway_V6.12.1/run_time/tmp/F0000801.dcm -rfx 801 -prop LocalPartner=QT2_TP_LOCAL1 -prop RemotePartner=QT2_TP_REMOTE_SSP -prop RequestType=camt.998.001.02 -prop Service=swift.generic.ia!x -prop RequestRef=0001</p>
<p>LEAVE: dotrans</p>
<p>LEAVE: routingdata</p>
<p>Tuesday, October 14, 2008 6:05:32 PM CEST</p>
<p>----- END TRACE from tg2msg</p>         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
