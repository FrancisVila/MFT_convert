{
    "title": "Rollback upgrade and restore the catalog",
    "linkTitle": "Rollback upgrade and restore catalog",
    "weight": "250"
}## Prerequisites

-   You must have made a backup of the environment prior to the upgrade you are rolling back.
-   Upgraded from {{< TransferCFT/hflongproductname >}} 3.4 or higher to {{< TransferCFT/hflongproductname >}} {{< TransferCFT/releasenumber >}}

## Procedure

1.  Export all catalogs. Base your export procedure on the following example:  
2.  Perform a version rollback as described in [Upgrade version rollback](#Upgrade) below.
3.  Recreate the catalogs and re-import the catalogs. Base your procedure on the following example:  

<span id="Upgrade"></span>

## Upgrade version rollback

The following procedure enables you to rollback to the previous state if you have applied a SP or patch. This is useful if there is an incident during the application of a PTF, or when validating a patch.

1.  Use the A13RBACK
2.  Use the A13RBACK to restore the executable file library, USS Copilot and USS Secure Relay environment. This JCL executes the following three JCLs:
    -   A13RSTOR: Restores the Transfer CFT Load library.
    -   A13UCOPR: Restores the Transfer CFT USS Copilot environment.
    -   A13UXSRR: Restores the Transfer CFT USS Secure Relay environment.
