{
    "title": "Post-migration procedure",
    "linkTitle": "Post-migration procedure",
    "weight": "240"
}## Post manual migration or auto import

If you performed an install and auto import or a manual migration, you must manually import compiled objects and exec scripts from the old configuration. There are no Transfer CFT commands to import these compiled objects and exec scripts, and they are not included in the auto import process.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">After completing an upgrade or a migration procedure, you must update to the most recent SP.          </td>
      </tr>
</table>

### Compiled objects: APIs and Exits

To manually migrate your API and exit binary files after migrating, copy your program's source code to the new Transfer CFT 3.9 runtime directory and compile them.

1.  Copy the API source code to &lt;new\_Transfer CFT\_3.9\_installation\_dir>/runtime/src/capi and compile.

<!-- -->

1.  Copy the Exit source code to &lt;new\_Transfer CFT\_3.9\_installation\_dir>/runtime/src/exit and compile.

### Exec scripts

Copy the exec scripts to &lt;new\_Transfer CFT\_3.9\_installation\_dir>/runtime/exe. It is important that you update any paths that you were using in the exec scripts to reflect the new installation directory.

## Post-manual migration only

### Migrating UCONF parameters from a previous Transfer CFT version

You must manually migrate UCONF parameters for versions prior to Transfer CFT 2.5.1. The UCONF configuration
replaces the following configuration files:

-   Sentinel configuration
    file (trkapi.cfg, trkapi.conf, and so on...)  
    The parameters in the Sentinel file are integrated
    in UCONF as sentinel.FORMER-PARAMETER-NAME. For example, TRKTNAME becomes
    sentinel.TRKTNAME.
-   Copilot ini file
    (copconf.ini)  
    This file no longer exists. All former Copilot parameters are named copilot.SECTION.PARAMETER-NAME in the UCONF interface. For example, the parameter ServerPort, located in the general section, is now copilot.general.serverport.
-   The profile file, formerly ENV\_CFT or cft.ini, now
    uses UCONF to set the environment variables.

## Post upgrade

If you performed an upgrade, you need only recompile your APIs and Exits.
