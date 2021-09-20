{
    "title": "Transformed file as the input to the next step",
    "linkTitle": "Transformed file as the input to the next step",
    "weight": "310"
}The following Advanced Routing routes are configured:

-   Route 1:
    -   Transformation 1: Line Ending where **Rename output files** is not selected
    -   Routing 1: Publish To Account

A text file is uploaded. Route 1 is triggered. Transformation 1 performs a Line Ending transformation over the file. The name of the file is not modified because **Rename output files** is not selected and the Line Ending transformation does not automatically modify the file name. The transformed file is the input for the next step, that's why the transformed file is routed to the Publish To Account destination.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When <strong>Rename output files</strong> is selected, the transformed file is renamed in the sandbox folder only. The original file in the subscription folder is not transformed.         </td>
      </tr>
</table>

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Route failure](../c_st_route_failure)
-   [Routing to multiple transfer sites](../c_st_routing_to_multiple_transfer_sites)