{
    "title": "Route failure",
    "linkTitle": "Route failure",
    "weight": "290"
}The following {{< SecureTransport/advancedrouting  >}} routes are configured:

-   Route 1:
    -   Transformation 1: Decompress
    -   Transformation 2: PGP Decryption where **Require Encryption** is selected and **Proceed with route execution on step failure** is not selected
    -   Routing 1: Publish To Account
-   Route 2:
    -   Routing 1: Send To Partner

A compressed file, containing both PGP encrypted and clean files, is uploaded. Route 1 is triggered. Transformation 1 decompresses the file and multiple files are passed on to Transformation 2. The PGP encrypted files are decrypted but since some of the files are in plain text the step execution fails (because **Require Encryption** is selected). Since **Proceed with route execution on step failure** is not selected the whole transformation chain is considered failed and any further processing within Route 1 is not executed, which means that Routing 1 (Publish To Account) is not executed (even though there are successfully decrypted files). Although other routes (if any) defined in the chain are executed. That's why Route 2 is triggered and the originally uploaded compressed file is pushed to the partner site.

> **Note:**
>
> By default all routing steps (Send To Partner and Publish To Account) are configured to be processed even though one or more files have failed to be sent or published, though all transformation steps (PGP Encryption, PGP Decryption, and so forth) are configured to fail even if only one file transformation has failed.

> **Note:**
>
> If route execution fails, any successfully transformed files (until the failure point) are left in the sandbox folder. Any files that are in the sandbox folder are lost. Only files published by the Send To Partner or Publish To Account route steps are available.

**Related topics:**

-   [Chain of route execution](../c_st_chain_of_route_execution)
-   [Inherited settings versus Specific settings](../c_st_inherited_versus_specific)
-   [Skipped transformation](../c_st_skipped_transformation)
-   [Transformation on multiple files](../c_st_transformation_on_multiple_files)
-   [Transformed file as the input to the next step]()
-   [Routing to multiple transfer sites](../c_st_routing_to_multiple_transfer_sites)
