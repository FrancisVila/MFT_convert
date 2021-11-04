{
    "title": "Real users",
    "linkTitle": "Real users",
    "weight": "230"
}> **Note:**
>
> Real users cannot be granted access to SecureTransport on non-root installations.

Real users are the users defined at the operating-system level. Access rights to the server file system for real users are based on the underlying operating system file access rights. Real users can be defined locally on the server (for instance, on a UNIX-based platform in `/etc/passwd`, or on Windows as a computer-specific local user) or on a network resource (NIS for UNIX or on a domain controller for Windows).

Set a home folder for each real user to ensure that the user is not logged into a randomly-selected directory when logging in to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

> **Note:**
>
> Real users can view the complete file system of the SecureTransport Server, regardless of the location of the home folder.

The following topics describe real users on UNIX and on Windows:

-   <a href="#Real_UNIX" class="MCXref xref">Real users on UNIX</a>
-   <a href="#Real_Windows" class="MCXref xref">Real users on Windows</a>

**Related topic:**

-   <a href="../t_st_passwordfiles" class="MCXref xref">Manage password files</a>

<span id="Real_UNIX"></span>

## Real users on UNIX

UNIX real users are the users defined in `/etc/passwd`, or in NIS. Real users are created at the system level. They can login using `telnet` or `rlogin`, in addition to FTP access only if their rights and permissions give them access.

<span id="Real_Windows"></span>

## Real users on Windows

Windows real users are created locally on the server or on the domain controller with the system controls. For Windows Server, the system controls are accessed through **Control Panel &gt; User Accounts &gt; Add or remove user accounts**.

For more information on Windows users, refer to the Microsoft documentation.

> **Note:**
>
> Real users set up on the SecureTransport Edge are unable to log into either a SecureTransport Edge or SecureTransport Server. You must create a user account for each real user set up on a SecureTransport Edge to allow log ins.

> **Note:**
>
> If the account home folder prefix is on a shared network, specify a real user that has access to it. The real user must be part of the domain, not a local user for one of the cluster nodes; otherwise the other nodes in the cluster cannot impersonate it to access the shared location.

> **Note:**
>
> The specified real user needs to added in a password vault file. For more information, refer to Add a user to a password vault.

When <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is running on a Windows platform, the *Password Files* page provides an additional option to specify password vaults. A password vault stores user names and passwords of real users on Windows, is used to mimic virtual users on Windows, and is applicable only for Windows. See <a href="../t_st_passwordfiles#top" class="MCXref xref">Manage password files</a>
