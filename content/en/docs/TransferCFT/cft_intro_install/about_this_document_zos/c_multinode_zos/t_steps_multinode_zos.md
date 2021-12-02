{
    "title": "Multi-node installation overview",
    "linkTitle": "Procedure overview ",
    "weight": "180"
}**Installing Transfer CFT**

If you have not done so already, begin by performing a standard Transfer CFT z/OS installation. See the [Transfer CFT {{< TransferCFT/componentversion  >}} z/OS Installation Overview](../../c_about_zos) for information on how to get started. You can set up Transfer CFT multi-node either with multiple nodes and hosts, or multi-node mono-host. This documentation primarily focuses on the multi-node, multi-host scenario.

If you create a multi-node, mulit-host installation, and the USS Environment for Transfer CFT is not shared between all the hosts, you must install a separate USS Environment on each host. To do this, execute the member COPA010, in the INSTALL library, on each host that is not shared.

If an APF mode is defined on one of the hosts, then you must configure the APF mode for every host.

**After installing**

After installing Transfer CFT, you must customize this Transfer CFT from a standard standalone installation to a multi-node enabled Transfer CFT. The following sections, which describe how to customize MNINIT and the VIPA programs, are based on a multi-node and multi-host example implementation. If your organization requires a mono-host installation, you can modify the example procedure accordingly.

## Steps

The process consists of customizing the z/OS specific programs and members, checking the Transfer CFT configuration, and then executing the customized programs.

> **Note:**
>
> To execute the multi-node customization you require administrator rights.

> **Note:**
>
> Depending on the type of installation you are performing, a Transfer CFT CATALOG file may be created during installation. Additionally, files having the format CATALOG.Nxx (where Nxx represents the node identifier) are created by the MNINIT JCL. The CATALOG file without a suffix is not used, so you can delete this file (the one without the .Nxx suffix). We recommend that you comment the //CFTCAT DD cards in the JCL and procedures. For example, comment the cards in the PCFTUTIL procedure and CFTINC member.
