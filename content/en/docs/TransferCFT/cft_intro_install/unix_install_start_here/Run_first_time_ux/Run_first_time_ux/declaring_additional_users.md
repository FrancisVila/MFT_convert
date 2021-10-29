{
    "title": "Declaring  additional users",
    "linkTitle": "Declaring additional users",
    "weight": "230"
}If Transfer CFT is to be run by users other than the holder of the account
from which Transfer CFT was installed, these users must be added to the environment.

In all subsequent definitions, it is assumed that Transfer CFT is installed,
by default, in the *cft* subdirectory of the user root directory
($HOME).

If your installation differs, you must modify the definitions provided.

### Extending the command path (PATH)

To use a Transfer CFT installed in another account, the paths pointing to the Transfer CFT &lt;installdir>/bin/, &lt;installdir>/bin/, and &lt;installdir>/runtime/src/exit/ command directories must appear in the PATH environment variable.

The actions required depend on the type of shell used. The following examples show how to add the &lt;installdir>/runtime/src/exit/ directory to the path list:

If the user shell
is *csh* (C shell), add the following command to the *~/.cshrc*
or *~/.login* file:  
set path=($path ~account\_cft/cft/bin)

If the user shell
is *sh* (BOURNE shell) or *ksh* (KORN shell), add the following
command to the *$HOME/.profile* file:  
  
PATH=$PATH:root/cft\_account/cft/bin; export PATH

where:

-   root is the
    path pointing to the user directories (usually /home)    
-   cft\_account
    is the name of the Transfer CFT installation account     

For example, if Transfer CFT is installed in the *cft* subdirectory
of the */home/transfer* account, enter the following commands:

-   For *csh*:  
    set path=($path ~transfer/cft/bin)
-   For *sh* or
    *ksh*:  
      
    PATH=$PATH:/home/transfer/cft/bin; export PATH

### Transfer CFT file access environment

To access the Transfer CFT configuration files installed in another
account, set the following environment variables defining the paths pointing
to the Transfer CFT files and directories.

#### Environment variables used by Transfer CFT

The table below lists alphabetically all the environment variables used
by Transfer CFT UNIX.

To simplify the descriptions, the variable name from this list will
be used in the remainder of this guide to refer to the environment variables
(for example, the assertion *file to which CFTCATA points* is equivalent
to *the file, the name of which is declared in the CFTCATA environment
variable*).

**Path Pointing
to the Files**

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>            <p><strong>Environment variable</strong> </p></th>
         <th>            <p><strong>Default definition</strong>
 </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTDIRINSTALL         </td>
         <td data-valign="top">Top of the Transfer CFT installation directory structure         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTDIRRUNTIME         </td>
         <td data-valign="top">Runtime directory         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTUCONF         </td>
         <td data-valign="top">UCONF file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTDIRDAT         </td>
         <td data-valign="top">Data directory         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTDIRINS         </td>
         <td data-valign="top">Conf directory         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTDIRLOG         </td>
         <td data-valign="top">Log directory         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTDIRPUB         </td>
         <td data-valign="top">Pub directory         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTDIRSEC         </td>
         <td data-valign="top">Security directory         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTDIREXEC         </td>
         <td data-valign="top">Exec directory         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTPKIDIR         </td>
         <td data-valign="top">Directory containing the security information         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTPKIDIR         </td>
         <td data-valign="top">Exit directory         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTDIRAPI         </td>
         <td data-valign="top">Api directory         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTHICNF         </td>
         <td data-valign="top">Security system initialization file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTDSPCNF         </td>
         <td data-valign="top">Display configuration file         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTKEY         </td>
         <td data-valign="top">License key file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTACNT         </td>
         <td data-valign="top">Accounting file         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTACNTA         </td>
         <td data-valign="top">Alternate accounting file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTCATA         </td>
         <td data-valign="top">Catalog file         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTTCOM         </td>
         <td data-valign="top">Communication file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTLOG         </td>
         <td data-valign="top">Log file         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTLOGA         </td>
         <td data-valign="top">Alternate log file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTPARM         </td>
         <td data-valign="top">Parameter file         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTPART         </td>
         <td data-valign="top">Partner file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTPKU         </td>
         <td data-valign="top">PKI file         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top">CFTHINI         </td>
         <td data-valign="top">Security system implementation file         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top">CFTHPARM         </td>
         <td data-valign="top">Security system implementation parameter file         </td>
      </tr>
   </tbody>
</table>

#### Setting the environment variables

In BOURNE shell (sh) or KORN shell (ksh), depending on your operating requirements, you must create the following commands in a file with the same strategy as the $CFTDIRUNTIME/profile file created by default during the installation procedure or add them to the $HOME/.profile file:

CFTDIRINSTALL=&lt;path pointing to Transfer CFT installation directory>

CFTDIRRUNTIME=&lt;path pointing to Transfer CFT runtime directory>

CFTUCONF=$CFTDIRRUNTIME/data/cftuconf.dat

. $CFTDIRINSTALL/distrib/dat/profile.inc

# Set Directories for user Convenience

\_EXPORT CFTDIRDAT $CFTDIRRUNTIME/data

\_EXPORT CFTDIRINS $CFTDIRRUNTIME/conf

\_EXPORT CFTDIRLOG $CFTDIRRUNTIME/log

\_EXPORT CFTDIRPUB $CFTDIRRUNTIME/pub

\_EXPORT CFTDIRSEC $CFTDIRINSTALL/distrib/am

\_EXPORT CFTDIREXEC $CFTDIRRUNTIME/exec

\_EXPORT CFTPKIDIR $CFTDIRRUNTIME/conf/pki

\_EXPORT CFTDIREXIT $CFTDIRRUNTIME/src/exit

\_EXPORT CFTDIRAPI $CFTDIRRUNTIME/src/capi

# Set CFT Logical Names From Uconf (For information Only)

# CFTACNT \`cftuconf cft.cftaccnt.fname\` # Accounting File

# CFTACNTA \`cftuconf cft.cftaccnt.afname\` # Alternate Accounting File

# CFTCATA \`cftuconf cft.cftcat.fname\` # Catalog Database

# CFTCOM \`cftuconf cft.cftcom.fname\` # Communication Media File

# CFTLOG \`cftuconf cft.cftlog.fname\` # Log File

# CFTLOGA \`cftuconf cft.cftlog.afname\` # Alternate Log File

# CFTPARM \`cftuconf cft.cftparm.fname\` # Parameter Database

# CFTPART \`cftuconf cft.cftparm.partfname\` # Partners Database

# CFTPKU \`cftuconf cft.cftparm.pkifname\` # PKI Database

# CFTHINI \`cftuconf cft.cftparm.habfname\` # Access Management Control File

# CFTHPARM \`cftuconf cft.cftparm.secparm\` # Access Management Database

# Helper Environment Variables

\_EXPORT CFTHICNF $CFTDIRRUNTIME/conf/default.sei

\_EXPORT CFTDSPCNF $CFTDIRRUNTIME/conf/dspcnf.xml

\_EXPORT CFTKEY $CFTDIRRUNTIME/conf/cft.key

\_EXPORT CFTCONF $CFTDIRRUNTIME/conf/cft.conf

PATH=$PATH:$CFTDIRINSTALL/bin:$CFTDIREXIT:$CFTDIRAPI

export PATH

In C shell (csh), add the following commands to the *~/.cshrc*
or *~/.login* file, with the following format:

setenv &lt;variable> &lt;descriptor>

For example, for the CFTCATA variable, you get:

setenv CFTCATA $CFTDIRRUNTIME/data/cft\_cata

### Privileges and rights

All system users, irrespective of their user identifiers (*uid*)
and group identifiers (*gid*), can theoretically communicate with
another Transfer CFT started by a different user.

The only constraint is the rights that they have when accessing Transfer
CFT configuration files. The minimum requirement is:

-   Write access rights
    for the communication file to which the CFTTCOM environment variable points
-   Read access rights
    for all files to which the other Transfer CFT environment variables point
-   Read access rights
    for all Transfer CFT programs
-   Read and execute
    access rights for all procedures written in a shell
