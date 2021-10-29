{
    "title": "Folder monitoring IBM i native files",
    "linkTitle": "Folder monitoring IBM i native files",
    "weight": "200"
}This section describes the IBM i native file folder monitoring specificities. The IBM i native files folder monitoring mechanism is the same as [Scheduled folder monitoring](transfercft/app_integration_intro/intro_folder_monitor): Transfer CFT periodically checks the status of native files (\*FILE objects) in a defined library to see if there are transfer candidates.

## Support

Native file monitoring supports:

-   All filtering methods are supported - STRJCMP, WILDMAT, REGEXP.
-   The file method with a file having the same name as the scanned file, which is created in the Working library. This file has a unique member called met that hosts metadata.
-   The move method with or without timestamps.
-   The RENAMEMETHOD parameter's TIMESTAMP option (MOVE method). However, due to file name limitation the timestamp is shorter than as described in [CFTFOLDER](../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftfolder).

## Limitations

-   You can only transfer native files between libraries. Transfer CFT does not monitor any other object (e.g. program, data area,...).
-   Since there is no directory structure in libraries, you cannot set the IDF and PART to be named after directories as described in the CFTFOLDER object. (You must explicitly define these parameters for each CFTFOLDER object dedicated to native file monitoring.)
-   You can only transfer single member files. If a file contains several members, only the first member is transferred.

## Procedure

To monitor the creation of native files in a library:

1.  Define the scanned library using the scanning directory parameter (SCANDIR).
2.  Create a working library to take the place of the working directory, and define (WORKDIR).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Both libraries must exist, and you cannot mix libraries and IFS directories.         </td>
      </tr>
   </tbody>
</table>

Example

Below the CFTFOLDER object uses CFTFOLD1 as the scanning directory, and CFTWRK1 as the working directory (library).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTFOLDER MODE=REPLACE,</p>
            <p>ID=CFTFOLD1,</p>
            <p>STATE=ACTIVE,</p>
            <p>METHOD=MOVE,</p>
            <p>RESUBMITCHANGES=YES,</p>
            <p>FILEIDLEDELAY=5,</p>
            <p>IDF=BIN,
PART=PARIS,</p>
            <p>SCANDIR=<span>CFTFOLD1</span>,</p>
            <p>WORKDIR=<span>CFTWRK1</span>,</p>
            <p>RENAMEMETHOD=TIMESTAMP</p>         </td>
      </tr>
   </tbody>
</table>

## Timestamp conventions

Files are limited to 10 characters starting with a letter, where the first letter of the moved file is that of the original file. The timestamp comprises the 9 remaining characters and has the pattern YDDDSSSSS (Y: last digit of the year, D: day of the year, S: second in the day).

Since file names are not preserved when using a timestamp, the original file and library are set in the TEXT field of the file. You can use the either MOVE without TIMESTAMP or FILE method to preserve the name of the original file.
