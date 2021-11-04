{
    "title": "faction",
    "linkTitle": "faction",
    "weight": "1030"
}<span id="faction"></span>

### faction

<span id="faction_CFTSEND"></span>

#### CFTSEND, SEND

**\[FACTION = {<span style="text-decoration: underline;">NONE</span>
| DELETE | ERASE | ARCHIVE }\]**

Action on the file after a send transfer:

-   <span style="font-weight: bold;">NONE</span>: No action on this file on completion
    of the transfer.
-   <span style="font-weight: bold;">DELETE</span>: Delete the file after transfer. Note the following specificities:
    -   No delete occurs if you are using SELFNAME and the FNAME is set to a directory mask (for example, #dir is deleted, but #dir/\* is ignored).
    -   If a file is added to the directory while a transfer is in progress, neither this new file nor is the directory is deleted.
-   <span style="font-weight: bold;">ERASE</span>: erase the contents of the file
    after the transfer ("End Of File" mark at the beginning of the
    file)
-   **ARCHIVE**: the source file is moved to the file name specified in the ARCHIVEFNAME parameter when the transfer is completed. If the transfer fails, the file is not moved. If the target file already exists, it is overwritten.

<span class="bold_in_para">FACTION limitations</span>

-   ERASE is not supported when using a group of files in homogeneous mode, or when broadcasting (CFTDEST ).
-   DELETE is not supported when broadcasting (CFTDEST ).
-   ARCHIVE is not supported when using a group of files (homogeneous transfers), or when broadcasting (CFTDEST).
-   OS-specific limitations:
    -   z/OS: VSAM, PDS, and GDG files are not supported.
    -   HP NonStop: ARCHIVE is not supported with Guardian files.

#### CFTRECV, RECV

**\[FACTION = {<span style="text-decoration: underline;">VERIFY</span>
| DELETE | ERASE | RENAME | RETRYRENAME }\]**

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The RENAME option is only available on Unix platforms.         </td>
      </tr>
   </tbody>
</table>

Action on a file before a receive transfer except when using RENAME or RETRYRENAME, which are post transfer actions.

If a receiver file with the same name already exists, <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> performs
one of the following actions:

-   <span style="font-weight: bold;">VERIFY</span>: checks that the file is empty before the transfer occurs
-   <span style="font-weight: bold;">DELETE</span>:
    deletes the file before the transfer occurs
-   <span style="font-weight: bold;">ERASE</span>:
    erases the contents of the file before the transfer occurs
-   **RENAME**: replaces the existing FNAME file after the transfer completes by renaming the WFNAME file (*Unix only*)
-   **RETRYRENAME**: Renames the file on transfer completion in the post-processing phase, and includes a configurable retry mechanism. See also [Post-transfer file renaming](../../../../app_integration_intro/spoolout).

Requirements when using RENAME or RETRYRENAME:

-   If the CFTRECV WFNAME is not defined, the transfer fails with DIAGI=138.
-   The user (userid) who performs the transfer must have adequate rights to rename the file WFNAME to file FNAME. If not, the transfer fails with DIAGI=156.

The following table shows the combined effect of the FDISP and FACTION parameters when used in a RECV command.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>There no impact on FDISP when used in combination with RENAME or RETRYRENAME.         </td>
      </tr>
   </tbody>
</table>

<table>
   <th>
      <tr>
<th>CFTRECV, FDISP         </th>
<th>CFTRECV, FACTION         </th>
<th>Comments         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>both         </td>
         <td>delete         </td>
         <td>If no file exists, the file is created. If file exists it is deleted and recreated (regardless of if it is empty or not).         </td>
      </tr>
      <tr>
         <td>both         </td>
         <td>erase         </td>
         <td>If no file exists, the file is created. If file exists it is overwritten (no matter if it is empty or not).         </td>
      </tr>
      <tr>
         <td>both         </td>
         <td>verify         </td>
         <td>If no file exists, the file is created. If file exists and it is not empty, the transfer is aborted. If file exists but it is empty, the file is overwritten.         </td>
      </tr>
      <tr>
         <td>new         </td>
         <td>verify         </td>
         <td>If no file exists, the file is created. If file exists the transfer is aborted (regardless of if it is empty or not).         </td>
      </tr>
      <tr>
         <td>old         </td>
         <td>delete         </td>
         <td>If no file exists, the transfer is aborted. If file exists the file is deleted and recreated (regardless of if it is empty or not).         </td>
      </tr>
      <tr>
         <td>old         </td>
         <td>erase         </td>
         <td>If no file exists, the transfer is aborted. If file exists the file is overwritten (regardless of if it is empty or not).         </td>
      </tr>
      <tr>
         <td>old         </td>
         <td>verify         </td>
         <td>If no file exists, the transfer is aborted. If file exists and it is not empty, the transfer is aborted. If file exists but it is empty, the file is overwritten.         </td>
      </tr>
   </tbody>
</table>

<table>
   <th>
      <tr>
<th>OS         </th>
<th>Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>z/OS</p>         </td>
         <td><p>For VSAM files, only FACTION = ERASE is accepted.</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)<a href="#" class="selected"> </a>