{
    "title": "Define additional environment variables",
    "linkTitle": "Define additional environment variables",
    "weight": "270"
}When loading the Transfer CFT profile, files that are stored in the `profile.d` directory are also executed, and all defined environment variables are then available in the current environment. This enables you to use these variables in the Transfer CFT configuration or processing scripts.

When loading the profile, the files that are loaded depend on if you are using Batch or PowerShell:

-   profile.bat: only .bat files are loaded
-   profile.ps1: only .ps1 files are loaded

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">When executing <span>cft </span>commands such as CFTUTIL or PKIUTIL in PowerShell, you must remove all spaces surrounding the comma (,). For example, instead of the command <span>CFTUTIL send part=paris<span> ,</span> idf=test</span> enter <span>CFTUTIL send part=paris<span>,</span>idf=test.</span>         </td>
      </tr>
</table>

## How to define additional Transfer CFT environment variables

1.  In the %CFTDIRRUNTIME%/profile.d directory, create a new file with .bat as the suffix. In this file, add your customized variables as follows. For example:  
    set MYVARIABLE01=TheVariableValue01  
    set MYVARIABLE02=TheVariableValue02
2.  Execute the profile command.

See also, [Windows-specific system functions](../../specific_system_functions).
