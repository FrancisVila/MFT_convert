{
    "title": "Perform a manual migration",
    "linkTitle": "Perform a manual migration",
    "weight": "200"
}After performing a Transfer CFT 3.9 installation, you should update to the most recent service pack.

You require a new license key if you are migrating from a version 2.x Transfer CFT to a version 3.x.

## Check the impact of new features

Before starting the migration, we highly recommend that you review the features changes listed in [Migration or upgrade impact and considerations](../../../)

## System requirements

Transfer CFT on Windows requires the **Visual C++ Redistributable Package for Visual Studio 2019** for proper functioning. This provides the necessary library files (DLL) for Transfer CFT. You must install `vcredist_x64.exe` prior to installing or upgrading Transfer CFT.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the redistribution package is already installed on your Windows system, there is no need to reinstall.         </td>
      </tr>
</table>

## Install Transfer CFT 3.9

Perform a Transfer CFT installation, as described in the OS-specific installation section.

## Load the environment

Before beginning a standard migration procedure, you must load the old Transfer CFT environment.

### Windows procedure

#### Transfer CFT 2.4

There is no profile file for Transfer CFT 2.4 in Windows.

To execute a command you must be in the correct directory. Therefore, before starting the migration, change the directory to the version-appropriate Transfer CFT installation directory.

#### Transfer CFT 2.5 and higher

From the console, change the directory to the Transfer CFT runtime directory and execute the profile file using the command: profile.bat

After loading the profile, you can execute commands from anywhere.

### UNIX procedure

#### Transfer CFT 2.4

From the console, execute the profile file for your version of Transfer CFT, which is by default located in the home directory. Enter: . ./ENV\_CFT

#### Transfer CFT 2.5 and higher

From the console, change directory to the Transfer CFT runtime directory and execute the profile file using the command: . ./profile

After loading the profile, you can execute commands from anywhere.
