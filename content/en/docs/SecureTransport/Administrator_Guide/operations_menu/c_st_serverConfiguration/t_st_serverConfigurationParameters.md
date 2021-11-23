{
    "title": "View and change server configuration parameters",
    "linkTitle": "View and change server configuration parameters",
    "weight": "170"
}Many {{< SecureTransport/componentshortname  >}} server configuration parameters are stored in the database. In a cluster, any change you make to any shared parameter is automatically copied to all nodes in the cluster.

The *Server Configuration* page, accessed by selecting **Operations &gt; Server Configuration**, shows all configuration parameters that are stored in the database. You can view the values of all parameters and you can edit the values of some of them. You set the values of parameters you cannot edit on the *Server Configuration* page using fields on other pages of the Administration Tool.

The following topics provide how-to instructions for searching, paging through, and changing parameters:

-   [Search for a parameter](#Search)
-   [Page through the parameter list](#Page)
-   [Change a parameter value](#Change)

**Related topics:**

-   [Editable server configuration parameters](../c_st_editable_server_configuration_parameters)
-   [Local server configuration parameters](../c_st_local_server_configuration_parameters)
-   [Update configuration files](../t_st_serverconfigurationfiles)
-   [Export and import server configuration](../t_st_serverconfigurationexportimport)

<span id="Search"></span>

## Search for a parameter

You can filter the list of parameters using fields in the *Search* pane.

1.  To display only parameters that contain a string in their name, type that string in the **Parameter** field. The parameter name search is not case sensitive.
2.  To display only parameters that contain a string in their value, type that string in the **Value** field. The parameter value search is case sensitive.
3.  To display only parameters you can edit, select **Editable Parameters**.
4.  To display only local parameters, select **Local Parameters**.
5.  Click **Go**.  
    The filtered list is displayed.

> **Note:**
>
> Drag the resize handle of a field in the Value column to see or change all the text.

<span id="Page"></span>

## Page through the parameter list

If there are more than 100 parameters in the filtered list, they are displayed on pages.

1.  To display to the next or previous page, click the forward or back arrow.
2.  To display a page, type the page number in the **page** field and click **GO**.

<span id="Change"></span>

## Change a parameter value

If a parameter is editable, you can change its value. In many case, the valid values are include in the Description column.

1.  In the Edit column, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)).
2.  Type the new value in the **Value** column.
3.  In the Edit column, click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)).  
    {{< SecureTransport/componentshortname >}} saves the value to the database. If the parameter applies to all nodes in the cluster, {{< SecureTransport/componentshortname >}} copies it to the other nodes.
4.  To cancel an edit, click **Go** in the *Search* pane.

> **Note:**
>
> If you edit the value of a second parameter before saving the value of the first, save each value in turn, waiting for each save operation to complete before saving the next.
