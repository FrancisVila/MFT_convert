{
    "title": "Pre-login disclaimer banner",
    "linkTitle": "Pre-login disclaimer banner",
    "weight": "230"
}You can configure a disclaimer banner that is displayed to users before they log in. The banner can contain legal statements that must be accepted before a user can continue to the login process.

## Enable the disclaimer feature

To enable the disclaimer feature, add a `"disclaimer"` section to the features configuration and set `enabled` to `true`.


    {
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
    }                       

The disclaimer appearance is controlled by the `showAlways` property. It is set to `false` by default which means that the disclaimer appears once per user/browser. The user confirmation is stored locally along with a content hash to ensure the disclaimer will pop again when its content changes.

To configure a disclaimer that appears before every login attempt, set `showAlways` to `true`.

> **Note:**
>
> To prevent accidental confirmation of the disclaimer by users without ST Web Client credentials, the confirmation is stored permanently only after the user logs into ST Web Client.

## Set up the disclaimer banner

The disclaimer banner has two controls: for the text and the button, respectively. Since the disclaimer text can be long, it should be placed inside a separate file, and the file name must be added to i18n settings.

To set up the disclaimer text, follow the steps below:

1.  Put your disclaimer text into a file. The format can be either text or HTML (only basic formatting tags are supported: `p`, div, span, br, b, strong, i, u).  
    `disclaimer.html`  



        <p>Please, read the terms and conditions below.....</p>
        Additional text

2.  Put the file in the `custom/locales/en/` folder.

3.  Set up override for the default translation by following the steps as described in <a href="../add_mod_lang" class="MCXref xref">Add and modify languages</a>.  
    In `custom/locales/en/override.json`, define the disclaimer section:

The final configuration should look like this:

    {
      "features": {
         "disclaimer": {
         "enabled": true
      }
    },
      "i18n": {
         "overridenLocales": ["en"]
      },
     ....
    }       

Once done, you should see the disclaimer banner on the login page.

### Add translations for other languages

1.  Modify `custom/locales/<your_locale>/translation.json`. For more information, see <a href="../add_mod_lang" class="MCXref xref">Add and modify languages</a>.
2.  Translate the disclaimer text and place the file next to `translation.json`.

> **Note:**
>
> The name of the disclaimer content file can be the same because each locale is placed in its own folder; the "\_bg" suffix in the example is used only for clarity.

If everything is correct, you should see the disclaimer properly translated for the chosen locale.  
