{
    "title": "z/OS: Installation and Operation",
    "linkTitle": "Prerequisites",
    "weight": "130"
}## Preface

The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Installation Guide provides instructions for installing and deploying your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

<span id="Installation support format"></span>

## Version

The minimum z/OS version depends on the JES:

-   If you use the JES2 component, then you require z/OS 2.1 or higher
-   If you use the JES3 component, then you require z/OS 2.2 or higher

<span id="Installation support format"></span>

## Version format

To accommodate changing product versions, we use the convention &lt;version> in place of the actual version number in samples and lists.

For example if your Transfer CFT is version 3.3.x, the file ZOS/CFT/&lt;version> would be ZOS/CFT/3.3.x.

<span id="Delivery process"></span>

## Delivery - distribution method

Axway delivers Transfer CFT z/OS on the support site: [support.axway.com](https://support.axway.com/). To download the packages from Axway support, you require a user ID and password.

There are three Transfer CFT packages available on the Axway support site - 2 packages for the standard Transfer CFT installation method (which differ only in file format, ADRDSSU or XMIT), and additionally the SMP/E Transfer CFT installation package.

Again, there are 2 product packaging formats in the **`Components\Transfer_CFT_V<version>_mvs\install`** directory:

-   \\adrdssu 
-   \\xmit

**<span id="kanchor14"></span>Installation directory contents**

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">File         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfer_CFT_&lt;version&gt;_mvs_&lt;format&gt;.bin</p>         </td>
         <td><p>Product</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer_CFT_&lt;version&gt;_mvs_&lt;format&gt;_J1IDIST.txt</p>         </td>
         <td><p>JCL that creates the distribution environment</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer_CFT_&lt;version&gt;_mvs_&lt;format&gt;_J2IICFT.txt</p>         </td>
         <td><p>JCL that creates the instance environment</p>         </td>
      </tr>
   </tbody>
</table>

<span id="kanchor15"></span>

## Transfer CFT z/OS components

The Transfer CFT z/OS components include:

-   CFTUTIL: Batch program for processing the commands and parameters
-   CFTMAIN: File transfer server itself, which is comprised of:
    -   CFTTPRO: File transfer protocols (PeSIT)
    -   CFTTFIL: File manager
    -   CFTTCP: TCP/IP network manager
    -   CFTLOG: Log file manager
    -   CFTTRK: Manages message tracking towards Sentinel
    -   CFTTCOM: Command file manager
    -   CFTTCOMS: Manages commands in synchronous mode
    -   CFTOPER: Operator console interface
    -   CFTTSSL: Partner and data ciphering authentication interface
    -   CFTPRX: Proxy task
    -   CFTAPI: Interface for user batch programming
    -   CFTSFTP: Main SFTP task, with POSIX runtime option set to ON
    -   Threads (BPXPTATT) are started one by one and are permanent (unlike TFIL tasks)
-   Other major components:
    -   CFTPKI: Management utility for internal datafile security
    -   CFTCOPL: Transfer CFT UI server
    -   COPSTOP: Stops the Transfer CFT UI server

<span id="Special"></span>

## Special characters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Windows         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Unix         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">z/OS         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">IBM i         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>char_file         </td>
         <td><p>Logical name prefix</p>         </td>
         <td>$         </td>
         <td>_         </td>
         <td>$         </td>
         <td>+         </td>
      </tr>
      <tr>
         <td>char_mask         </td>
         <td>Wildcard character         </td>
         <td>?         </td>
         <td>?         </td>
         <td>?         </td>
         <td>?         </td>
      </tr>
      <tr>
         <td>char_unit         </td>
         <td>Separator character (volume)         </td>
         <td>%         </td>
         <td>\01         </td>
         <td>%         </td>
         <td>;         </td>
      </tr>
      <tr>
         <td>char_symb         </td>
         <td>Symbolic variable prefix         </td>
         <td>&amp;         </td>
         <td>&amp;         </td>
         <td>&amp;         </td>
         <td>?         </td>
      </tr>
      <tr>
         <td>file_symb         </td>
         <td>Character introducing a file name passed to CFTUTIL as a parameter         </td>
         <td>#         </td>
         <td>@         </td>
         <td>#         </td>
         <td>#         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [Prerequisites](r_prerequistes_zos)
-   Installing Transfer CFT z/OS
