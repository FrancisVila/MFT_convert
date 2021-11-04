{
    "title": "Transferring multiple files with SFTP ",
    "linkTitle": "Transferring multiple files with SFTP",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About transferring multiple files](#About)

[Transferring multiple files](#Transferring_multiple_files)

[Displaying transfer details](#displaying_transfer_details)

<span id="About"></span>

## About transferring multiple files

Gateway’s SFTP client can upload and download <span style="font-style: italic;">multiple files</span> with a single Transfer Request.

This function is equivalent to the SFTP <span class="code">MPUT</span> and <span class="code">MGET</span> commands:

-   <span class="code">MPUT</span>: to upload multiple files from a local directory to a remote site
-   <span class="code">MGET</span>: to download multiple files from a remote site to a local directory

When you use this function, Gateway carries out the following functions:

1.  Lists the files of the specified directory.
2.  Parses the list.
3.  Applies a filter to specified file attributes.
4.  Selects the matching files.
5.  Requests and attaches the individual file transfers ("children") to a multiple transfer ("master").
6.  Uploads or downloads the matching files.

This function is compatible with UNIX and Windows platforms.

<span id="Transferring_multiple_files"></span>

## Transferring multiple files

<span style="font-weight: bold;">Prerequisite:</span> All files must be in the same directory.

### Using the GUI

Submit a Transfer Request with the following parameters:

1.  In the [General tab](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab):
    -   In <span style="font-weight: bold;">Type</span>, select <span style="font-weight: bold;">MULTI</span>
    -   In <span style="font-weight: bold;">Direction</span>, select <span style="font-weight: bold;">Send</span> (<span class="code">MPUT</span> or upload) or <span style="font-weight: bold;">Receive</span> (<span class="code">MGET</span> or download)
2.  In the [Attributes tab](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab):
    -   Complete the <span style="font-weight: bold;">Filter</span> field to specify the files to send or receive. You can filter on file properties such as name, size, time, etc.
    -   Select the <span style="font-weight: bold;">Hash type</span> to determine the file duplication behavior.
    -   (<span style="font-style: italic;">optional</span>) Select the <span style="font-weight: bold;">Model to use for child transfers</span>.

### Using online commands

Use the <span class="code" style="font-weight: bold;">peltrans</span> online command to submit a Transfer Request with the following parameters:

-   Set <span class="code">-type (-ty</span>) to <span style="font-weight: bold;">MULTI</span>.
-   Set <span class="code">-direction (-dir)</span> to <span style="font-weight: bold;">O</span> (<span class="code">MPUT</span> or upload) or <span style="font-weight: bold;">I</span> (<span class="code">MGET</span> or download).
-   Use <span class="code">-multi\_filter (-muf)</span> to specify the files to send or receive. You can filter on file properties such as name, size, time, etc.
-   Use <span class="code">-multi\_hash\_type (-muh)</span> to determine the file duplication behavior.
-   Use <span class="code">-multi\_model (-mum) &lt;Model name></span> to select a Model to apply to the <span style="font-style: italic;">child</span> transfers.

#### Example 1: Submitting an MGET using the peltrans online command

**peltrans**  -type MULTI  –mode I  –dir I  -oa RS16\_STD  -da LOCAL  -ap FTP\_A

          –dn public/available\_things/

where:

<span class="code">dir\_name (-dn)</span> is the name of the directory on the remote computer.

#### Example 2: Submitting an MPUT using the peltrans online command

**peltrans**  -type MULTI  -da RS16\_STD  -oa LOCAL  -mode I  -dir O  -ap FTP\_A

          -fc \\Temp\\doc\\Rfc\\HTTP  –dn public/received\_things/

where:

<span class="code">file\_component (-fc)</span> indicates the name of the local directory that contains the files to send. This parameter is normally used for the name of the file to send.

<span class="code">dir\_name (-dn)</span> is the name of the directory on the remote computer.

<span id="displaying_transfer_details"></span>

## Displaying transfer details

Use the <span class="code">peldsp display\_trans</span> command to display the details of a Transfer. When you use this command on a master transfer id, you get the following additional lines:

x\_multi\_state='processed all ok'

x\_multi\_hash\_type='1'

x\_multi\_model=''

x\_multi\_filter='name=\*.h'

x\_multi\_nb\_total='90'

x\_multi\_nb\_ok='90'

 

For <span class="code">x\_multi\_state</span>, there are three possible states:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>State</p>         </th>
<th class="HeadE-Column1-Header1"><p>Message displayed</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SUCCESS</p>         </td>
         <td><p><span class="code">processed all ok</span></p>         </td>
         <td><p>All child transfers have been transferred successfully.</p>         </td>
      </tr>
      <tr>
         <td><p>PARTIAL_SUCCESS</p>         </td>
         <td><p><span class="code">processed partial ok</span></p>         </td>
         <td><p>Error on at least one child transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>ERROR</p>         </td>
         <td><p><span class="code">processed all ko</span></p>         </td>
         <td><p>Errors on all child transfers.</p>         </td>
      </tr>
   </tbody>
</table>

This information is also displayed in the GUI.

Related topics

[Working with File Transfer Requests](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui))

[Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli)

[Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
