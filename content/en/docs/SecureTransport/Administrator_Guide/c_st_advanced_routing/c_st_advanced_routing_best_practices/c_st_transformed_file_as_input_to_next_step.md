{
    "title": "Transformed file as the input to the next step",
    "linkTitle": "Transformed file as the input to the next step",
    "weight": "300"
}The following {{< SecureTransport/advancedrouting  >}} routes are configured:

-   Route 1:
    -   Transformation 1: Line Ending where **Rename output files** is not selected
    -   Routing 1: Publish To Account

A text file is uploaded. Route 1 is triggered. Transformation 1 performs a Line Ending transformation over the file. The name of the file is not modified because **Rename output files** is not selected and the Line Ending transformation does not automatically modify the file name. The transformed file is the input for the next step, that's why the transformed file is routed to the Publish To Account destination.

> **Note:**
>
> When Rename output files is selected, the transformed file is renamed in the sandbox folder only. The original file in the subscription folder is not transformed.

**Related topics:**

-   <a href="../c_st_chain_of_route_execution" class="MCXref xref">Chain of route execution</a>
-   <a href="../c_st_inherited_versus_specific" class="MCXref xref">Inherited settings versus Specific settings</a>
-   <a href="../c_st_skipped_transformation" class="MCXref xref">Skipped transformation</a>
-   <a href="../c_st_transformation_on_multiple_files" class="MCXref xref">Transformation on multiple files</a>
-   <a href="../c_st_route_failure" class="MCXref xref">Route failure</a>
-   <a href="../c_st_routing_to_multiple_transfer_sites" class="MCXref xref">Routing to multiple transfer sites</a>
