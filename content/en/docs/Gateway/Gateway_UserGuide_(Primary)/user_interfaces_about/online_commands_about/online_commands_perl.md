{
    "title": "Online commands in Perl",
    "linkTitle": "Online commands in Perl",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: User Interfaces

## GIK Perl overview

Axway Gateway provides two GIK Perl Command module extensions for Perl Version 5.24.0. These modules enable you to run Gateway command lines from a Perl script:

-   <span style="font-weight: bold;">GIKCMDPL</span>: module for <span style="font-style: italic;">local</span> command calls
-   <span style="font-weight: bold;">GIKCCMDPL</span>: module for <span style="font-style: italic;">remote</span> command calls

### Syntax

Use the following command-line syntax:

GIKCMDPL::cmd('command line')

or

GIKCCMDPL::cmd('command line')

## Using Perl modules

The Perl modules use the <span class="code" style="font-weight: bold;">cmd(…)</span> command. To execute a command, perform the following steps (detailed below):

1.  Invoke the GIKCMDPL or GIKCCMDPL module.
2.  Open the session.
3.  Execute the command.
4.  Close the session.

The Perl modules comprise the following routines.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Routine</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Int openSession(char *, char *, char *) ;</p>         </td>
         <td><p>To open a session</p>         </td>
      </tr>
      <tr>
         <td><p>Int closeSession() ;</p>         </td>
         <td><p>To close a session</p>         </td>
      </tr>
      <tr>
         <td><p>Int cmd(char *) ;</p>         </td>
         <td><p>To run a command line</p>         </td>
      </tr>
      <tr>
         <td><p>Void printErrMsg() ;</p>         </td>
         <td><p>To display the error output</p>         </td>
      </tr>
      <tr>
         <td><p>Int getNumVar(char *)</p>         </td>
         <td><p>To retrieve numeric symbolic variables</p>         </td>
      </tr>
      <tr>
         <td><p>Char *getStringVar(char *) ;</p>         </td>
         <td><p>To retrieve alphanumeric symbolic variables</p>         </td>
      </tr>
      <tr>
         <td><p>Char **getResult() ;</p>         </td>
         <td><p>To retrieve the results array</p>         </td>
      </tr>
   </tbody>
</table>

### Invoking the Perl module

To invoke the GIKCMDPL or GIKCCMDPL module, both a Perl environment and the module must be installed on the same platform as <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.

Use either of the following call syntaxes in a Perl script:

#importing the GIKCMDPL module

use GIKCMDPL ;

or

#importing the GIKCCMDPL module

use GIKCCMDPL ;

### Opening and closing a session

To initialize the Perl environment, call the <span style="font-weight: bold;">openSession</span> routine. If security is enabled, you must define the <span style="font-weight: bold;">openSession</span> command input parameters.

The <span style="font-weight: bold;">openSession</span> routine requires three parameters, including the user name and password. The first parameter is reserved for future use.

openSession('future use', 'user', 'password')

If security is enabled:

$rc = openSession(' ', 'user', 'password') ;

If security is disabled:

$rc = openSession(' ', ' ', ' ') ;

Before exiting the Perl script, call the <span style="font-weight: bold;">closeSession</span> routine to close the session and release memory space.

<span style="font-weight: bold;">Note:</span> You do not need to open a session for the <span class="code" style="font-weight: bold;">pel</span><span class="code" style="font-weight: bold;">dconf</span> (<span style="font-style: italic;">deprecated</span>) or <span class="code" style="font-weight: bold;">pelmon</span> commands.

### Executing commands

The GIKCMDPL module is based on <span style="font-style: italic;">local</span> online commands.

The GIKCCMDPL module is based on <span style="font-style: italic;">remote</span> online commands.

The following table lists the commands available for each module.

<table>
   <tbody>
      <tr>
         <td><p>Command</p>         </td>
         <td><p>Available for:</p>         </td>
      </tr>
      <tr>
         <td><p>GIKCMDPL</p>         </td>
         <td><p>GIKCCMDPL</p>         </td>
      </tr>
      <tr>
         <td><p>peladm</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>peldsp</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>pelbase</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>pelctl</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>pelpur</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>peltrans</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>pelmon</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td><p>pelmig</p>         </td>
         <td><p>No</p>         </td>
         <td><p>No</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">peldconf</span> (<span style="font-style: italic;">deprecated</span>)</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>vfdadm</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>vfddsp</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>secadm</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
      <tr>
         <td><p>secdsp</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Yes</p>         </td>
      </tr>
   </tbody>
</table>

### Syntax

The call syntax of the <span class="code" style="font-weight: bold;">cmd</span> function is:

Int cmd('command line')

The command line passed as an argument is parsed and processed. The function returns 0 if the command line executed successfully. Otherwise, the return code is negative.

If the return code is negative, use the void <span style="font-weight: bold;">printErrMsg()</span> function to display the corresponding error message.

#### peltrans commands

The <span class="code" style="font-weight: bold;">peltrans</span> commands return the Transfer identifier if processing was successful, or a negative value if processing failed.

#### peldsp commands

The <span class="code" style="font-weight: bold;">peldsp</span> commands include the <span class="code" style="font-weight: bold;">–st</span> option, which is used to set internal symbolic variables. For example:

$rc = GIKCMDPL::cmd('peldsp select\_site –st');

If you use a <span class="code" style="font-weight: bold;">select</span> sub-command with the <span class="code" style="font-weight: bold;">–st</span> option, you can then use the <span style="font-weight: bold;">getResult()</span> function to retrieve the symbolic variables. This function returns an array containing the information requested during the command.

For example:

#results array display

@result=GIKCMDPL::getResult();

for $i ( 0 .. $#result ) {

print "\\t $result\[$i\], \\n";

}

The following example shows a <span class="code" style="font-weight: bold;">display</span> sub-command that uses the <span class="code" style="font-weight: bold;">–st</span> option.

$rc = GIKCMDPL::cmd('peldsp display\_site –a LOOPPHSE –st');

If you use a <span class="code" style="font-weight: bold;">display</span> sub-command with the <span class="code" style="font-weight: bold;">–st</span> option, you can access the symbolic variables via the <span style="font-weight: bold;">getStringVar('var')</span> and <span style="font-weight: bold;">getNumVar('var')</span> functions, as described in the following section.

### Accessing internal symbolic variables

Use the command <span class="code" style="font-weight: bold;">peldsp display\_xxx –st</span> to create symbolic variables. All internal variables conform to the following syntax:

peldsp display\_object … –st

This command makes the internal variables available:

object.attribute

For example: <span class="code" style="font-weight: bold;">site.alias</span>.

There are two types of internal variable: numeric and alphanumeric. To access both types of variable, the call functions are as follows:

<span class="code" style="font-weight: bold;">getNumVar('variable name')</span> - for numeric variables

<span class="code" style="font-weight: bold;">getStringVar('variable name')</span> - for alphanumeric variables

If errors occur, use the <span style="font-weight: bold;">printErrMsg()</span> function. For example, if a numeric value returns a negative value or if a variable is not set for an alphanumeric variable, and so on.

#retrieving internal variables

GIKCMDPL::cmd(" peldsp display\_site –a LOOPPHSE –st ");

$alias = GIKCMDPL::getStringVar(" site.alias ");

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
