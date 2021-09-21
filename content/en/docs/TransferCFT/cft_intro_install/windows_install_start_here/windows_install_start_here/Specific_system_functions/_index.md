{
    "title": "Specific system functions",
    "linkTitle": "Specific system functions",
    "weight": "220"
}This section describes specific system functions when using Transfer CFT
in Windows. It begins with this topic, which introduces the use of environmental
variables.

## <span id="About_environment_variables"></span>About environment variables

The operating system environment variables have an important role in
Transfer CFT. In the standard Transfer
CFT parameter setting, these variables establish the correspondence
between the logical name and the physical name for all file names. The
user uses the environment variable by prefixing its name with the character
‘$’. The variable name that corresponds to the logical file name is developed
into the physical name.

Example

The environment variable \[FULL\_NAME\] provides a definition
to the operating system as follows:

FULL\_NAME=C:\\REP0\\REP1\\FILE.SUF which is used as follows by the Transfer
CFT parameterization: FNAME = $FULL\_NAME

The implementation of a certain number of non-standard functions is
shown in [Windows specific system functions](#). These
functions are mostly system functions, but include some network functions.

#### Using the SET command

The environment variables are set by the SET command, called beforehand
in the same session as the CFTMAIN or CFTUTIL executable.

#### Using the profile.bat file

You can set the equivalent environment variables using the `profile.bat` file located in the Transfer CFT runtime folder.
For example, the CFTNODEL setting would be:
`SET CFTNODEL=YES`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For more information, see <a href="env_variables_and_specific_parms">Environment 
 variables and specific parameters.</a>         </td>
      </tr>
</table>