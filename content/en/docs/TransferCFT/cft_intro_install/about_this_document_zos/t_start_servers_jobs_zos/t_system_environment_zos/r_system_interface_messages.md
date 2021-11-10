{
    "title": "System interface messages",
    "linkTitle": "System interface messages",
    "weight": "270"
}The Transfer CFT system interfaces generate z/OS operator messages that display on the system console, and appear when:

-   A severe error is detected by a system function

<!-- -->

-   Or the corresponding SGTRACE trace is active

> **Note:**
>
> Certain OS specific messages that are auto-documented, CFDMnnx, CARMnnx, CCFTnnx, CFRNnnx, CFCAnnx, and CFTInnx, may not be detailed in this document. These messages are considered self-explanatory.

## System interface message definitions

The messages have the following format:

-   4 letters corresponding to the system interface

<!-- -->

-   2 digits to number the messages

<!-- -->

-   1 classification letter

<!-- -->

-   The message text

Transfer CFT z/OS system interface messages

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Message</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CFINnnI:text</p>         </td>
         <td><p>CFTINT interface information messages under VTAM.</p>         </td>
      </tr>
      <tr>
         <td><p>SGEXnnL:text</p>         </td>
         <td><p>Task manager information message that displays with information ‘SGTRACE 2’.</p>         </td>
      </tr>
      <tr>
         <td><p>SGABnnL:text</p>         </td>
         <td><p>Message consecutive to a Transfer CFT abnormal end. These messages are also recorded in the Transfer CFT diagnostics file.</p>         </td>
      </tr>
      <tr>
         <td><p>SYNA01E:text</p>         </td>
         <td><p>The text is returned by the MACRO SYNADAF following an input/output error.</p>         </td>
      </tr>
   </tbody>
</table>

**Transfer CFT z/OS messages**

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Message</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CFST00E</p>         </td>
         <td><p>Transfer CFT region is limited to 1024 Mb. It is recommended that you not start Transfer CFT with REGION=0M.</p>         </td>
      </tr>
      <tr>
         <td><p>CHSM01I</p>         </td>
         <td><p>HSM Recall of: filename HSM recall in synchronous mode for a file.</p>         </td>
      </tr>
      <tr>
         <td><p>CHSM02I</p>         </td>
         <td><p>Recall completed: filename HSM recall in synchronous mode terminated normally.</p>         </td>
      </tr>
      <tr>
         <td><p>CHSM03E</p>         </td>
         <td><p>Recall FAILED: filename A problem occurred with the HSM recall, the volume is still MIGRAT.</p>         </td>
      </tr>
      <tr>
         <td><p>CHSM04I</p>         </td>
         <td><p>HSM Recall (ASY) of: filename. HSM recall in asynchronous mode.</p>         </td>
      </tr>
      <tr>
         <td><p>CHSM05I</p>         </td>
         <td><p>Recall completed: filename HSM recall in asynchronous mode terminated normally.</p>         </td>
      </tr>
      <tr>
         <td><p>SITM02E</p>         </td>
         <td><p>LOAD FAILED FOR: module_name Error loading a module because module was not found in STEPLIB, JOBLIB, etc.</p>         </td>
      </tr>
      <tr>
         <td>CTCP01F         </td>
         <td><p>Unexpected TCP error caused a forced dump. A Transfer CFT restart is required.</p>         </td>
      </tr>
      <tr>
         <td>CTCP02F         </td>
         <td><p>Unexpected TCP error. You must restart the Copilot server.</p>
<p>Configure job scheduling to restart the Copilot server to manage this type of error (it is not automatically restarted by the ARM service).</p>         </td>
      </tr>
   </tbody>
</table>

For a complete list of possible error messages and their meaning, refer to the Troubleshooting topics in the *[*Transfer CFT* <span class="mc-variable axway_variables.Component_Version variable" style="mc-tag-and-class: i;">3.9</span> *Documentation*](http://docs-dev.ecd.axway.int/u/documentation/transfer_cft/3.2.4/webhelp_portal/content/troubleshooting/messages_and_codes/messages_and_error_codes_start_here.htm)*.
