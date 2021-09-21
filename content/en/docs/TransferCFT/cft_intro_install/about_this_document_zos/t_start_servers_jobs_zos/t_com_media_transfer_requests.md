{
    "title": "Communication media JCL for transfer requests",
    "linkTitle": "Communication media JCL for transfer requests",
    "weight": "190"
}This section presents JCL examples that you can use to create the JOBs to perform transfer requests. All of these JCLs are located in the target.SAMPLE library. The following examples for send procedures are described below:

-   [CFTSEND for a JCL requesting a transfer](#cftsend%20for%20a%20jcl%20requesting%20a%20transfer)
-   [CFTSENDS synchronous transfer request API](#cftsends%20synchronous%20transfer%20request%20api)

### <span id="CFTSEND for a JCL requesting a transfer"></span>CFTSEND for a JCL requesting a transfer

The following JOB is an example of a JCL for requesting a file transfer. Using the CFTSEND example, you can create JOBs that satisfy your operating requirements.

Example

<table cellspacing="0">
   <col/>
      <tr>
         <td>
            <p>CFTSEND</p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
            <p>//LIB    JCLLIB ORDER=(cftv2.INSTALL)
                    </p>
            <p>//      INCLUDE MEMBER=cftenv
                    </p>
            <p>//CFTSEND  EXEC PCFTUTIL,PARM='/1=&amp;CFTENV',</p>
            <p>//         QUAL=&amp;CFTENV,OUT=&amp;OUT</p>
            <p>//CFTIN    DD *</p>
            <p>   SEND PART=LOOP,IDF=SAMPLE,</p>
            <p>           FNAME=%_ARGV1%.FTEST</p>
            <p>/*</p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
            <p>The parameters shown in bold are substituted during the customization phase.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTUTIL parameters:</p>
            <p>/1= Transfer CFT prefix environment [%_ARGV1%]</p>
            <p>This JCL contains others templates, such as:</p>
            <p>•	Transfer a pds member.</p>
            <p>•	Transfer files from a files list.</p>
            <p>•	Transfer a file using broadcast list.</p>
            <p>•	Generate and transfer a files list.</p>
            <p>•	Transfer a group files</p>
            <p>•	Transfer a group files using REGEX filter.</p>
         </td>
      </tr>
</table>

### <span id="CFTSENDS synchronous transfer request API"></span>CFTSENDS synchronous transfer request API 

Example

<table cellspacing="0">
   <col/>
      <tr>
         <td>
            <p>CFTSENDS</p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
            <p>//LIB    JCLLIB ORDER=(<span>cftv2</span>.INSTALL)</p>
            <p>//      INCLUDE MEMBER=<span>cftenv</span></p>
            <p>//CFTSENDS EXEC PCFTUTIL,PARM='/1=&amp;CFTENV',</p>
            <p>//         QUAL=&amp;CFTENV,OUT=&amp;OUT</p>
            <p>/* ----  WITH INDIRECT CONFIGURATION FILE ---- */</p>
            <p> </p>
            <p>   CONFIG TYPE=COM,FNAME=$CFTTCP </p>
            <p> </p>
            <p>   SEND PART=LOOP,IDF=SAMPLE,</p>
            <p>      FNAME=%_ARGV1%.FTEST</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>The parameters shown in bold are substituted during the customization phase</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTUTIL parameters:</p>
            <p>/1= Transfer CFT prefix environment [%_ARGV1%]</p>
         </td>
      </tr>
</table>

### <span id="CFTSENDM request deposit in XMEM mailbox"></span>

Related topics

-   [Starting and stopping the Transfer CFT servers JOBs](..//transfercft/cft_intro_install/about_this_document_zos/t_start_servers_jobs_zos)
