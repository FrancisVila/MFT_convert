{
    "title": "Add and modify languages",
    "linkTitle": "Add and modify languages",
    "weight": "70"
}The ST Web Client is installed with some predefined languages. The translations for the predefined languages are located in the `C/locales` folder.

Each translation has a language code folder which contains a JSON file with the translated labels. For example, the English translation is in the `C/locales/en/translation.json` file.

## Add a supported language

The default translations that are part of ST Web Client installation should not be altered. You cannot add new languages in the same location as the default ones. They must be added in the `custom` folder.

To add the Bulgarian language:

1.  Copy the content from the English translation (`C/locales/en/translation.json`) file into the `custom/locales/bg/translation.json` file.

2.  Translate the values from English to Bulgarian.  
    If a value is not translated, it will default to the English translation.

3.  Edit the `stwebclient.config.json` file and specify the additional language in the `i18n` section:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  ...</pre><pre xml:space="preserve">  "i18n": {</pre><pre xml:space="preserve">    "additionalLocales": [{</pre><pre xml:space="preserve">      "id": "bg",</pre><pre xml:space="preserve">      "nameEng": "Bulgarian",</pre><pre xml:space="preserve">      "name": "Български"</pre><pre xml:space="preserve">    }]</pre><pre xml:space="preserve">  }</pre><pre xml:space="preserve">  ...</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

4.  Refresh the ST Web Client and open the *Preferences* pane. The new language should be present in the *Language* drop-down menu.

## <span id="ModifyLanguage"></span>Modify an existing language

You can change the labels for any (default or additional) language.

To change the Welcome label to "Hello Mate:"

1.  Create the `custom/locales/en/override.json` file.

2.  Using the same structure as the English translation (`C/locales/en/translation.json`) file, add the labels that need changed:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre>"header": {</pre><pre xml:space="preserve">  "user_welcome": "Hello mate, "</pre><pre xml:space="preserve">  }</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

3.  Edit the `stwebclient.config.json` file and specify the override for the English language in the `i18n` section:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  ...</pre><pre xml:space="preserve">  "i18n": {</pre><pre xml:space="preserve">    "overridenLocales": ["en"]</pre><pre xml:space="preserve">  }</pre><pre xml:space="preserve">  ...</pre><pre xml:space="preserve">}</pre>
         </td>
      </tr>
   </tbody>
</table>

4.  Refresh the ST Web Client. The overridden label should be displayed.
