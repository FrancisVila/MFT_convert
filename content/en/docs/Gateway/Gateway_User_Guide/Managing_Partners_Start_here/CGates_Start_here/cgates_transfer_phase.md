{
    "title": "CGates: Transfer phase",
    "linkTitle": "CGates: Transfer phase",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[How Gateway selects a Site](#How_Gateway_selects_a_Site)

[Passing parameters to File Transfer Layer](#Passing_parameters_to_File_Transfer_Layer)

<span id="How_Gateway_selects_a_Site"></span>

## How Gateway selects a Site

For the transfer phase, Gateway must select a Site object that represents the remote partner. The following three cases are possible:

-   Gateway identifies a Remote Site whose protocol parameters match those taken from the network during the protocol connection phase. In this case, this Site becomes the connected Site.
-   No configured Remote Site matches the client trying to connect. If correctly configured, Gateway can dynamically create a Remote Site using a template. This template is a special type of Remote Site that only plays the role of Initiator and has no defined network parameters. The template is duplicated and completed depending on the current connection being processed. The following Template Sites are automatically created on Gateway startup:
    -   TPEL: PEL connections
    -   TODT: OFTP connections
    -   TFTP: FTP connections
    -   TSFTP: SFTP connections
    -   TFTP\_HTTP: FTP/HTTP connections
    -   TPHSE: PHSE connections
    -   THTTP: HTTP connections

To enable Gateway to use this mechanism, you must set the <span style="font-style: italic;">template\_site</span> field of one of the CGateGroup members in the selected CGate hierarchy. Since a CGate hierarchy can comprise multiple CGateGroups, Gateway takes into account the <span style="font-style: italic;">template\_site</span> field value taken from the CGateGroup nearest the root.

-   No defined Remote Site matching the connection is defined and no <span style="font-style: italic;">template\_site</span> field in the whole selected CGate hierarchy is set. Although the CGate definition is valid, the connection is rejected.

<span id="Passing_parameters_to_File_Transfer_Layer"></span>

## Passing parameters to File Transfer Layer

When Gateway selects a CGate (and its associated CGateGroup hierarchy), it passes a set of parameters for the current connection to the File Transfer Layer (depending on the protocol).

You can set the same parameters in several CGates and CGateGroups within a given hierarchy. In some cases all parameters are taken into account (additive parameters). In other cases, parameters are overwritten by object definitions higher up the hierarchy ([overwritten parameters](#Overwritten_parameters)).

<span id="Additive_parameters"></span>

### Additive parameters

The following CGate parameters are additive:

-   User parameters 1 and 2: used to customize VFD logical file availability. All user parameters that you define within a given hierarchy are taken into account.
-   VFD rights (described below)

<span id="Defining_VFD_rights"></span>

### Defining VFD rights

Gateway uses CGates to assign Virtual File Directory access rights to connecting users.

You can define VFD access rights in both CGates and CGateGroups. This means that you can define a set of shared rights for a group of users in the CGateGroup and can refine this definition, if required, by defining specific additional rights for a given CGate within that group.

<span style="font-weight: bold;">Note:</span> VFD rights are only meaningful for connections via FTP, SFTP or HTTP protocols.

The definition of VFD rights for a CGate (or CGateGroup) comprises the following fields:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Directory path</p>         </td>
         <td><p>The VFD absolute path of the directory (either logical, mounted or real) to which the rights apply</p>         </td>
      </tr>
      <tr>
         <td><p>VFD File pattern</p>         </td>
         <td><p>File name mask – may contain wildcards (<span style="font-weight: bold;">?</span> and <span style="font-weight: bold;">*</span>). The <span style="font-style: italic;">file rights</span> (see below) only apply to the files (either logical or real) that match the file mask.</p>         </td>
      </tr>
      <tr>
         <td><p>Subdirectory inheritance</p>         </td>
         <td><p>The current rights definition applies to the sub-directories of the directory that the <span style="font-style: italic;">directory path</span> field references (and recursively).</p>         </td>
      </tr>
      <tr>
         <td><p>Directory rights</p>         </td>
         <td><p>Authorized operations on the current directory (referenced by the <span style="font-style: italic;">directory path</span> field). You can authorize the following operations:</p>
<ul>
<li><span style="font-style: italic;">List (L):</span> Users are authorized to list the contents of the directory (<span style="font-style: italic;">LIST FTP</span> command).</li>
<li><span style="font-style: italic;">Create (C):</span> Users are authorized to create sub-directories in the current directory.</li>
<li><span style="font-style: italic;">Remove (R):</span> Users are authorized to remove sub-directories from the current directory.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>File rights</p>         </td>
         <td><p>Authorized operations on the files located in the current directory and that match the <span style="font-style: italic;">file pattern</span> field<span style="font-style: italic;">.</span> You can authorize the following operations:</p>
<ul>
<li><span style="font-style: italic;">Read (R):</span> Users are authorized to read the file (via FTP or HTTP Get operation). If the <span style="font-style: italic;">file pattern</span> field is empty, this operation corresponds to the user rights for downloading files.</li>
<li><span style="font-style: italic;">Write (W):</span> Users are authorized to overwrite the file (via FTP or HTTP Put operation). If the <span style="font-style: italic;">file pattern</span> field is empty, this operation corresponds to the user rights for uploading files.</li>
<li><span style="font-style: italic;">Delete (D):</span> Users are authorized to delete the file.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Example of CGate hierarchy VFD rights

The following example shows the VFD rights defined for a CGate hierarchy that comprises a root CGateGroup <span style="font-weight: bold;font-style: italic;">G1</span>, a sub-group <span style="font-weight: bold;font-style: italic;">G1-1</span> and a CGate <span style="font-weight: bold;font-style: italic;">U1</span>. The resolved VFD rights are associated with a user that matches the <span style="font-weight: bold;font-style: italic;">U1</span> CGate definition.

<table>
         
         
         
         
         
         
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p>dir_path</p>         </td>
         <td><p>file_pattern</p>         </td>
         <td><p>dir_rights</p>         </td>
         <td><p>file_rights</p>         </td>
         <td><p>subdir_</p>
<p>inheritance</p>         </td>
      </tr>
      <tr>
         <td><p>CGateGroup <span style="font-weight: bold;font-style: italic;">G1</span></p>         </td>
         <td><p>/upload</p>         </td>
         <td><p>*.txt</p>         </td>
         <td><p>LC</p>         </td>
         <td><p>W</p>         </td>
         <td><p>N</p>         </td>
      </tr>
      <tr>
         <td><p>CGateGroup <span style="font-weight: bold;font-style: italic;">G1-1</span></p>         </td>
         <td><p>/download</p>         </td>
         <td><p>*.*</p>         </td>
         <td><p>L</p>         </td>
         <td><p>R</p>         </td>
         <td><p>N</p>         </td>
      </tr>
      <tr>
         <td><p>CGate <span style="font-weight: bold;font-style: italic;">U1</span></p>         </td>
         <td><p>/upload/user1</p>         </td>
         <td><p>*.*</p>         </td>
         <td><p>L</p>         </td>
         <td><p>none</p>         </td>
         <td><p>N</p>         </td>
      </tr>
      <tr>
         <td><p>/common</p>         </td>
         <td><p>*.*</p>         </td>
         <td><p>LCR</p>         </td>
         <td><p>RW</p>         </td>
         <td><p>Y</p>         </td>
      </tr>
   </tbody>
</table>

Gateway resolves the VFD rights for CGate U1 users as follows: they inherit all VFD rights defined for CGate U1, CGateGroup G1-1 and CGateGroup G1.

<span id="Overwritten_parameters"></span>

### Overwritten parameters

All remaining CGate parameters are overwritten within the hierarchy. Gateway always applies the parameter settings from the CGateGroup nearest the root. Some parameters are independent of the connection type and others are protocol-dependent.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Meaning</p>         </td>
      </tr>
      <tr>
         <td><p>PeSIT HS D &amp; E specific parameters:</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">server_password</span></p>         </td>
         <td><p>Server connection partner password returned to the connection partner</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP, FTP, SFTP specific parameters:</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">home_dir</span></p>         </td>
         <td><p>VFD directory on which the first <span class="code" style="font-weight: bold;">LIST</span> command (HTTP or FTP) is processed just after protocol connection</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">root_dir</span></p>         </td>
         <td><p>VFD root directory of the connected user. Regardless of the VFD rights defined for the current CGate, the connected user only has access to the VFD directory tree under the root directory (HTTP or FTP connections).</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">HTTP only:</span></p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">http_home_page</span></p>         </td>
         <td><p>Default HTTP home page that you can reference via a symbolic link in the Gateway website HTML pages</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">http_list_template</span></p>         </td>
         <td><p>VFD file path that points to an HTML page used for browsing the VFD directory tree</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

In this example the CGate hierarchy comprises a single CGateGroup (the root) <span style="font-weight: bold;font-style: italic;">G1</span> and a CGate <span style="font-weight: bold;font-style: italic;">U1</span> with the following <span class="code">http\_home\_page</span> field values:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>G1 definition:</p>         </td>
         <td><p>http_home_page: /http/download/home_page.html</p>         </td>
      </tr>
      <tr>
         <td><p>U1 definition:</p>         </td>
         <td><p>http_home_page: /home/index.html</p>         </td>
      </tr>
   </tbody>
</table>

The valid <span class="code">http\_home\_page</span> value obtained by merging the CGate hierarchy is: <span class="code" style="font-weight: bold;">/http/download/home\_page.html</span> since this is the set value taken from the CGateGroup nearest the root (G1).

<span id="Substituting_symbolic_variables"></span>

### Substituting symbolic variables

Values for all input and output parameters (except those used for CGate selection and VFD rights) can contain symbolic variables.

#### Syntax

Symbolic variable syntax is <span style="font-weight: bold;">$(VAR)</span> where VAR is any of the following:

PROTOCOL, LOGIN\_USER, LOGIN\_PASSWORD, LOGIN\_SAP, CLIENT\_IDENT, SERVER\_IDENT, CLIENT\_PASSWORD and TLS\_CN

For example, if you define the user login and password fields as follows:

login\_user=\*

login\_password=$(LOGIN\_USER)@axway.com

then, for an FTP client station identification, any user name is accepted, but the password must be &lt;<span style="font-style: italic;">Username</span>&gt; followed by the string <span style="font-style: italic;">@axway.com</span>.

So if the FTP user name is <span style="font-weight: bold;">rftp</span>, the associated password must be <span style="font-style: italic;">rftp@axway.com</span>.

Symbolic variable syntax is <span style="font-weight: bold;">&(VAR)</span> when VAR is either of the following:

\- ORIGINATOR: transfer protocol originator

\- DESTINATION: transfer protocol destination

For example:

route\_remote\_agent=&(DESTINATION)

route\_local\_agent= &(ORIGINATOR)

<span style="font-weight: bold;">Note:</span> The symbolic variable <span class="code">TLS\_CN</span> is only available if the incoming connection is secured with TLS or SSL with mutual authentication. It consists of the common name (CN) of the user. For compatibility with previous releases and protocol specifications, such as the format of the FTP login user field, this field cannot contain spaces. You must check whether the certificates used correspond to this rule.

Related topics

[Overview: Connection Gates](../../../ov_gateway/ov_connection_gates)

[About CGates and CGateGroups](../)

[CGates: Protocol connection phase](../cgates_protocol_connection_phase)

[Working with CGates and CGateGroups](../working_with_cgates_and_cgategroups_(gui))

[Working with CGates (command line)](../working_with_cgates_cli)

[Working with CGateGroups (command line)](../working_with_cgates_cli/working_with_cgategroups_cli)

[CGates and CGateGroups: Parameters List](../working_with_cgates_cli/cgates_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
