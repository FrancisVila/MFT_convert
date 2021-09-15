{
    "title": "TRK configuration parameters",
    "linkTitle": "TRK configuration parameters",
    "weight": "220"
}To limit the number of messages related to monitoring the XFB.Transfer class, due to a large number of transfers, you can set the monitoring parameters as described in this section.

Parameters to regulate monitoring can have one of the following values:

-   NO: no monitoring
-   ALL: full monitoring (for each transfer status change)
-   SUMMARY: summary monitoring (created at end of the transfer)
-   UNDEFINED: undefined value
-   ERROR: all unsuccessful transfers (where the state can be Canceled, Suspended, or Interrupted - as described in [XFBTransfer system attributes](../intro_sentinel/pesit_prot_sentinel))

For a transfer command, if Sentinel monitoring is implemented, these parameters are analyzed in the following order: transfer command, transfer definition, partner definition, general parameter (CFTPARM), and lastly the UCONF parameter definition(sentinel.xfb.transfer). If the uconf is not defined, you can set it using the command CFTUTIL uconfset id=sentinel.xfb.transfer.

Parameters to regulate level of monitoring messages

The parameter definitions are taken into account in the order listed below. For example, the transfer request definition takes precedence over the partner definition.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using <span>Central Governance</span> to manage Transfer CFT, you can only use TRK at the flow level, which corresponds to transfer models, but not for partners and general parameters.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Definition </th>
         <th>NO   </th>
         <th>ALL  </th>
         <th>SUMMARY  </th>
         <th>ERROR</th>
         <th>UNDEFINED</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1. Transfer requests (SEND/RECV in requester mode only)         </td>
         <td> No tracking         </td>
         <td>Full tracking         </td>
         <td>First and last         </td>
         <td>Errors only         </td>
         <td>Uses the transfer definition          </td>
      </tr>
      <tr>
         <td>
            <p>2. Transfer models (CFTSEND/CFTRECV)</p>
         </td>
         <td>
            <p>No tracking</p>
         </td>
         <td>
            <p>Full tracking </p>
         </td>
         <td>
            <p>First and last</p>
         </td>
         <td>Errors only         </td>
         <td>Uses the partner definition          </td>
      </tr>
      <tr>
         <td>
            <p>3. Partners </p>
         </td>
         <td>
            <p>No tracking</p>
         </td>
         <td>
            <p> Full tracking </p>
         </td>
         <td>First and last         </td>
         <td>Errors only         </td>
         <td> Uses the general parameter definition          </td>
      </tr>
      <tr>
         <td>4. General parameters (CFTPARM)         </td>
         <td>No tracking         </td>
         <td>Full tracking         </td>
         <td>First and last         </td>
         <td>Errors only         </td>
         <td>Uses the UCONF definition (sentinel.xfb.transfer)         </td>
      </tr>
      <tr>
         <td>5. UCONF definition         </td>
         <td>
            <p>No </p>
            <p>tracking</p>
         </td>
         <td>Full tracking         </td>
         <td>First and last         </td>
         <td>Errors only         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

### Check Transfer CFT's Sentinel task (CFTTRK) activity

Enter the following command to get the Transfer CFT CFTTRK details:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>cftutil mquery object=SYSTEM         </td>
      </tr>
   </tbody>
</table>

When Sentinel is available, the following messages display in the log:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTI24I CFTTRK MQUERY OBJECT=SYSTEM</p>
            <p>CFTI24I CFTTRK Nb max messages = 100</p>
            <p>CFTI24I CFTTRK nb messages = 65</p>
            <p>CFTI24I CFTTRK Sentinel state = connected</p>
         </td>
      </tr>
   </tbody>
</table>

If Sentinel is not available, or has been disabled, the following messages display in the log:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTI24I CFTTRK MQUERY OBJECT=SYSTEM</p>
            <p>CFTI24I CFTTRK Nb max messages = 100</p>
            <p>CFTI24I CFTTRK nb messages = 102</p>
            <p>CFTI24I CFTTRK Sentinel state = disconnected</p>
         </td>
      </tr>
   </tbody>
</table>

## Command parameters

CFTPARM

TRKPART = { \*UNDEFINED \*| ALL | SUMMARY | NO | ERROR }

TRKSEND = { \*UNDEFINED \*| ALL | SUMMARY | NO | ERROR }

TRKRECV =
{ \*UNDEFINED \*| ALL | SUMMARY | NO | ERROR }

These parameters define the TRK default settings for the CFTPART, CFTSEND, and CFTRECV commands respectively.

SEND/RECV

TRK =
{ \*UNDEFINED\* | ALL | SUMMARY | NO | ERROR }

An optional parameter with a default value of UNDEFINED. Enables tracking for a query.

CFTSEND/CFTRECV

TRK =
{ UNDEFINED | ALL | SUMMARY | NO | ERROR }

An optional parameter having TRKSEND/TRKRECV as the default values. Enables tracking for the file model (IDF).

CFTPART

TRK = { UNDEFINED | ALL | SUMMARY | NO | ERROR }

An optional parameter having TRKPART as the default value. Enables tracking for a partner.
