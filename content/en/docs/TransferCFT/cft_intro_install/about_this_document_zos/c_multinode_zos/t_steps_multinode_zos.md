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

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="HeadE-Column1-Header1" style="font-weight: bold; font-style: italic">Step         </th>
<th style="text-align: left;" class="HeadD-Column1-Header1" style="font-weight: bold; font-style: italic">Task         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Customize <a href="../t_vipa_multinode_zos">VIPA</a> programs and execute the customized members, including the following tasks.</p>
<p>For each LPAR:</p>
<ul>
<li>Enable the port sharing (to execute on each LPAR) - Share Listening port: (protocol port (e.g. PESIT and port PESIT SSL))</li>
<li>Identified all ports (protocol ports) to share on the LPAR</li>
<li>Define the LPAR dynamic XCF address (DYNAMICXCF)</li>
</ul>
<p>On the first LPAR</p>
<ul>
<li>Define the cluster address (VIPA)</li>
<li>Define the port balancing between the LPAR</li>
</ul>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>Customize <a href="../t_mninit_multinode_zos">MNINIT</a>.         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td><p><a href="../t_submit_mninit_zos">Execute</a> the customized MNINIT.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Depending on the type of installation you are performing, a Transfer CFT CATALOG file may be created during installation. Additionally, files having the format CATALOG.Nxx (where Nxx represents the node identifier) are created by the MNINIT JCL. The CATALOG file without a suffix is not used, so you can delete this file (the one without the .Nxx suffix). We recommend that you comment the //CFTCAT DD cards in the JCL and procedures. For example, comment the cards in the PCFTUTIL procedure and CFTINC member.
