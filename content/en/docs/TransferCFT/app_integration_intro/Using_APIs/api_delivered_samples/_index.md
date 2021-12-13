{
    "title": "Delivered API templates",
    "linkTitle": "Delivered API templates",
    "weight": "330"
}This topic describes the  {{< TransferCFT/companyname  >}} {{< TransferCFT/componentshortname  >}} API templates, or samples, that are delivered with your {{< TransferCFT/componentshortname  >}} product.  You can use the delivered samples as a template for integrating APIs, as a model, or create your own.

The templates titles are listed in the following tables according to OS and language. In the **Template** column, you can click the template link to view the sample template as a text file.

-   All platform C language templates
-   Specific z/OS templates
-   IBM i templates

## All platform C language templates

The following C language templates are delivered  on UNIX, Windows,  IBM i (OS/400), with the exceptions as noted in the table below.

```

Template

Function

Services

Description

api2xmp1
ipcai2_\*

-   ipcai2_initialize-ipcai2_catalog_open-ipcai2_catalog_selection_new
-   ipcai2_catalog_selection_set-ipcai2_catalog_selection_sortby
-   ipcai2_monitor_info_get
-   ipcai2_catalog_selection_next-ipcai2_catalog_info_get
-   ipcai2_catalog_selection_delete-ipcai2_catalog_close
-   ipcai2_finalize

{{< TransferCFT/componentshortname >}} Catalog API sample program, which lists all catalog content.
\*\* Not delivered on z/OS (iseries).
api2xmp2
ipcai2_\*

-   ipcai2_initialize-ipcai2_catalog_open
-   ipcai2_catalog_selection_new
-   ipcai2_catalog_selection_set
-   ipcai2_catalog_selection_sortby
-   ipcai2_monitor_info_get
-   ipcai2_catalog_selection_next-
-   ipcai2_catalog_info_get
-   ipcai2_catalog_selection_delete
-   ipcai2_catalog_close
-   ipcai2_finalize

{{< TransferCFT/componentshortname >}} Catalog API sample program, which changes all Terminated transfers to Ended.
\*\* Not delivered on z/OS (iseries).
tcftsyn
cftau
COM, SEND, GETXINFO, SWAITCAT, CLOSEAPI
{{< TransferCFT/componentshortname >}} Communication and Catalog API sample program using
a synchronous communication media.
\*\* Not delivered on OS/400 or z/OS (iseries).
```

### File location of the templates

##### UX/Win

The templates are located in the `<Transfer_CFT>\home\distrib\template` directory. For example in Windows, `C:\Axway\Transfer_CFT\home\distrib\template`.

##### IBM i (OS/400)

The templates located in the production library (CFTPROD by default), in the CFTSRC folder.