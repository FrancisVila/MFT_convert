{
    "title": "SecureTransport specific named variable sets",
    "linkTitle": "SecureTransport specific named variable sets",
    "weight": "310"
}Named variable sets separate variables into logical groups. Named variable sets use the following syntax:

`${name['variable']}`

or

`${name.variable}`

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses the following named variable sets:

-   `${sess['variable']}` – used with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> session variables including LDAP
-   `${env['variable']}`, `${stenv['variable']}`, or `${stenv.variable}` – used with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> predefined environment variables
-   `${pesit['variable']}` – used with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> PeSIT variables described in <a href="../r_st_expressionlanguagepesitvariables" class="MCXref xref">PeSIT variables</a>

LDAP session variables can be used with the `sess` named variable set. You can also develop an agent that contains the session variables you want to use. All session variables must be prefixed with `STSESSION_`.

The `env` named variable set contains the entire environment, including any non- <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific variables. Environment variables accessed using `stenv` are preprocessed to remove the `DXAGENT_` prefix, and upper case characters are converted to lower case characters. For example, to use the environment variable `DXAGENT_TARGET`, write the following expression:

`${env['DXAGENT_TARGET']}`

or use the `stenv` named variable set and access the variable as:

`${stenv['target']} or ${stenv.target}`

## <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific named variable set examples

The following table shows examples of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific named variables:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Example         </th>
<th class="HeadD-Column1-Header1">Example return value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>${sess['STSESSION_LDAP_DIR_homeDirectory']}</code>         </td>
         <td><code>/home/user1</code>         </td>
      </tr>
      <tr>
         <td><code>${sess['STSESSION_LDAP_DN']}</code>         </td>
         <td><code>cn=john,ou=People,dc=tp,dc=axway,dc=com</code><br />
         </td>
      </tr>
      <tr>
         <td><code>${sess['STSESSION_LDAP_DIR_uidNumber']}</code>         </td>
         <td><code>1000</code>         </td>
      </tr>
      <tr>
         <td><code>${env['DXAGENT_HOMEDIR']}</code>         </td>
         <td><code>/home/user2</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv['homedir']}</code>         </td>
         <td><code>/home/user2</code>         </td>
      </tr>
      <tr>
         <td><code>${env['DXAGENT_FULLSOURCE']}</code>         </td>
         <td><code>/st/monitor/download/test.xml</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv['fullsource']}</code>         </td>
         <td><code>/st/monitor/download/test.xml</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.rawsource}</code>         </td>
         <td><code>AS2OriginalFile</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.site_target}</code>         </td>
         <td><code>OriginalFile</code>         </td>
      </tr>
   </tbody>
</table>
