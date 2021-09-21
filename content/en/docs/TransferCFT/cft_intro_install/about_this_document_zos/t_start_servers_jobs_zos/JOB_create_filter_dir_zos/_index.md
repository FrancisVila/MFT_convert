{
    "title": "Set up optional features",
    "linkTitle": "Set up optional features",
    "weight": "220"
}You can optionally set up log and catalog filters in Copilot using the JCL described in this section.

The JCL **COPFILTR** lets you create a directory under the USS to store the Copilot catalog and log filters. This server directory has read, write, and delete rights for Transfer CFT Copilot users, but is independent of the Copilot component directory.

## Creating a filter directory

You use the following JCL and statements to create a filter directory.

### Defining the directory

You will need to enter the directory name twice for the following:

-   STP001 - To create the directory
-   STP002 - To initialize the variable copilot.general.persistencedir

**Example**

You can use the following example as a reference for creating your directory.  In this example, we used **` /home/COPILOT/runtime/persist`  as the new directory.**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>//*</p>
            <p>// SET P='/home/COPILOT/runtime/persist'</p>
            <p>//*</p>
            <p>//STP001 EXEC PGM=BPXBATCH,</p>
            <p>// PARM='SH mkdir -p -m 774 &amp;P'</p>
            <p>//STDIN DD DUMMY</p>
            <p>//STDOUT DD SYSOUT=*</p>
            <p>//STDERR DD SYSOUT=*</p>
            <p>//*</p>
            <p>//* Set variable: copilot.general.persistencedir</p>
            <p>//*</p>
            <p>//STP002 EXEC PCFTUTIL,PARM='/1=&amp;P'</p>
            <p>//CFTIN DD *</p>
            <p>UCONFSET ID=copilot.general.persistencedir,</p>
            <p>VALUE='%_ARGV1%'</p>
            <p>/*</p>
         </td>
      </tr>
   </tbody>
</table>
