{
    "title": "Chain of route execution",
    "linkTitle": "Chain of route execution",
    "weight": "260"
}The following Advanced Routing steps are configured:

-   Route 1:
    -   Transformation 1: Compression
    -   Routing 1: Publish To Account
-   Route 2
    -   Transformation 1: Compression
    -   Transformation 2: PGP Encryption
    -   Routing 1: Send To Partner

The uploaded file triggers Route 1 and Route 2 in the specified order. The execution of Route 1 compresses the original file and routes the transformed (compressed) file to an account for publishing. The execution of Route 2 compresses the original file, PGP encrypts the compressed file, and routes the transformed (compressed and PGP encrypted) file to a partner transfer site.

Each route works with a copy of the original file. During the route execution the copy of the original file is passed from step to step. See [Transformed file as the input to the next step](../c_st_transformed_file_as_input_to_next_step) for more information.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Execution of the routes is sequential, not simultaneous.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">It is highly recommended that the last step of every route is a routing step (Send To Partner or Publish To Account). The reason is that only routing steps can move (send or publish) the transformed file or files outside of the sandbox folder. Having only transformation steps properly transforms the file in the sandbox folder, but when the route terminates the transformed files is deleted along with the sandbox folder.         </td>
      </tr>
</table>

**Related topics:**

-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Route failure](../c_st_route_failure)
-   [Transformed file as the input to the next step](../c_st_transformed_file_as_input_to_next_step)
-   [Routing to multiple transfer sites](../c_st_routing_to_multiple_transfer_sites)
