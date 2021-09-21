{
    "title": "Pre-login disclaimer banner",
    "linkTitle": "Pre-login disclaimer banner",
    "weight": "230"
}You can configure a disclaimer banner that is displayed to users before they log in. The banner can contain legal statements that must be accepted before a user can continue to the login process.

## Enable the disclaimer feature

To enable the disclaimer feature, add a `"disclaimer"` section to the features configuration and set `enabled` to `true`.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{
"features": {
   ...
   "disclaimer": {
   "enabled": true
   }
  ...
},
"disclaimer": {
   "showAlways": false
   }
}						</pre>
         </td>
      </tr>
   </tbody>
</table>

The disclaimer appearance is controlled by the `showAlways` property. It is set to `false` by default which means that the disclaimer appears once per user/browser. The user confirmation is stored locally along with a content hash to ensure the disclaimer will pop again when its content changes.

To configure a disclaimer that appears before every login attempt, set `showAlways` to `true`.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To prevent accidental confirmation of the disclaimer by  users without <span>ST Web Client</span> credentials, the confirmation is stored permanently only after the user logs into <span>ST Web Client</span>.         </td>
      </tr>
</table>

## Set up the disclaimer banner

The disclaimer banner has two controls: for the text and the button, respectively. Since the disclaimer text can be long, it should be placed inside a separate file, and the file name must be added to i18n settings.

To set up the disclaimer text, follow the steps below:

1.  Put your disclaimer text into a file. The format can be either text or HTML (only basic formatting tags are supported: `p`, div, span, br, b, strong, i, u).  
    `disclaimer.html`  

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;p&gt;Please, read the terms and conditions below.....&lt;/p&gt;</p>
            <p>Additional text</p>
         </td>
      </tr>
   </tbody>
</table>

2.  Put the file in the `custom/locales/en/` folder.

3.  Set up override for the default translation by following the steps as described in [Add and modify languages](../add_mod_lang).  
    In `custom/locales/en/override.json`, define the disclaimer section:

The final configuration should look like this:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
...
"disclaimer": {
   "button_label": "I agree",
   "content_file_name": "disclaimer.html"
   }
}							</pre>
         </td>
      </tr>
   </tbody>
</table>

Once done, you should see the disclaimer banner on the login page.

### Add translations for other languages

1.  Modify `custom/locales/<your_locale>/translation.json`. For more information, see [Add and modify languages](../add_mod_lang).
2.  Translate the disclaimer text and place the file next to `translation.json`.

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td><pre xml:space="preserve">{
  "features": {
     "disclaimer": {
     "enabled": true
  }
},
  "i18n": {
     "overridenLocales": ["en"]
  },
 ....
}		</pre>         </td>      </tr>   </tbody></table>

If everything is correct, you should see the disclaimer properly translated for the chosen locale.  
