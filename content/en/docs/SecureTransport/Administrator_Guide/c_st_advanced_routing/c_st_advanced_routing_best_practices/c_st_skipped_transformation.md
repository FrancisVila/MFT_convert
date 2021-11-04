{
    "title": "Skipped transformation",
    "linkTitle": "Skipped transformation",
    "weight": "270"
}The <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> routes are configured:

-   Route 1:
    -   Transformation 1: PGP Decryption where **Require Encryption** is not selected
    -   Route 1: Publish To Account
-   Route 2:
    -   Transformation 1: Line Ending where **Process files based on a filename pattern** is selected
    -   Route 1: Send To Partner

A clear text file is uploaded. Route 1 is triggered. The PGP Decryption transformation is skipped since **Require Encryption** is not selected. The clear text file is published successfully. A file is uploaded that does not match the configured filename pattern. Route 2 is triggered. The Line Ending transformation is skipped since the filename pattern was not recognized and routes the original file to partner transfer site.

> **Note:**
>
> PGP Decryption, Decompression, and Line Ending transformations have optional behaviors that enables them to pass along files that are not eligible for transformation.

> **Note:**
>
> Even though transformation steps could be skipped, it is highly recommended that the last step of every route will be a routing step (Send To Partner or Publish To Account). Only routing steps can route the transformed file outside of the sandbox folder.

**Related topics:**

-   <a href="../c_st_chain_of_route_execution" class="MCXref xref">Chain of route execution</a>
-   <a href="../c_st_inherited_versus_specific" class="MCXref xref">Inherited settings versus Specific settings</a>
-   <a href="../c_st_transformation_on_multiple_files" class="MCXref xref">Transformation on multiple files</a>
-   <a href="../c_st_route_failure" class="MCXref xref">Route failure</a>
-   <a href="#" class="MCXref xref">Transformed file as the input to the next step</a>
-   <a href="../c_st_routing_to_multiple_transfer_sites" class="MCXref xref">Routing to multiple transfer sites</a>
