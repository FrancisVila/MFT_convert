{
    "title": "Create a delegated administrator",
    "linkTitle": "Create a delegated administrator",
    "weight": "190"
}Use the following procedure to create a delegated administrator.

1.  Create or edit an administrator and set the **Administrative Role** to Delegated Administrator. The panel area expands with various additional Delegated Administrator Settings.

2.  Select a **Parent Administrator**. This is the administrator who hierarchically stands on the higher level to the delegated administrator you are creating.

3.  Select the business units you want to assign to the administrator, if required. Business Units can be added or modified through the *Business Units* page. Also, here you can only assign business units that are assigned to the Parent Administrator.  

    > **Note:**
    >
    > General rules of inheritance apply here: if the Business unit assigned to Delegated Administrator has one or more child business units, all those child business units will be also assigned to this Delegated Administrator.
    > If the business unit does not have child, but another Delegated Administrator adds child on a later stage, the newly added child will be automatically assigned to the first Delegated Administrator. If the child Business Unit is removed from the parent Business Unit but continues to exist, the Delegated Administrator will not be assigned to it anymore.

4.  Depending on the duties and responsibilities of your new delegated administrator, select either of the following options: **Read Only**, **Checker Rights** or **Maker Rights**.  
    -   Select **Read Only** to allow the delegated admin read-only access to the user management screens within the selected Business Units. This option deselects and disables editing of all the permission options that follow.
    -   Select **Checker Rights** to allow the delegated admin Checker-only privileges. This option disables all additional permissions for user account creation and modification.
    -   Select **Maker Rights** to allow the delegated administrator Maker-only privileges. This option preselects the **Create Users** and **Update Users** permissions. You can still edit HelpDesk and Manage rights.

5.  If you do not any of the options in the previous step, you can still assign any of the available privilege options to the new delegated administrator.

6.  Click **Save** to add the new administrator.
