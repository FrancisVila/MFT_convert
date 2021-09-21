{
    "title": "Enable and disable features",
    "linkTitle": "Enable and disable features",
    "weight": "60"
}The features key in the `default.config.json` configuration file defines all the ST Web Client features that can be enabled or disabled by overriding them in the custom `stwebclient.config.json` configuration file.

The `default.config.json` file contains the following features:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  ...</pre><pre xml:space="preserve">  "features": {</pre><pre xml:space="preserve">    "addressBook": {</pre><pre xml:space="preserve">      "enabled": null,</pre><pre xml:space="preserve">      "collaborationAllowed": null,</pre><pre xml:space="preserve">      "favoritesEnabled": true</pre><pre xml:space="preserve">    },</pre><pre xml:space="preserve">    "i18n": {</pre><pre xml:space="preserve">      "enabled": true</pre><pre xml:space="preserve">    }</pre><pre xml:space="preserve">  },</pre><pre xml:space="preserve">  ...</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

Where:

`true` - The feature is enabled.

`false` - The feature is disabled.

`null` - The feature is controlled by the SecureTransport server. Server controlled features can be disabled, but not enabled.

To disable the internationalization (language localization) feature, edit the `stwebclient.config.json` file and add the following:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
...
   "features": {
      "i18n": {
         "enabled": false
      }
   },
...
}						</pre>
         </td>
      </tr>
   </tbody>
</table>

Keys not included in this file are inherited from the `default.config.json` file.

To disable the Address Book feature, even if is it enabled on the SecureTransport server, edit the `stwebclient.config.json` file and add the following:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
 ...
   "features": {
      "addressBook": {
         "enabled": false
      }
   },
...
}</pre>
         </td>
      </tr>
   </tbody>
</table>

To make the feature changes effective, clear your browser cache and reload ST Web Client. No server restart is required.
