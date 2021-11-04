{
    "title": "Increase the catalog size",
    "linkTitle": "Increase the catalog size",
    "weight": "290"
}You can increase the catalog size either dynamically or statically as described below.

## Dynamic mode

Use the JCL INSTALL(CFTCATDY). There is no need to stop Transfer CFT or Copilot prior to performing this action. Check the recommendations provided in the CFTCATDY JCL.

Modify the <span class="code">recnb </span>parameter (the new number of records), in the <span class="code">reconfig </span>command, to the new target catalog size.

For more general information on expanding the catalog, you can refer to the section *Housekeeping for catalog and output files* in the *Transfer CFT User Guide.*

## Static mode

1.  Stop Transfer CFT and Copilot if not already done.
2.  Save the CATALOG file.
3.  Modify the JCL INSTALL(CFTCATAL):

-   RECNB is the new CATALOG size in number of records
-   TMPSPACE 'CYL,(50,10)' is the size of the temporary file

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If the Transfer CFT HABILITATION is activated:         </td>
      </tr>
   </tbody>
</table>

-   In the CFTFILE TYPE=CAT, MODE=CREATE command, add the HABFNAME parameter with the SECINI file (created by the JCL H86SAFCR).

-   In the SISYN : CREATE.CFTIN, comment the sequence code (1), and uncomment the sequence code (3) as follows:  



        //CREATE.CFTIN DD *,DLM='XX'

        /* CREATE CATALOG */

        /* (1) CATALOG (No Transfer CFT HABILITATION) */

        /* CFTFILE MODE  =  CREATE,TYPE=CAT, 

                      
                FNAME =  %_ARGV3%%%%_ARGV1%,            
                
        RECNB =  %_ARGV2%         */


        /* or (3) CATALOG (when Transfer CFT HABILITATION is active) */
                                                                    
           
          CFTFILE MODE     = CREATE,TYPE=CAT,                         
                   

        FNAME    = %_ARGV3%%%%_ARGV1%,                      
                   
        HABFNAME = %_ARGV4%,                                
                   
        RECNB    = %_ARGV2%                                 
         

        XX                                                    

1.  Start the INSTALL(CFTCATAL).

### Static mode for multi-node

If you are using a multi-node architecture, use this static mode procedure.

1.  Stop all <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> nodes and all Copilot servers if not already done.
2.  Save the CATALOG files.
3.  Modify the JCL INSTALL(CFTCATAL):

-   RECNB is the new CATALOG size in number of records
-   TMPSPACE 'CYL,(50,10)' is the size of the temporary file
-   NODE is the node ID (ex NODE=’0’)
-   In the SISYN : CREATE.CFTIN, comment the sequence code (1), and uncomment the sequence code (2) as follows:

<!-- -->



    //CREATE.CFTIN DD *,DLM='XX'
    /* CREATE CATALOG */
    /* (1) CATALOG (No Transfer CFT HABILITATION) */
    /* CFTFILE MODE  =  CREATE,TYPE=CAT,

    FNAME =  %_ARGV3%%%%_ARGV1%,
    RECNB =  %_ARGV2%         */

    /* or (2) CATALOG MULTI-NODES (No Transfer CFT HABILITATION) */
    CFTFILE MODE  =  CREATE,TYPE=CAT,

    FNAME =  %_ARGV3%%%%_ARGV1%,
    NODE  =  %_ARGV5%,
    RECNB =  %_ARGV2%

1.  Submit this procedure as many times as there are nodes.
