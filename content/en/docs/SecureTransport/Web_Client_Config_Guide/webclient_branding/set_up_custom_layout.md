{
    "title": "Set up a custom layout",
    "linkTitle": "Set up a custom layout",
    "weight": "110"
}This feature enables you to add custom content on the ST Web Client login page and on the pages logged in users can access.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Your customizations must NOT modify any <span>ST Web Client</span> file inside <code>&lt;FDH&gt;/share/ftdocs/html/skin/ric/C</code>. These kinds of customizations are not supported.         </td>
      </tr>
</table>

1.  Collect all your changes in an HTML template. Analyze them and make sure that you can apply these changes after STWC initialization.

2.  Create the plugin by following the rules:  
    
    -   must be placed in its own folder, e.g., `/my-layout`.
    -   must contain an index.html file (this is the entry point), e.g., `/my-layout/index.html`.
    -   the plugin folder can contain resources like images and fonts, e.g., `/my-layout/mylogo.png`.
    -   the layout name can contain letters, numbers, underscores, and dashes; If the name does not comply with these rules, the layout will be ignored.

3.  When the plugin is ready, add it to ST Web Client by copying its folder to /custom.

4.  Edit `stwebclient.config.json` to tell ST Web Client to load the plug-in:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  "branding": {</pre><pre xml:space="preserve">    "layoutInject": {</pre><pre xml:space="preserve">      "my-layout": ["login", "list"]</pre><pre xml:space="preserve">    }</pre><pre xml:space="preserve">  }</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

      
     The values on the right are the target HTML template names without the extension. In this case, the plug-in is applied to the login and the main application pages.   
    The templates are placed in `<FDH>/share/ftdocs/html/skin/ric/C`.   
    The available templates are: `account_expired, download_public, download, list, lockout, login, logout, message, password_expired, password_fail, password_msg, password_reset, password, secretQuestion, timeout`.

**HINTS** When creating your plugin, you can use the CSS style definitions in `wap.css` and `progress.css`. You can also add styles in the plugin HTML file (`index.html`). If the styles are overriding existing ones, flickering may occur.
