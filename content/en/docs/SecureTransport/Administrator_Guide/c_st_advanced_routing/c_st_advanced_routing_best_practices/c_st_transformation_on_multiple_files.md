{
    "title": "Transformation on multiple files",
    "linkTitle": "Transformation on multiple files",
    "weight": "290"
}The following Advanced Routing routes are configured:

-   Route 1:
    -   Transformation 1: Decompress
    -   Transformation 2: PGP Decryption where **Require Encryption** is not selected
    -   Routing 1: Publish To Account
-   Route 2:
    -   Routing 2: Send To Partner

A compressed file, containing both PGP encrypted and clean files, is uploaded. Route 1 is triggered. Transformation 1 decompresses the file and multiple files are passed on to Transformation 2. The PGP encrypted files are decrypted and the clean files are left as they are. The PGP decrypted and clean files are routed to the Publish to Account destination. Route 2 is triggered and originally uploaded compressed file is pushed to the partner transfer site.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If <strong>Proceed with route execution on step failure</strong> is not selected for the PGP Decryption (Route 1, Transformation 2) and PGP Decryption fails on any file, the whole transformation chain is considered failed. Any further operations withing the route are not executed. Any successfully transformed files (until the failure point) are left on the file system. Any files that are in the sandbox folder are lost. Only files published by Send To Partner or Publish To Account route steps are available.         </td>
      </tr>
</table>

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Route failure](../c_st_route_failure)
-   [Transformed file as the input to the next step](../c_st_transformed_file_as_input_to_next_step)
-   [Routing to multiple transfer sites](../c_st_routing_to_multiple_transfer_sites)
