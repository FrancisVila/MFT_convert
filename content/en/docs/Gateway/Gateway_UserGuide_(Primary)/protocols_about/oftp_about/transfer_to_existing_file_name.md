{
    "title": "Transfer to an existing file name",
    "linkTitle": "Transfer to an existing file name",
    "weight": "250"
}The following properties define the actions Gateway performs on a pre-existing file before receiving the transfer of a file with the same name, in the case of OFTP and PeSIT protocols.

-   **File availability  
    **Specifies whether the Gateway server accepts incoming files with the same name as existing ones.
-   **File action  
    **Specifies the action Gateway takes if an incoming file has the same name as an existing one.

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>File
availability</p>         </th>
<th class="HeadE-Column1-Header1"><p>File
action</p>         </th>
<th class="HeadE-Column1-Header1"><p>File
with same name as the incoming file</p>         </th>
<th class="HeadD-Column1-Header1"><p>Transfer
accepted</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>New</strong></p>         </td>
         <td><p>Erase</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Delete</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Verify</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td><p><strong>New</strong></p>         </td>
         <td><p>Erase</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Delete</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Verify</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Old</strong></p>         </td>
         <td><p>Erase</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Delete</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Verify</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>Yes, if the existing file is empty</p>
<p>No, if the existing file is not empty</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Old</strong></p>         </td>
         <td><p>Erase</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Delete</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Verify</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Both</strong></p>         </td>
         <td><p>Erase</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Delete</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Verify</p>         </td>
         <td><p>exists</p>         </td>
         <td><p>Yes, if the existing file is empty</p>
<p>No, if the existing file is not empty</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Erase</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Delete</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>Verify</p>         </td>
         <td><p>does not exist</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
   </tbody>
</table>

## Receiving a pre-existing file

The values in this section
define the action of the monitor if the file being transferred already exits.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>File availability</strong></p>         </td>
         <td><p>Select one of the following values:</p>
<ul>
<li>Undefined</li>
<li>New</li>
<li>Old</li>
<li>Both</li>
</ul>
<p>Gateway responds to the various possible pre-existing file
conditions depending on the values of the <em>File availability</em> and <em>File
action</em> parameters.</p>
<p>Refer to the description of the <em>File action</em>
parameter below.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>File action</strong></p>         </td>
         <td><p>Select one of the following values:</p>
<ul>
<li>Undefined</li>
<li>Erase</li>
<li>Delete</li>
<li>Verify</li>
</ul>
<p>To determine how to handle a pre-existing file, Gateway
interprets the File availability and File action parameter
values as follows:</p>
<p>If <em>File availability</em> is set to:</p>
<ul>
<li><strong>NEW</strong> and a valid file with the same file name already exists, then:
<ul>
<li><strong>ERASE</strong> = refuse</li>
<li><strong>DELETE</strong> = refuse</li>
<li><strong>VERIFY</strong> = refuse</li>
</ul></li>
<li><strong>NEW</strong> and a file with the same file name does not already exist, then:
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept</li>
</ul></li>
<li><strong>OLD</strong> and a valid file with the same file name already exists, then:
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept if empty, refuse if not empty</li>
</ul></li>
<li><strong>OLD</strong> and a file with the same file name does not already exist, then:
<ul>
<li><strong>ERASE</strong> = refuse</li>
<li><strong>DELETE</strong> = refuse</li>
<li><strong>VERIFY</strong> = refuse</li>
</ul></li>
<li><strong>BOTH</strong> and a valid file with the same file name already exists, then:
containing
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept if empty, refuse if not empty</li>
</ul></li>
<li><strong>BOTH</strong> and a file with the same file name does not already exist, then:
containing
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept</li>
</ul></li>
</ul>
<p>where:</p>
<p>   accept = accept the transferred file</p>
<p>   refuse = refuse the transferred file</p>         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
