{
    "title": "Routing to multiple transfer sites",
    "linkTitle": "Routing to multiple transfer sites",
    "weight": "320"
}The following Advanced Routing route is configured:

-   Route 1:
    -   Routing 1: Send To Partner where multiple transfer sites belonging to a single account are selected

A file is uploaded. Route 1 is triggered. The file is sent to all transfer sites. If any of the transfers temporarily fail, only the failed transfers are automatically retried. There are no retries if the transfer permanently fails.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When routing to multiple transfer sites, it is recommended the <strong>Route file as</strong> be set using an Expression Language expression, containing <code>${timestamp}</code> or <code>${random()}</code> so it's  transformed to an unique value for each of the transfers.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Unlike automatic retries when an ordinary subscription folder is used to send files directly to a transfer site, with the <span>Advanced Routing</span> feature the administrator is not able to control the automatic retries using <em>Cancel</em> or <em>Resubmit</em> buttons.         </td>
      </tr>
</table>

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Route failure](../c_st_route_failure)
-   [Transformed file as the input to the next step](../c_st_transformed_file_as_input_to_next_step)
