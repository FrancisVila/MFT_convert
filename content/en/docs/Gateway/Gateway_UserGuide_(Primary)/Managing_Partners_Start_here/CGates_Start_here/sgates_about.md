{
    "title": "About SGates",
    "linkTitle": "About SGates",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[Connection control using SGates](#connection_control_using_sgates)

[SGates versus CGates](#sgates_v_cgates)

[SGateGroups versus CGateGroups](#sgategroups_v_cgategroups)

[When to use SGates](#when_to_use_sgates)

<span id="connection_control_using_sgates"></span>

## Connection control using SGates

Gateway now supports the use of <span style="font-style: italic;">Super CGates</span> (SGates) that offer a higher capacity than the standard CGates.

The following table summarizes the differences between CGates and SGates.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">          </th>
<th class="HeadE-Column1-Header1"><p>CGates</p>         </th>
<th class="HeadD-Column1-Header1"><p>SGates</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Total number of supported CGates or SGates</strong></p>         </td>
         <td><p>Several thousand</p>         </td>
         <td><p>Several hundred thousand</p>         </td>
      </tr>
      <tr>
         <td><p><strong>VFD rights</strong></p>         </td>
         <td><p>Maximum: 30</p>         </td>
         <td><p>Maximum: 300</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Selection using</strong> <span style="font-style: italic;font-weight: bold;">Best matching</span> <strong>principle</strong></p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>No</p>
<p>Use an exit to force the selection.</p>         </td>
      </tr>
   </tbody>
</table>

These SGates are not available by default. If you want to use SGates, you must modify a configuration file. If you have existing CGates, you can upgrade them to SGates if desired.

<span id="sgates_v_cgates"></span>

## SGates versus CGates

The SGate object can be used instead of a CGate object in the particular case where SGate names are unambiguously selected by the Exit PCNX user routine. The <span style="font-style: italic;">best matching</span> facility is not supported with SGates. Only the <span class="code">cgate\_forced</span> mechanism from Exit PCNX is currently supported.

Bearing in mind this restriction, the new SGate object can overcome the following limitations of the CGate object implementation.

### Maximum number of rights per SGate

The VFD rights of each SGate are packed into a list of 16 KB records containing up to 36 rights each. Up to 65535 of these 16 KB records can exist for each SGate.

Although an SGate with a very large number of rights is possible, it is not recommended to define more than 300 rights for any SGate (approx. 10 x 16 KB records), since such large objects can very significantly increase the memory footprint of Gateway processes and disk I/O load.

For the same reason, it is advisable to ensure that the average number of rights per SGate is not significantly greater than 36 (1 x 16 KB record per SGate). In other words, the number of SGates using a list of VFD rights larger than 36 entries must be small compared to those using fewer than 36 VFD rights.

### Maximum number of SGates

The fixed part of each SGate (SGate with no VFD rights) is stored as a record of about 5 KB in size. These records are gathered in a single data file that can be considered as not being limited in size given current technology (2^47 bytes).

The SGate records are retrieved by name through a two-level hash index of 512 x 512 = 262 144 entries.

Although a very large SGate file is technically possible, it is advisable, for I/O performance considerations, to avoid too many collisions in the hash index. For example, a 200 000 SGate file will normally encounter no collisions in the hash index, but a 700 000 SGate file will show about two such collisions on average.

### Scalability

Unlike the CGate object management that is implemented through the SUP process (the central process of Gateway), the SGate object management is based on concurrent access to the SGate data file and VFD rights data file with proper synchronization using POSIX locking system services.

The VFD rights list is no longer read by the SUP process and passed to File Transfer process through IPC as for CGates, but read in parallel by all File Transfer processes.

This new way of concurrently handling VFD rights list accesses for SGates can also improve scalability of SGates against CGates.

<span id="sgategroups_v_cgategroups"></span>

## SGateGroups versus CGateGroups

The SGateGroup object is the replacement of the CGateGroup object when SGates are used instead of CGates.

The same limitations that apply to SGates also apply to SGateGroups.

<span id="when_to_use_sgates"></span>

## When to use SGates

As the current SGate implementation offers only a subset of CGate related services, it is not recommended to use SGates if the corresponding CGates meet the performance requirements of your application.

Basically, using fewer than 1000 CGates should not significantly impair Gateway performance for most applications.

Depending on the machine on which Gateway is running, and the workload of your application, performance problems can arise when the number of CGates reaches a value between 1000 and 10 000.

Switching to SGates is likely to fix the performance issue in such situations.

Related topics

[Working with SGates](../sgates_working_with)

[Working with CGates (command line)](../working_with_cgates_cli)

[Working with CGateGroups (command line)](../working_with_cgates_cli/working_with_cgategroups_cli)

[CGates and CGateGroups: Parameters List](../working_with_cgates_cli/cgates_parameter_list)

[About CGates and CGateGroups](../)

[Overview: Connection Gates](../../../ov_gateway/ov_connection_gates)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
