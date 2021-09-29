{
    "title": "Extract the Access Management Cache",
    "linkTitle": "Extract the Access Management Cache",
    "weight": "370"
}If you need to check the Transfer CFT rights for a specific user, you can use the EXTAMCACHE command to obtain this information.

Command syntax: EXTAMCACHE

## Parameters

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fname">FNAME</a></td>
<td>Selects the Access Management cache file. By default, this is the CFTAM file, which is located in the <span>data </span>folder.</td>
</tr>
<tr class="even">
<td><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fout">FOUT</a></td>
<td>Selects the output file. By default, it is the console.</td>
</tr>
<tr class="odd">
<td><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a></td>
<td><p>Selects the user, or users, for which you want to obtain access rights. By default, the function returns all users.</p>
<p>You can use the wildcard characters <span>*</span> and <span>?</span> to filter the user names.</p></td>
</tr>
</tbody>
</table>

Example

The following command extracts the cache file information for all users and their rights to a text file called AMuser.txt.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL EXTAMCACHE FOUT=AMuser.txt</td>
</tr>
</tbody>
</table>

Or, to filter on user names containing "admin":

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL EXTAMCACHE ID=Admin*, FOUT=export_cache</td>
</tr>
</tbody>
</table>

The following is an example output:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>Access Management cache, last update at 2018-08-27T06:19:21.882+02:00</p>
<p> </p>
<p>3 entries found in the Access Management Cache:</p>
<p>==&gt; Application@Synchrony Has the following privileges:</p>
<p>CONFIGURATION:CFTPARM VIEW</p>
<p>TRANSFER                           RESUME</p>
<p>TRANSFER                           DELETE</p>
<p>TRANSFER                           CANCEL</p>
<p>TRANSFER                           SUBMIT</p>
<p>TRANSFER                           PAUSE</p>
<p>TRANSFER                           EXECUTE</p>
<p>TRANSFER                           VIEW</p>
<p>TRANSFER                           END</p>
<p>TRANSFER                           CREATE</p>
<p>CONFIGURATION:CFTRECV              VIEW</p>
<p>SERVICE:UI                         CONNECT</p>
<p>CONFIGURATION:CFTSEND              VIEW</p>
<p>FILTER:CATALOG                     DELETE</p>
<p>FILTER:CATALOG                     VIEW</p>
<p>FILTER:CATALOG                     EDIT</p>
<p>FILTER:CATALOG                     CREATE</p>
<p>CONFIGURATION:CFTCOM              VIEW</p>
<p>FILE                                VIEW</p>
<p>FILTER:LOG                          EDIT</p>
<p>FILTER:LOG                          DELETE</p>
<p>FILTER:LOG                          VIEW</p>
<p>FILTER:LOG                         CREATE</p>
<p>CONFIGURATION:CFTPART              VIEW</p>
<p>TRANSFER                           EDITFILE</p>
<p>TRANSFER                            EDIT</p>
<p>TRANSFER                            VIEWFILE</p>
<p>TRANSFER                            DELETEFILE</p>
<p>CONFIGURATION:CFTLOG                VIEW</p>
<p>CONFIGURATION:CFTDEST               VIEW</p>
<p>==&gt; HelpDesk@Synchrony             Has no access</p>
<p>==&gt; Partner@Synchrony                Has no access</p></td>
</tr>
</tbody>
</table>

 
