{
    "title": "Use a site template to define a transfer site",
    "linkTitle": "Use a site template to define a transfer site",
    "weight": "230"
}Use the following procedure to create a transfer site from a template.

1.  Create or edit a Connect:Direct or file services interface protocol site as described in [Create a transfer site](../../../accounts/transfersites/t_st_transfersites#Create) or [Edit a transfer site](../../../accounts/transfersites/t_st_transfersites#Edit).
2.  Select the desired template from the **Site Template** drop-down list.
3.  If the selected template uses placeholder parameters, they are listed at the bottom of the page under **Site Template Placeholders**.  
    If a default value was provided by the site template, you can modify it for this account.  
    (Optional) To have the placeholder default values automatically filled in when the site template is updated, select the **Use Default** check box for one or more placeholder parameters.  
    When you modify a site template, the changes are automatically applied to all transfer sites that use that template. For example:
    -   Add or remove a placeholder parameter adds or removes it to or from all associated transfer sites.
    -   Modify an optional default value of a placeholder parameter updates it in all associated sites that have the Use Default check box selected for that placeholder.
    -   Delete the default value of a placeholder parameter clears it in all associated sites that have the Use Default check box selected for that placeholder.
4.  Click **Add** or **Save** to save your changes and close the *Add Transfer Site* or *Edit Transfer Site* page. Click **Cancel** to close the page without saving your changes.

**Related topic:**

-   [Manage site templates](../t_st_sitetemplates)
