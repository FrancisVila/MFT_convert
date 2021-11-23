{
    "title": "Routing to multiple transfer sites",
    "linkTitle": "Routing to multiple transfer sites",
    "weight": "310"
}The following {{< SecureTransport/advancedrouting  >}} route is configured:

-   Route 1:
    -   Routing 1: Send To Partner where multiple transfer sites belonging to a single account are selected

A file is uploaded. Route 1 is triggered. The file is sent to all transfer sites. If any of the transfers temporarily fail, only the failed transfers are automatically retried. There are no retries if the transfer permanently fails.

> **Note:**
>
> When routing to multiple transfer sites, it is recommended the Route file as be set using an Expression Language expression, containing ${timestamp} or ${random()} so it's transformed to an unique value for each of the transfers.

> **Note:**
>
> Unlike automatic retries when an ordinary subscription folder is used to send files directly to a transfer site, with the Advanced Routing feature the administrator is not able to control the automatic retries using Cancel or Resubmit buttons.

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Route failure](../c_st_route_failure)
-   [Transformed file as the input to the next step]()
