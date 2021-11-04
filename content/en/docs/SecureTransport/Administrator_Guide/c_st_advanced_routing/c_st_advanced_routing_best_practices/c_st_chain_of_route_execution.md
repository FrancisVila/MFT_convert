{
    "title": "Chain of route execution",
    "linkTitle": "Chain of route execution",
    "weight": "250"
}The following <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> steps are configured:

-   Route 1:
    -   Transformation 1: Compression
    -   Routing 1: Publish To Account
-   Route 2
    -   Transformation 1: Compression
    -   Transformation 2: PGP Encryption
    -   Routing 1: Send To Partner

The uploaded file triggers Route 1 and Route 2 in the specified order. The execution of Route 1 compresses the original file and routes the transformed (compressed) file to an account for publishing. The execution of Route 2 compresses the original file, PGP encrypts the compressed file, and routes the transformed (compressed and PGP encrypted) file to a partner transfer site.

Each route works with a copy of the original file. During the route execution the copy of the original file is passed from step to step. See <a href="#" class="MCXref xref">Transformed file as the input to the next step</a> for more information.

> **Note:**
>
> Execution of the routes is sequential, not simultaneous.

> **Note:**
>
> It is highly recommended that the last step of every route is a routing step (Send To Partner or Publish To Account). The reason is that only routing steps can move (send or publish) the transformed file or files outside of the sandbox folder. Having only transformation steps properly transforms the file in the sandbox folder, but when the route terminates the transformed files is deleted along with the sandbox folder.

**Related topics:**

-   <a href="../c_st_inherited_versus_specific" class="MCXref xref">Inherited settings versus Specific settings</a>
-   <a href="../c_st_skipped_transformation" class="MCXref xref">Skipped transformation</a>
-   <a href="../c_st_transformation_on_multiple_files" class="MCXref xref">Transformation on multiple files</a>
-   <a href="../c_st_route_failure" class="MCXref xref">Route failure</a>
-   <a href="#" class="MCXref xref">Transformed file as the input to the next step</a>
-   <a href="../c_st_routing_to_multiple_transfer_sites" class="MCXref xref">Routing to multiple transfer sites</a>