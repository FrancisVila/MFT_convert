{
    "title": "Command line utilities",
    "linkTitle": "Command line utilities",
    "weight": "220"
}The <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> Server includes several utility files that allow users to manually perform functions like installing a license file, stopping a server, and starting a server. These files are scripts on UNIX and batch files (`.bat`) on Windows. The utility files are located in the `<FILEDRIVEHOME>/bin` directory.

<a href="r_st_utilityfiles#AppCommandLineUtilities_1050989234_1010168" class="MCXref xref">Utility files</a> provides a summary of the utilities and their functions.

> **Note:**
>
> If an alias is used to install SecureTransport, use the -A option for any other commands for the server on UNIX. For example, to stop all servers for a SecureTransport installation with an alias as myserver on UNIX, use the following command:./stop\_all -A myserverOn Windows, you do not need to use the -A option. Instead, use the following command:stop\_all

The following topics describe how to control servers from the command line and list the command line utility files:

-   <a href="r_st_controlservers" class="MCXref xref">Control the servers</a> - Describes how to control servers from the command line.
-   <a href="r_st_utilityfiles" class="MCXref xref">Utility files</a> - Lists the command line utility files.
