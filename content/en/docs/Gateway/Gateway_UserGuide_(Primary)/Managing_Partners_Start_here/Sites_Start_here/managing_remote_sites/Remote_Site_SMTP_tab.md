{
    "title": "New Remote Site: SMTP tab",
    "linkTitle": "SMTP tab",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Alphanumeric X-Priority (SEPAMail)</strong>         </td>
         <td>Check this option to indicate that the <strong>X-Priority</strong> header should take alphanumeric values (<em>HIGHEST</em>, <em>HIGH, NORMAL, LOW, LOWEST</em>). If left unchecked, the header will take numeric values (1 to 5).         </td>
      </tr>
      <tr>
         <td><p>Authentication method</p>         </td>
         <td><p>Select the authentication method to use when connecting to the SMTP server:</p>
<ul>
<li><span style="font-weight: bold;">None</span> (default)</li>
<li><span style="font-weight: bold;">Plain</span></li>
<li><span style="font-weight: bold;">Login</span> (provide user and password)</li>
<li><span style="font-weight: bold;">Anonymous</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Login identification</p>         </td>
         <td><p>Enter the user login name.<br />
Maximum: 24 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Set Login password</p>         </td>
         <td><p>Opens a dialog box to enter the user login password.<br />
Maximum: 14 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Default email address</p>         </td>
         <td><p>Enter the default destination email address (<span style="font-weight: bold;">To</span>) for the Remote Site.<br />
Maximum: 128 characters.</p>
<p>The address that you enter in this field is only used if you do not define a destination email address in the Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p>Attach file</p>         </td>
         <td><p>Check this option to indicate whether or not to attach a file by default. If you check this option, Gateway creates an email and attaches the file. Do not check this option if the file to transfer is already formatted as an email.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About SMTP/POP3](../../../../protocols_about/smtp_pop3_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
