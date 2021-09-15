{
    "title": "Command line utilities",
    "linkTitle": "Command line utilities",
    "weight": "230"
}The Axway SecureTransport Server includes several utility files that allow users to manually perform functions like installing a license file, stopping a server, and starting a server. These files are scripts on UNIX and batch files (`.bat`) on Windows. The utility files are located in the `<FILEDRIVEHOME>/bin` directory.

[Utility files](r_st_utilityfiles) provides a summary of the utilities and their functions.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If an alias is used to install <span>SecureTransport</span>, use the <code>-A</code> option for any other commands for the server on UNIX. For example, to stop all servers for a <span>SecureTransport</span> installation with an alias as <code>myserver</code> on UNIX, use the following command:<br/><code>./stop_all -A myserver</code><br/>On Windows, you do not need to use the <code>-A</code> option. Instead, use the following command:<br/><code>stop_all</code><br/>         </td>
      </tr>
</table>

The following topics describe how to control servers from the command line and list the command line utility files:

-   [Control the servers](r_st_controlservers) - Describes how to control servers from the command line.
-   [Utility files](r_st_utilityfiles) - Lists the command line utility files.
