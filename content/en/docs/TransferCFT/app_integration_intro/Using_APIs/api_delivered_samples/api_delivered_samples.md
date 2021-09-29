{
    "title": "Delivered API templates",
    "linkTitle": "Delivered API templates",
    "weight": "360"
}# Delivered API templates



This topic describes the <span>Axway</span> <span>Transfer CFT</span> API templates, or samples, that are delivered with your <span>Transfer CFT</span> product. You can use the delivered samples as a template for integrating APIs, as a model, or create your own.



The templates titles are listed in the following tables according to OS and language. In the **Template** column, you can click the template link to view the sample template as a text file.



-   All platform C language templates

-   Specific z/OS templates

-   IBM i templates



## All platform C language templates



The following C language templates are delivered on UNIX, Windows, IBM i (OS/400), with the exceptions as noted in the table below.



<table data-cellspacing="0">
<thead>
<tr>
<th>Template</th>
<th>Function</th>
<th><p>Services</p></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>api2xmp1</td>
<td>ipcai2_*</td>
<td><ul>
<li>ipcai2_initialize-ipcai2_catalog_open-ipcai2_catalog_selection_new</li>
<li>ipcai2_catalog_selection_set-ipcai2_catalog_selection_sortby</li>
<li>ipcai2_monitor_info_get</li>
<li>ipcai2_catalog_selection_next-ipcai2_catalog_info_get</li>
<li>ipcai2_catalog_selection_delete-ipcai2_catalog_close</li>
<li>ipcai2_finalize</li>
</ul></td>
<td><p><span>Transfer CFT</span> Catalog API sample program, which lists all catalog content.</p>
<p>** Not delivered on z/OS (iseries).</p></td>
</tr>
<tr>
<td>api2xmp2</td>
<td>ipcai2_*</td>
<td><ul>
<li>ipcai2_initialize-ipcai2_catalog_open</li>
<li>ipcai2_catalog_selection_new</li>
<li>ipcai2_catalog_selection_set</li>
<li>ipcai2_catalog_selection_sortby</li>
<li>ipcai2_monitor_info_get</li>
<li>ipcai2_catalog_selection_next-</li>
<li>ipcai2_catalog_info_get</li>
<li>ipcai2_catalog_selection_delete</li>
<li>ipcai2_catalog_close</li>
<li>ipcai2_finalize</li>
</ul></td>
<td><p><span>Transfer CFT</span> Catalog API sample program, which changes all Terminated transfers to Ended.</p>
<p>** Not delivered on z/OS (iseries).</p></td>
</tr>
<tr>
<td>tcftsyn</td>
<td>cftau</td>
<td>COM, SEND, GETXINFO, SWAITCAT, CLOSEAPI</td>
<td><p><span>Transfer CFT</span> Communication and Catalog API sample program using

a synchronous communication media.</p>
<p>** Not delivered on OS/400 or z/OS (iseries).</p></td>
</tr>
</tbody>
</table>



### File location of the templates



##### UX/Win



The templates are located in the `<transfer_cft>\home\distrib\template` directory. For example in Windows, `C:\Axway\Transfer_CFT\home\distrib\template`.



##### IBM i (OS/400)



The templates located in the production library (CFTPROD by default), in the CFTSRC folder.

</transfer_cft>