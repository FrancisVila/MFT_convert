{
    "title": "Expression examples",
    "linkTitle": "Expression examples",
    "weight": "350"
}This topic provides additional examples on expression usage. In this topic, sample variable values are given to show how various expressions can use the information. The examples provided in this topic apply to:

-   Transfer site post-transmission actions
-   Subscription post-transmission actions
-   PGP
-   Account templates

For a complete listing of the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> Expression Language (EL) functions and variables, refer to <a href="../../c_st_advanced_routing/r_st_custom_el_functions_variables" class="MCXref xref">Custom Expression Language functions and variables</a>.

## Expression variables and examples

The following table provides the variable names and values that are used in the subsequent examples:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Variable name         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>DXAGENT_LOGINNAME</code>         </td>
         <td><code>stuser</code>         </td>
      </tr>
      <tr>
         <td><code>DXAGENT_HOMEDIR</code>         </td>
         <td><code>/home/users/stuser</code>         </td>
      </tr>
      <tr>
         <td><code>DXAGENT_TARGET</code>         </td>
         <td><code>document_12.txt</code>         </td>
      </tr>
      <tr>
         <td><code>DXAGENT_TARGETPATH</code>         </td>
         <td><code>/home/users/stuser</code>         </td>
      </tr>
      <tr>
         <td><code>DXAGENT_TRANSFORMATION_INPUT</code>         </td>
         <td><code>/home/users/stuser/PGP/encrypted.pgp</code>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> The variable DXAGENT\_TRANSFORMATION\_INPUT is only available from within a PGP transformation agent. Expressions using this variable do not evaluate correctly in other cases. In the example using this variable, assume that the original file name before encryption is original\_12.txt.

The following table shows additional examples of the different expressions available for use in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Example variable name         </th>
<th class="HeadD-Column1-Header1">Example return value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>${env['DXAGENT_TARGET']}</code>         </td>
         <td><code>document_12.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv['target']}</code>         </td>
         <td><code>document_12.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv["target"]}</code>         </td>
         <td><code>document_12.txt</code>         </td>
      </tr>
      <tr>
         <td><code>Prefix${stenv["target"]}.newext</code>         </td>
         <td><code>Prefixdocument_12.txt.newext</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.targetpath}</code>         </td>
         <td><code>/home/users/stuser</code>         </td>
      </tr>
      <tr>
         <td><code>${basename(stenv.target)}</code>         </td>
         <td><code>document_12</code>         </td>
      </tr>
      <tr>
         <td><code>${extension(stenv.target)}</code>         </td>
         <td><code>txt</code>         </td>
      </tr>
      <tr>
         <td><code>${filename(stenv.target).replace('[0-9]','z').replace('[*&amp;_]','-')}</code>         </td>
         <td><code>document-zz.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${basename(stenv.target)}-${random}.${extension(stenv.target)}</code>         </td>
         <td><code>document_12-C7F2119AAECEACCDE16C496C96FEEE39.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.loginname.replace('st', 'SecureTransport-')}</code>         </td>
         <td><code>SecureTransport-user</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.target.matches('.*.txt') ? 1 : 0}</code>         </td>
         <td><code>1</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.target.matches('.*.pgp') ? 1 : 0}</code>         </td>
         <td><code>0</code>         </td>
      </tr>
      <tr>
         <td><code>${stenv.transformation_input.matches('\*.pgp') ? 1 : 0}</code><br />
         </td>
         <td><code>1</code>         </td>
      </tr>
      <tr>
         <td><code>${embedded}</code>         </td>
         <td><code>original_12.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${basename(embedded)}-${timestamp}.${extension(embedded)}</code>         </td>
         <td><code>original_12-1345652729052.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${basename(embedded)}-${date('yyyy.MM.dd_hhmmss')}.${extension(embedded)}</code>         </td>
         <td><code>original_12-2012.08.22_162529.txt</code>         </td>
      </tr>
      <tr>
         <td><code>${resolve(concat(stenv.homedir, '../..'))}</code>         </td>
         <td><code>/home</code>         </td>
      </tr>
      <tr>
         <td><code>${empty var ? error('Missing Variable') : var}</code>         </td>
         <td>Either the value of <code>$var</code> or an exception         </td>
      </tr>
   </tbody>
</table>
