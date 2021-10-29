{
    "title": "Troubleshoot the UCONFRUN dataset",
    "linkTitle": "Troubleshoot the UCONFRUN dataset",
    "weight": "230"
}CFTMAIN hangs while it waits for the UCONFRUN dataset to be freed

Messages

IEF861I FOLLOWING RESERVED DATA SET NAMES UNAVAILABLE TO CFTMAIN

IEF863I DSN = CFAUTO.AXWAY.D322.CFT.UCONFRUN CFTMAIN RC = 04

IEF099I JOB CFTMAIN WAITING FOR DATA SETS

Cause

When CFTMAIN is started, the UCONFRUN dataset is exclusively held by CFTMAIN and Copilot waits for the dataset to be freed.

-or-

If Copilot is started, the UCONFRUN dataset is held exclusively by Copilot.

Resolution

This issue is related to the use of at least one of the z/OS storage management tools, such as the IBM Tivoli Allocation Optimizer. The easiest way to disable Tivoli Allocation Optimizer is to add the bypass DDNAME in the JCL (COPRUN and CFTMAIN). Doing so bypasses the Tivoli Allocation Optimizer for all of the datasets accessed by this step.

The ddname is AOBYPASS and the format of the DD card is: //AOBYPASS DD DUMMY

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>//* ---------------------------------------------------</p>
            <p>//* Turning off Fault Analyzer with a JCL switch (IDIOFF)</p>
            <p>//* and/or other debuging products.</p>
            <p>//* uncomment the following statement(s).</p>
            <p>//* ---------------------------------------------------</p>
            <p>//*IDIOFF DD DUMMY IBM FAULT ANALYZER OFF</p>
            <p>//*</p>
            <p>//*ABNLIGNR DD DUMMY ABEND-AID OFF</p>
            <p>//*ESPYIBM DD DUMMY EYE-SPY OFF</p>
            <p>//*CAOESTOP DD DUMMY CA-OPT II &amp; CA-SYMDUMP OFF</p>
            <p>//*DMBENAN DD DUMMY TURN OFF DUMPMASTER</p>
            <p>//*PSPOFF DD DUMMY TURN OFF SOFTWORKS PERFORMANCE ESSENTIAL</p>
            <p>//*</p>
            <p>//* ---------------------------------------------------</p>
            <p>//* Turn off PDSMAN</p>
            <p>//* uncomment the following statement.</p>
            <p>//* ---------------------------------------------------</p>
            <p>//*FCOPYOFF DD DUMMY</p>
            <p>//*</p>
            <p>//*PROIGN DD DUMMY To bypass Stop-X37</p>
            <p>//*AOBYPASS DD DUMMY To bypass Tivoli Allocation Optimizer</p>
            <p>//*</p>         </td>
      </tr>
   </tbody>
</table>
