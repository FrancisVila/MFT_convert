{
    "title": "Compiling C user exits",
    "linkTitle": "Compiling C user exits",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Customizing Gateway Processes

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <strong><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">customizing user exits</span>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

This topic describes how to compile the C language external user exits that you modify for use with Gateway.

This information is intended for application programmers familiar with the C programming language. It does not discuss the C language, the C run-time library or the C execution environment (compiler and system dependencies). Refer to public reference manuals on C language, and to your platform documentation, for detailed information on this programming language.

### Exit file locations

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>File (extension)</p>         </th>
<th class="HeadD-Column1-Header1"><p>Location</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Exit header files (<span class="code">.h</span>)</p>         </td>
         <td><p><span class="code">&lt;Gateway installation directory&gt;</span><span class="code" style="font-weight: bold;">/inc</span></p>         </td>
      </tr>
      <tr>
         <td><p>Exit source files (<span class="code">.c</span>)</p>         </td>
         <td><p>sub-directories in<br />
<span class="code">&lt;Gateway installation directory&gt;</span><span class="code" style="font-weight: bold;">/src</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="How_to_compile_and_link_C_user_exits__Windows_NT"></span>

### How to compile and link C user exits: Windows

Go to the directory <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">\\run\_time\\etc\\</span> and use the script <span class="code" style="font-weight: bold;">profile.bat</span> to load the appropriate environment variables for the operating system.

In the directory where the exit file was modified, execute:

nmake /f Makefile

<span id="How_to_compile_and_link_C_user_exits__Unix"></span>

### How to compile and link C user exits: UNIX

Go to the directory <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/src</span> and use the script <span class="code" style="font-weight: bold;">userprof.sh</span> to load the appropriate environment variables for the operating system.

If you want to compile and link all the exits to Gateway programs, enter:

userbuild.sh

If you want to compile only part of them, enter:

make xxxxxx

where:

<span class="code">xxxxxx</span> = one of the following:

-   exitclnt
-   exituser
-   exitsecs
-   exitsech
-   exitc
-   exitrte
-   perlstub

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
