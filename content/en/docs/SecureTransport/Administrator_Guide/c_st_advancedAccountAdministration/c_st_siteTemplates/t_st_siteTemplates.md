{
    "title": "Manage site templates",
    "linkTitle": "Manage site templates",
    "weight": "220"
}From the *Site Templates* page, you can create, search for, view, modify, and delete site templates.

The following topics provide how-to instructions for managing site templates:

-   <a href="#Create" class="MCXref xref">Create a site template</a>
-   <a href="#Search" class="MCXref xref">Search for a site template</a>
-   <a href="#View" class="MCXref xref">View a site template</a>
-   <a href="#Modify" class="MCXref xref">Modify a site template</a>
-   <a href="#Delete" class="MCXref xref">Delete a site template</a>

**Related topic:**

-   <a href="../t_st_usesitetemplate" class="MCXref xref">Use a site template to define a transfer site</a>

<span id="Create"></span>

## Create a site template

You can create site templates for Connect:Direct and file services interface sites.

A site template contains the same fields as the corresponding transfer site. Within those fields you can provide hardcoded values such as a server name or port number, or you can provide a placeholder parameter. You can specify an optional default value as part of a placeholder parameter. This default value can be changed after the site template is applied to a transfer site. When you select a site template while defining a transfer site, you can provide values tailored for a specific transfer site in each field that specified a placeholder parameter.

> **Note:**
>
> You can create multiple site templates, but each site template must have a unique name.

{{< SecureTransport/componentshortname  >}} provides a placeholder parameter you can use when you do not want to hard code values in the fields for the site template. A placeholder parameter is associated only with the site template where it is used. You can, however, specify different placeholder parameters for each site template you create. A placeholder parameter consist of two parts, the placeholder name and an optional default value. The format for entering a placeholder parameter is:

`%{PlaceholderName|DefaultValue}`

where `PlaceholderName` is the name of the placeholder parameter and `DefaultValue` is an optional default value assigned to a specific field.

> **Note:**
>
> If you are using the optional default value, it must be separated from the placeholder name by the | character.

For example, the placeholder parameter `%{ServerPort|456}` has both a placeholder name and a default value. In this example, the placeholder parameter is entered in the **Local server port** field and a server port number of 456 is used by all transfer sites that apply this site template and accept the default value.

Placeholder names can only contain the following characters: a-z, A-Z, 0-9, and the underscore (`_`). The first character of a placeholder name cannot be a digit. The default value can use any characters, but to include a right brace (`}`), precede it with a backslash (`\}`).

Placeholder examples:

`%{ServerPort|456}`

`%{certificate|st_cd_server_certificate_hr}`

`pull %{pullTransferFile}`

> **Note:**
>
> The placeholder parameter cannot include regular expressions.

1.  Select **Accounts > Site Templates**.  
    The *Site Templates* page is displayed.
2.  Click **New Site Template** to create the template.
3.  Type a site template name in the **Template Name** field.
4.  Select Connect:Direct or the file services interface protocol from the **Transfer Protocol** list.
5.  Complete the remaining fields for the transfer protocol you selected.
6.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.
7.  Click **Add** to save the site template. Click **Cancel** to close the page without saving the site template.

<span id="Search"></span>

## Search for a site template

Use the following procedure to search for a site template.

1.  Select **Accounts > Site Templates**.  
    The *Site Templates* page is displayed.
2.  In the *Search* pane, type all or part of a site template name and click **Search**. Wildcards are not accepted.  
    All site templates that match the search criteria are displayed.

> **Note:**
>
> You can use individual characters to search for a template, such as typing "1" to see all site templates that contain "1" in the name. If you have site templates named NDM1, 1NDM, and NDM 1, all three site templates are displayed. If you have a fourth site template named NDM2, it is not displayed.

<span id="View"></span>

## View a site template

Use the following procedure to view a site template.

1.  Select **Accounts > Site Templates**.  
    The *Site Templates* page is displayed.
2.  Click the site template name. The *Edit Transfer Site Template* page is displayed. Use this page to view the site template settings.
3.  Click **Save** or **Cancel** to return to the *Site Templates* page.

<span id="Modify"></span>

## Modify a site template

Use the following procedure to modify a site template.

1.  Select **Accounts > Site Templates**.  
    The *Site Templates* page is displayed.
2.  Click the site template name. The *Edit Transfer Site Template* page is displayed.
3.  Modify any fields you want to change.
4.  Click **Save** to return to the *Site Templates* page. Click **Cancel** to close the site template without saving the changes.

<span id="Delete"></span>

## Delete a site template

Use the following procedure to delete a site template.

1.  Select **Accounts > Site Templates**.  
    The *Site Templates* page is displayed.
2.  Select one or more site templates.
3.  Click **Delete** to remove the site templates. A dialog box displays asking you to confirm the deletion. Click **OK** to continue or **Cancel** to stop.
