{
    "title": "Customize MNINIT",
    "linkTitle": "Customize MNINIT",
    "weight": "200"
}The following section is based on implementing an Active/Active High Availability multi-host configuration use case. You should modify accordingly to implement either:

-   Mono host, multi-node architecture
-   Multi host, multi-node architecture

## About MNINIT

The  JCL MNINIT is delivered with the Transfer CFT product. It describes the possible uses cases available for Transfer CFT multi-node configuration. In the following example configuration, you begin by customizing this JCL to transform it from a standalone to a multi-node/host architecture.

In this example you configure two hosts. If your implementation has fewer or more hosts, repeat the host customization steps for each host. Replace the x's and y's with the actual host names in your organization.

-   hostname xxxxxxx -host xx.xxx.xx.xx Host 1
-   hostname yyyyyyy -host yy.yyy.yy.yy Host 2

## Procedure

Edit the MNINIT JCL located in the INSTALL Library as described in the following steps.

> **Note:**
>
> You only perform steps 4 and 8 if you are setting up a multi host multi-node configuration (not for a mono host, multi-node configuration).

<table>
         
         
         
         
   
   <thead>
      <tr>
<th style="text-align: center;" class="HeadE-Column1-Header1" style="font-weight: bold; font-style: normal">Step         </th>
<th class="HeadE-Column1-Header1" style="font-weight: bold; font-style: normal">Task         </th>
<th style="text-align: center;" class="HeadD-Column1-Header1" style="font-weight: bold; font-style: normal">Command or details                                                </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>0         </td>
         <td>Define file size         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>1         </td>
         <td>Activate multi-node         </td>
         <td>PARM=’UCONFSET ID=cft.multi_node.enable,value=yes’         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td><p>Define the number of nodes</p>         </td>
         <td>PARM=’UCONFSET ID=cft.multi_node.nodes,value=2’         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>Add hostname 1         </td>
         <td>PARM=’add_host –hostname xxxxxxx –host xx.xxx.xx.xx’         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td><p>Add hostname 2</p>
<p>(repeat for additional hosts)</p>         </td>
         <td>PARM=’add_host –hostname yyyyyyy –host yy.yyy.yy.yy’         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td><p>Create transfer files for each node</p>         </td>
         <td><p>PARM=’cftinit &amp;EXTPARM’</p>
<p>CFTIN DD DISP=(NEW,PASS),DSN=&amp;&amp;TMPU,</p>
<p>SPACE=(TRK,(1)),DCB=(RECFM=VB,LRECL=1024,DSORG=PS)</p>         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Enable node 0         </td>
         <td>PARM='enable_node -n 0'         </td>
      </tr>
      <tr>
         <td>7         </td>
         <td><p>Enable node 1 (repeat for additional nodes)</p>         </td>
         <td>PARM=’enable_node –n 1’         </td>
      </tr>
      <tr>
         <td>8         </td>
         <td><p>Customize the Copilot server address</p>         </td>
         <td><p>PARM=uconfset</p>
<p>ID=copilot.GENERAL.ServerHost,value=&amp;COPVIPA'</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> JCL variables to customize as described in the table above:

-   EXTPARM: Transfer CFT configuration file
-   COPVIPA: VIPA address for Copilot
-   CFTVIPA: VIPA address for Transfer CFT server

### Additional steps and notes

-   Operator commands are 'local' to a node.
-   The UCONF `sentinel.trktname` parameter defines the Sentinel overflow file. Configure as follows:
    -   Set the `sentinel.trksharedfile` parameter to YES.
    -   You must use an Event Router to process the overflow file.
    -   For a multi-hosts, multi-node implementation, define the logger file using a CF-Structure.
    -   For a mono-host, multi-node implementation, define the logger file using the DASDONLY parameter.

After completing these steps, you have a configured MNINIT, but note that you do not yet have an installed multi-node Transfer CFT.
