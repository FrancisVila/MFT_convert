{
    "title": "Configuration files",
    "linkTitle": "Configuration files",
    "weight": "50"
}The settings in the custom `/custom/stwebclient.config.json` configuration file override the settings in the default `C/config/default.config.json` configuration file.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You must not modify the <code>C/config/default.config.json</code> configuration file. You must make your changes in the <code> /custom/stwebclient.config.json</code> configuration file.         </td>
      </tr>
</table>

The default configuration file has the following top-level keys:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
 "features": {
   ... // enabling/disabling features
 },
 "i18n": {
   ... // adding/modifying languages (internationalization)
 },
 "branding": {
  ... // branding  
 }
"transferQueue": {
   ... // transfer queue settings
 },
 "views": {
  ... // views configuration
 }
 "liteMode": {
   ... // enabling/disabling liteMode
 },
 "passwordManagement": {
   ... // forgot password and change password settings 
 },
 "accessControl": {
   ... // enabling/disabling access to some UI functions
 },
 "sessionManagement": {
   ... // client session management settings
 },
 "disclaimer":{
    ... // disclaimer settings
 },
 "shareAction": {
   ... // disabling folder sharing or configuring the default folder sharing options  
 }
}					</pre>
         </td>
      </tr>
   </tbody>
</table>

The custom `stwebclient.config.json` configuration file must have the same structure as the `default.config.json` configuration file, but including a key in the custom configuration file is optional. If a key is not present in the custom configuration file, the key in the default configuration file is used.

For example, the following custom `stwebclient.config.json` configuration file only has a branding key.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  "branding": {</pre><pre xml:space="preserve">    ...</pre><pre xml:space="preserve">  }</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

In this example, the features and internationalization configurations are provided by the keys in the `default.config.json` file, and the branding configuration is provided by the key in the `stwebclient.config.json` file. Keys not included in the `stwebclient.config.json` file are inherited from the `default.config.json` file.
