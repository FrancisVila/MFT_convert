{
    "title": "Skipped transformation",
    "linkTitle": "Skipped transformation",
    "weight": "280"
}The Advanced Routing routes are configured:

-   Route 1:
    -   Transformation 1: PGP Decryption where **Require Encryption** is not selected
    -   Route 1: Publish To Account
-   Route 2:
    -   Transformation 1: Line Ending where **Process files based on a filename pattern** is selected
    -   Route 1: Send To Partner

A clear text file is uploaded. Route 1 is triggered. The PGP Decryption transformation is skipped since **Require Encryption** is not selected. The clear text file is published successfully. A file is uploaded that does not match the configured filename pattern. Route 2 is triggered. The Line Ending transformation is skipped since the filename pattern was not recognized and routes the original file to partner transfer site.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">PGP Decryption, Decompression, and Line Ending transformations have optional behaviors that enables them to pass along files that are not eligible for transformation.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Even though transformation steps could be skipped, it is highly recommended that the last step of every route will be a routing step (Send To Partner or Publish To Account). Only routing steps can route the transformed file outside of the sandbox folder.         </td>
      </tr>
</table>

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Route failure](../c_st_route_failure)
-   [Transformed file as the input to the next step](../c_st_transformed_file_as_input_to_next_step)
-   [Routing to multiple transfer sites](../c_st_routing_to_multiple_transfer_sites)
