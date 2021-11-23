{
    "title": "Create multiple instances with different configurations",
    "linkTitle": "Create multiple instances with different configurations",
    "weight": "100"
}You can run multiple instances of the on one {{< SecureTransport/securetransportname  >}} server. This allows you to use the {{< SecureTransport/securetransportname  >}} dynamic skin feature and set the available features and appearance of the per user account, account template, or business unit.

On Unix platforms, use the following procedure to create a new instance of (STWC):

1.  Go to `<FILEDREVEHOME>/share/ftdocs/html/skin/`.

2.  Duplicate the `ric` folder. Choose a short and meaningful name for the duplicated folder, for example, *stwc1*.

3.  Prepare the branding assets you need for the new skin following the instructions in the [Branding](../webclient_branding) section. The new instance is styled and branded using the following files located in the folder created in Step 2.  
    -   `<stwc1>/C/assets/wap.css` - Controls the color theme and the style.
    -   `<stwc1>/custom/stwebclient.config.json` - Controls the logos, the text header displayed next to the logo and the disclaimer on the login page.

4.  In the new STWC instance folder, create a file with .sh extension (for example, *change\_ric.sh*) and paste the following script in it:  



        #!/bin/bash 
         
        # new deploy folder name
        DEPLOY_FOLDER=stwc1
        DEPLOY_FOLDER_ORIG=ric 
         
        DEPLOY_PATH_ORIG=html/skin/$DEPLOY_FOLDER_ORIG
        DEPLOY_PATH=html/skin/$DEPLOY_FOLDER 
         
        find ./C -maxdepth 2 -name "*.*" | xargs sed -i -r "s|$DEPLOY_PATH_ORIG|$DEPLOY_PATH|g"

5.  **Note:**
    >
    > The script will fix the paths in the STWC source folder (stwc1/C) only. All paths in other folders like /custom should be fixed manually to use the new path \[/html/skin/stwc1/...\].

6.  Set *execute* permission on your script: open the .sh file properties and change the file permissions to 755 (rwxr-xr-x).

7.  Open a console and navigate to the new STWC instance folder.

8.  Run the script you created in the previous steps using the following command:  



         ./change_ric.sh

9.  Exit the console.

10. Go back to the new STWC instance folder, and open the *skin.conf* file.

11. Edit the `description` - this is the name of the newly created HTML template.

12. Save the changes.  
    The newly created HTML template appears as an option in the HTML Template
    drop-downs in the {{< SecureTransport/componentshortname >}} Administration tool.

13. Go to `stwc1/C` folder and open one of the HTML templates, for example, `message.html`. Verify that all &lt;link> and &lt;script> elements contain the new path "`html/skin/stwc1/C/......`". We recommend that you perform a search for the old path "html/skin/ric" and make sure that it is not present in the `/stwc1/C/` directory.

## Set the HTML template for users and groups

The HTML template that SecureTransport displays when the user logs in to the can configure it on the following levels:

-   [user account](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/accounts/t_st_create_user_account.htm): **User Account Settings > HTML Template
    drop-down**
-   [account template](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/advanced_account_admin/t_st_accountTemplates.htm): **Account Template Settings > HTML Template
    drop-down**
-   [business unit](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/advanced_account_admin/t_st_businessUnits.htm#HTML_template_bu): **Business Units Settings > HTML Template Settings**
