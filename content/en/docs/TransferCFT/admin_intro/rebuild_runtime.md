{
    "title": "Rebuild the runtime",
    "linkTitle": "Rebuild the runtime",
    "weight": "190"
}# Rebuild the runtime



This section describes how to rebuild the unified configuration environment. You may need to use this process after accidentally erasing critical files, to deal with corrupted files, or after a disk failure.



## <span id="Create_regenerate_runtime_uconf"></span>Create or regenerate runtime uconf environment



**UNIX and Windows only**



**UNIX syntax**



cftruntime \[-h|--help|-p|--profile|-n &lt;name&gt;|--uconf|--inst\] &lt;cft-install-dir&gt; &lt;cft-runtime-dir&gt; \[--mac=yes|no\]



Where:



-   -p --profile : Regenerates the profile file

-   -n &lt;name&gt; : Regenerates the profile file with &lt;name&gt; of your choice

-   --uconf: Regenerates the uconf file.

-   -h --help: Displays this help.

-   --runtime: Creates a new runtime environment.

-   --inst: Creates an initial runtime environment, only when run by the Synchrony Installer.



**Example**



In a UNIX environment, regenerate the uconf settings as follows:



<table data-cellspacing="0">
<tbody>
<tr>
<td>cftruntime --uconf /home/Transfer_CFT/home /home/Transfer_CFT/runtime</td>
</tr>
</tbody>
</table>



**Windows syntax**



cftruntime &lt;cft-install-dir&gt; &lt;cft-runtime-dir&gt; \[-profile|-n &lt;name&gt;|-uconf|-inst\]



Where:



-   cft-install-dir: Is the full Transfer CFT install path and must exist.

-   cft-runtime-dir: Is the full Transfer CFT runtime path and does not exist.



Usage:



-   -profile: Creates a new profile.bat and backs up the old one.

-   -name: Creates a new profile with the &lt;name&gt; of your choice.

-   -uconf: Regenerates the uconf file.

-   -inst: Creates the initial runtime environment, which is used exclusively by the Installer.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">You must use double quotes when indicating a path that contains spaces.</td>
</tr>
</tbody>
</table>



**Example 1**



In a Windows environment, create a new runtime called <span>runtime2</span>:



<table data-cellspacing="0">
<tbody>
<tr>
<td>cftruntime c:\AxwayCFT38\Transfer_CFT\home c:\AxwayCFT36\Transfer_CFT\runtime2</td>
</tr>
</tbody>
</table>



**Example 2**



In a Windows environment, regenerate the <span>cftuconf.dat</span> uconf settings as follows:



<table data-cellspacing="0">
<tbody>
<tr>
<td>cftruntime c:\AxwayCFT38\Transfer_CFT\home c:\AxwayCFT36\Transfer_CFT\runtime –uconf</td>
</tr>
</tbody>
</table>
