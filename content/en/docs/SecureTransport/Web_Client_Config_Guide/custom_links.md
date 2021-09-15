{
    "title": "Custom links",
    "linkTitle": "Custom links",
    "weight": "220"
}Custom links appear between last menu item and the **Logout** one. A separator is inserted before the custom links (can be disabled in the configuration). The custom links feature supports translations with i18n module.

## Enable Custom Links feature

To enable Custom Links, in the custom configuration file, add the `userMenuCustomLinks` property and set its value to `true`.

    {
       "features": {
       ...
          "userMenuCustomLinks": {
             "enabled": true
          },
       ...
       },
       ...
    }                       

## Custom links without i18n translations

Add the feature section to the custom configuration file. Set `insertSeparator` to `false` to disable the separator. Each menu item has two mandatory properties - `label` and `url `, and one optional - `useSameWindow`. For security reasons, the `url` property must contain a valid URL (RFC 1738). The default behavior of the links is that they open in a new tab or window, depending on browser settings. To open the link in the same window, set the `useSameWindow` property to `true`.

A sample configuration with two links and no separator:

    {
       ...
       "userMenuCustomLinks": {
          "insertSeparator": false,
          "items": [{
             "label": "Google search",
             "url": "http://google.com"
          }, {
             "label": "Company policy",
             "url": "https://mycompany.com/policy",
             "useSameWindow": true
          }]
       }
       ...
    }                   

## Custom links with i18n

To enable translations via i18n module, follow the steps:

1.  Add an `"i18n"` section to the `userMenuCustomLinks` configuration and set `enabled` to `true`.

2.  Define the section name using the `sectionName` property.  
    This section name will be used in translation files in the next steps. We recommend that you follow the snake\_case naming convention which is also used in `translation.json` file.

3.  Add custom link definitions. For each item use the label property as a translation key - set a unique property value.  

    <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">DO NOT USE SPACES OR SPECIAL CHARACTERS AS KEY VALUES! We recommend that you use snake_case.         </td>      </tr></table>

      
    **Good**: "my\_link", "link\_to\_google", "myLink"  
    **Bad**: "my link", "1stlink", "my-link", "my,link"  
    Sample configuration:  

4.  Setup override for the default translation. Follow the steps as described in [Add and modify languages](../add_mod_lang).  
    In `custom/locales/en/override.json`, add the previously defined custom links section:

5.  Add a translation for another language - see [Add and modify languages](../add_mod_lang). Use the same section name and keys.  
    Modify `custom/locales/<your_locale>/translation.json`:  

The final configuration should look like this:

    {
       "features": {
          "userMenuCustomLinks": {
             "enabled": true
         },
       },
         "userMenuCustomLinks": {
            "i18n": {
              "enabled": true,
              "sectionName": "custom_links"
         }, 
       "items": [{
          "label": "link1",
          "url": "http://google.com"
       }, {
       "label": "link2",
       "url": "https://mycompany.com/policy",
       "useSameWindow": true
       }]
       "
    },i18n": {
         "additionalLocales": [{
            "id": "bg",
         "nameEng": "Bulgarian",
         "name": "български" 
          }],
         "overridenLocales": ["en"]
       },
       ...
    }                       

If all settings are correct, the links' names should be properly displayed for the selected locale.
