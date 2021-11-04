{
    "title": "Transfer CFT maintenance (SMP/E)",
    "linkTitle": "Transfer CFT maintenance (SMP/E)",
    "weight": "230"
}## Receive the SMP/E PTFs

The data set SMPCNTL contains the following model job for receiving SMP/E PTFs.

<table>
   <th>
      <tr>
<th>Member Name         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>$C10RECV         </td>
         <td><p>UNPAX the Maintenance archive package and RECEIVE the Maintenance Pack.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Create a new USS subdirectory to receive the maintenance package. The name and path are defined in the $C10RECV JCL (FROMNTS is the new package subdirectory, and SMPNTS DD PATH designates the path prefix).
2.  Use FTP in binary mode to download the pax.Z archive file of the appropriate PTF to this new package subdirectory. The name of the pax.Z archive file is defined in the $C10RECV JCL (STEP UNPAX: pax command).

## Install the SMP/E PTFs maintenance

Edit the sample jobs that are listed in the following table, modifying as necessary (supply a valid JOB JCL card statement, select and modify the dataset qualifier &HLQ& and the Patch number &NNNN&).

The format of a Transfer CFT PTF SYSMOD ID is <span class="code">P01NNNN</span>. For example, the PTF <span class="code">P010003</span> is comprised of the Patch number 0003, where P01 represents Transfer CFT version 323.

The SMPCNTL data set contains the following model job for the SMP/E PTFs maintenance.

Submit the job described in the table below.

<table>
   <th>
      <tr>
<th>Member Name         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>$C30PAPP         </td>
         <td>Performs an APPLY (with the CHECK operand) to install the PTFs in the target zone and libraries.         </td>
      </tr>
   </tbody>
</table>

If the $C30PAPP return code is a zero or a 4, edit $C30PAPP, remove the CHECK command, and resubmit the job.

The APPLY CHECK and APPLY jobs may end with a RC=4, and return the following warning messages:

> GIM38201W THERE IS A MODID ERROR FOR DATA ENTRY CSDNEW IN SYSMOD pid.
>
> GIM31901I SYSMOD pid DOES NOT SPECIFY pre-pid ON THE PRE OR SUP OPERAND.

These messages are normal; you can ignore them.

### Additional SMP/E sample jobs

The following table lists additional sample jobs.

<table>
   <th>
      <tr>
<th>Member Name         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>$C30PREM         </td>
         <td>Performs a RESTORE (to remove) for the PTF elements from the target zone.         </td>
      </tr>
      <tr>
         <td>$C60PACC         </td>
         <td>Performs an ACCEPT (with the CHECK operand) of the PTFs in the distribution zone and libraries.         </td>
      </tr>
   </tbody>
</table>

## Update the Transfer CFT instance with the maintenance identifier

Edit the sample jobs listed in the table below, modifying as necessary.

The Transfer CFT instance data set INSTALL contains the following model jobs for Transfer CFT SMP/E maintenance.  

<table>
   <th>
      <tr>
<th>Member Name         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>A13SMPE</p>         </td>
         <td><p>Applies maintenance to the Transfer CFT product instance.</p>         </td>
      </tr>
      <tr>
         <td><p>A13UCOP</p>         </td>
         <td><p>Applies maintenance to Copilot.</p>         </td>
      </tr>
      <tr>
         <td><p>A13UXSR</p>         </td>
         <td><p>Applies maintenance to the Secure Relay Master Agent.</p>         </td>
      </tr>
   </tbody>
</table>