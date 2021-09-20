{
    "title": "Directory browsing",
    "linkTitle": "Directory browsing",
    "weight": "160"
}By setting up a directory structure, you can access system drives and network mounts on Windows.

## Set up the structure for directory browsing

Use the following procedure to set up the structure for directory browsing.

1.  Enable browsing for system drives.  
    For system drives, create a directory under`<FILEDRIVEHOME>\..\cygwin\drives` with the drive letter as a name, and give permission to everyone. For example, to enable browsing of the `C` drive, create the following folder:  
    `<FILEDRIVEHOME>\..\cygwin\drives\c`
2.  Enable browsing for network shares.  
    For network shares `\\<hostname>\<sharename>`, create a directory structure like the following:  
    `<FILEDRIVEHOME>\..\cygwin\net\<hostname>\<sharename>`
      
    and give permission to everyone for this directory. `<hostname>` and &lt;`sharename>` are both required.  
    For example, to enable browsing of network share with path:  
    `\\myhost\my-shared-folder`
      
    create the following folder:  
    `<FILEDRIVEHOME>\..\cygwin\net\myhost\my-shared-folder`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">System drives in the user’s home folder are enabled for browsing by default.         </td>
      </tr>
</table>
