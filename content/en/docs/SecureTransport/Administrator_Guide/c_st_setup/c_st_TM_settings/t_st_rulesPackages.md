{
    "title": "Manage rules packages",
    "linkTitle": "Manage rules packages",
    "weight": "300"
}Rules packages are a collection of rules applicable to a business process.

Managing rules packages consists of:

-   Enabling and disabling rules packages
-   Creating Rules Packages
-   Editing Rules Packages
-   Importing and Exporting Rules Packages

To work with rules, you must login to the {{< SecureTransport/componentshortname  >}} Administration Tool as a system administrator with the appropriate privileges and access the **Admin UI &gt; Setup &gt; TM Settings** page.

> **Note:**
>
> All changes to rules packages are local to the SecureTransport server you are logged in to. For an Enterprise Cluster (EC), you typically develop and modify rules packages on a development server, test them, export them, and import them on the production servers.

<span id="EnableRulesPackage"></span>

## Enable a rules package

Use the following procedure to enable a rules package or packages.

1.  Select **Setup > TM Settings** to display *TM Settings* page.
2.  In the **Select** column, select the Disabled rules package or packages to enable.
3.  Click the **Enable** button.

## Disable a rules package

Use the following procedure to disable a rules package or packages:

1.  Select **Setup > TM Settings** to display *TM Settings* page.
2.  In the **Select** column, select the Enabled rules package or packages to disable.
3.  Click the **Disable** button.

<span id="ExportRulesPackage"></span>

## Export a rules package

Use the following procedure to export a rules package or packages.

1.  Select **Setup > TM Settings** to display *TM Settings* page.
2.  In the **Select** column, select the rules package or packages to export.  
    If only one rules package is selected, the rules package will be exported as a XML file.  
    If multiple rules packages are selected, the rules packages will be exported as a ZIP file.
3.  Click **Export**.
4.  Select the **Save As** option from the **File** menu of the new browser window.  
    The *Save As* dialog box is displayed.
5.  Select the directory in which you want to save the rules package or packages.
6.  Type an appropriate name for the rules package.
7.  Click **Save**.

<span id="ImportRulesPackage"></span>

## Import a rules package

Use the following procedure to import a rules package.

1.  Select **Setup > TM Settings** to display *TM Settings* page.

2.  Select **Import** on the *TM Settings* page.  

    > **Note:**
    >
    > The XML of ZIP file used to import rules packages must be well formatted. Importing an XML file with the XML elements in a single line causes the import to fail. If the import fails, an error message is written to tm.log and the rule are unavailable to execute at runtime.

      
    The *Import Rules Package* screen opens.  
    <img src="/Images/SecureTransport/Setup_Import_Rules.png" class="smallWidth" alt="Import Rules Package" />

3.  **Browse** and select a file (XML or ZIP) with the packages to be imported.

4.  (Optional) Verify to overwrite existing rules packages by selecting **Overwrite existing**.

5.  Select **Import** on the *Import Rules Package* screen.  
    The server checks if the file is a valid XML file or if the ZIP file contains valid XML files. If the file is a valid XML file or if the ZIP file contains valid XML files, the Rules Packages are displayed. If the file is not a valid XML file or if the ZIP file does not contain valid XML files., an error message is displayed.

<span id="CreateRulesPackage"></span>

## Create a rules package

Rules packages are a collection of rules applicable to a business process. To create rules, you must first define a rules package.

You must create rules packages externally and import them into the {{< SecureTransport/componentshortname  >}} Administration Tool. For a detailed explanation of each step in this procedure, refer to the following topics.

1.  Create a rules package.
2.  Add the arguments that need to be passed to the rule.
3.  Specify rule comparisons and conditions for the rule.  
    Conditions are event-based clauses that permit you to compare attribute values or functions that return a logical value.
4.  Insert clauses to add multiple comparisons and conditions.  
    Conditions can be composed of multiple clauses that are combined as logical expressions with the use of AND, OR, or NOT. These clauses can be nested to provide more complex rule processing.
5.  Add an action to rule.  
    Actions specify agents that are triggered depending on the result of a condition. A condition can trigger in-process agents or external agents.
6.  Save the rules package.
7.  Import the rules package into the {{< SecureTransport/componentshortname >}} Administration Tool as described in the above subtopic.

## Edit a rules package

A rule consists of conditions and actions. You can add conditions or actions to rules package by exporting the rules package, editing the rules package locally, and importing the updated rules package.

## Delete a rules package

Removing a rules package from the server is allowed. Agents referred to by a deleted rules package are not removed. These agents maybe used in other rules packages.

Use the following procedure to delete a rules package or packages.

1.  Select **Setup > TM Settings** to display *TM Settings* page.
2.  In the **Select** column, select the rules package or packages to delete.
3.  Click the **Delete** button.
4.  Confirm the deletion.
