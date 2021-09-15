{
    "title": "Inherited settings versus Specific settings",
    "linkTitle": "Inherited settings versus Specific settings",
    "weight": "270"
}The following Advanced Routing steps are configured:

-   Inherited Settings:
    -   Route 1:
        -   Transformation 1: Compression
        -   Routing 1: Publish To Account
-   Specific Settings:
    -   Route 2:
        -   Transformation 1: PGP Encryption
        -   Routing 1: Send To Partner

The uploaded file triggers Route 1 (Inherited Settings) and Route 2 (Specific Settings). The Inherited Settings compress the original file and routes the transformed (compress) file to an account for publishing. The Specific Settings PGP encrypt the original file and routes the transformed (PGP encrypted) file to a partner transfer site.

The Inherited Settings have a higher priority than the Specific Settings.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">It is highly recommended that the last step of every route is a routing step (Send To Partner or Publish To Account). The reason is that only routing steps can move (send or publish) the transformed file or files outside of the sandbox folder. Having only transformation steps properly transforms the file in the sandbox folder, but when the route terminates the transformed files are deleted along with the sandbox folder.         </td>
      </tr>
</table>

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Route failure](../c_st_route_failure)
-   [Transformed file as the input to the next step](../c_st_transformed_file_as_input_to_next_step)
-   [Routing to multiple transfer sites](../c_st_routing_to_multiple_transfer_sites)
