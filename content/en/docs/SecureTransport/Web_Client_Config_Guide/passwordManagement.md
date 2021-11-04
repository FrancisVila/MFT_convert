{
    "title": "Password Management",
    "linkTitle": "Password Management",
    "weight": "200"
}Use the `"passwordManagement"` section to override few restrictions for password management options on the sign-in screen.


    {
        "features": {
            ...
            "passwordManagement": {
                "enabled": false
            }
        },
        ...
        "passwordManagement": {
            "forgotPasswordButton": {
                "visible": true,
                "customUrl": ""
            },
            "changePassword": {
                "visible": true,
                "customUrl": ""
            }
        },
        ...
    }

The Password management customization options include:

-   `passwordManagement` is the option to enable customizing the Forgotten password options.
-   `forgotPasswordButton` is the "**Forgot your password?**" link on the sign-in page.
-   `changePassword` is the **Password** menu entry in the user menu.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Feature         </th>
<th class="HeadD-Column1-Header1">Description and usage         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>passwordManagement</strong></p>
<p>"enabled": Boolean</p>         </td>
         <td><p>This option allows you to enable visibility of all password management options.</p>
<ul>
<li>False (default value) – the section is disabled, all other settings ignored.</li>
<li>True – the settings are applied.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>forgotPasswordButton</strong>
<p>"visible": Boolean</p>         </td>
         <td><p>This option allows you to enable visibility of the <strong>Forgot your password?</strong> link on the sign-in page.</p>
<ul>
<li>True (default value) – the link is visible.</li>
<li>False – the link is hidden, all other settings related to <code>forgotPasswordButton</code> are ignored.<br />
</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>forgotPasswordButton</strong>
<p>"customUrl": String</p>         </td>
         <td><p>This option allows you to set a custom <strong>Forgot your password?</strong> link on the sign-in page.</p>
<ul>
<li>Default value is an empty string.</li>
<li>If "visible" is true and the value is empty, the setting is ignored and the application has default behavior.</li>
<li>If "visible" is true and the value is a valid URL, changes the behavior of the link to redirect to the specified custom URL. (IDP, etc.)<br />
</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>changePassword</strong>
<p>"visible": Boolean</p>         </td>
         <td><p>This option allows you to enable visibility of the Password (Change your password) entry in the Welcome menu.</p>
<ul>
<li>True (default value) – the change password entry option in the user menu is visible.</li>
<li>False – the Change password is hidden, all other settings related to it are ignored.<br />
</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>changePassword</strong>
<p>"customUrl": String</p>         </td>
         <td><p>This option allows you to set a custom URL for the Password (Change your password) web page.</p>
<ul>
<li>Default value is an empty string.</li>
<li>If "visible" is true and the value is empty, the setting is ignored and the application has default behavior.</li>
<li>If "visible" is true and the value is a valid URL, changes the behavior of the change password menu entry to redirect to the specified custom URL.<br />
</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 
