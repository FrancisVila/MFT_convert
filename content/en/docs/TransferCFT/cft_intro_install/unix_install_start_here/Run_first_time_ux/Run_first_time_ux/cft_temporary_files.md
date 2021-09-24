{
    "title": "Transfer CFT temporary files",
    "linkTitle": "Transfer CFT temporary files",
    "weight": "280"
}# <span id="CFT_temporary_files"></span>Transfer CFT temporary files

Depending on the processing involved, Transfer CFT creates various temporary
files in the */tmp* directory. This topic describes temporary files,
how to delete them, and provides an example.

## Temporary files

### Transfer CFT temporary files

There are four types of temporary files corresponding to different types
of actions:

-   */tmp/cftlo\**
    files are produced during the log switching procedure
-   */tmp/cftcn\**
    files are produced when the accounting feature is enabled
-   */tmp/cftsu\**
    files are produced when end of transfer procedures are run
-   */tmp/cftsu\*.err*
    files correspond to the results of commands in the *cftsu\** files

### Deleting temporary files

Transfer CFT cannot delete temporary files automatically. It does not
know exactly when the end of the user script is reached.

To avoid saturating the /tmp directory, you should end any shell
procedure with the rm $0 command.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">
 If this command is omitted, the <span>/tmp</span> partition rapidly becomes 
 full and the end of transfer procedures fails.         </td>
      </tr>
</table>

This command deletes the procedure that runs it and is applicable to
*cftlo\*, cftfcn*\* and *cftsu*\* files.

Additionally, the *cftsu\*.err* files associated with *cftsu\**
files should be deleted. However, to avoid losing any errors that may
be logged in this file, it is best to check that the file is empty before
deleting it.

For example, enter:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>if test -s $0.err<br/>then<br/>echo $0.err contains data to be consulted<br/>else<br/>rm $0.err<br/>fi</p>
         </td>
      </tr>
   </tbody>
</table>

### TMPDIR environment variable

You can use the environment variable TMPDIR=&lt;path> to define a temporary directory in Unix and POSIX. If you define TMPDIR, the temporary file goes in this directory. If you do not define TMPDIR, Transfer CFT uses the default directory (/tmp).

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>export TMPDIR=/home/Desktop/tmpdir/         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You must restart Transfer CFT if you change the <span>TMPDIR </span>value.         </td>
      </tr>
</table>

### Sample procedure

The contents of the recvm.cmd file stored in &lt;installdir>/runtime/conf/ are
shown below. The recvm.cmd file is a sample procedure executed
after receiving a message.

This procedure must first be declared in the CFTPARM section of your
configuration file, in the EXECRM field, so that it can be executed.

Example

<table cellspacing="0">
   <col/>
      <tr>
         <td>
            <p> </p>
            <p>     EXECRM = '/home/transfer/cft/&lt;installdir&gt;/runtime/conf//recvm.cmd'</p>
            <p>The contents of the recv.cmd file are as follows:</p>
            <p>echo "MESSAGE RECEIVED"     /* display 
 of the message received */</p>
            <p>echo "** &amp;msg **"      /* by CFT using 
 the &amp;msg symbolic */</p>
            <p>     /* variable that contains the */</p>
            <p>     /* message text */</p>
            <p>  </p>
            <p>rm $0      /* deleting the /tmp/cftsu* */</p>
            <p>     /* temporary file */<br/><br/>if test -s $0.err<br/>then<br/>echo $0.err contains data to be consulted<br/>else<br/>rm $0.err<br/>fi</p>
<h3> </h3>
         </td>
      </tr>
</table>

### Transfer CFT identification

Some clients package Transfer CFT/UNIX to meet the special requirements
of their company. This specific package can apply to both the product
in its ready-to-install state, as delivered by Axway, and the product
specifically preconfigured for the company.

To make it easier to identify this type of product, a specific directory
is available on the delivery medium and product following installation.
This directory is called *.info (*the dot must be included before
the name).

This *.info* directory is located:

-   *For
    the installable product*, on the same level as the other product files
    to install
-   *For
    the installed product*, in the subdirectory in which Transfer CFT/V2/UNIX
    was generated, in the examples provided in this guide, this is the *cft*
    directory

This directory comprises a series of subdirectories ending with an empty
file. These various levels provide the information below in the following
order:

-   Transfer CFT release,
    cft240 for example
-   Product generation
    date, 20060307 for example
-   Operating system,
    AIX for example
-   Operating system
    release, for example, for AIX: 43
-   If necessary, the
    hardware manufacturer, for example, for AIX: IBM

Taking the examples above, the complete directory structure is as follows:

     .info/cft240/20060307/AIX/43/IBM

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This directory and the information it contains are also used by Transfer 
 CFT. As some utilities are very similar from one product release to another, 
 the release information is retrieved to fine-tune the way in which the 
 utilities behave.         </td>
      </tr>
</table>
