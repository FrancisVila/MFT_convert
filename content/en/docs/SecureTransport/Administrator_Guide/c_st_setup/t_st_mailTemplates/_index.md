{
    "title": "Mail templates",
    "linkTitle": "Mail templates",
    "weight": "240"
}Use the *Mail Template Repository* page to manage the email templates used in Human to Human and System to Human file transfers. SecureTransport uses the mail template selected on the *AdHoc Settings* page to create all notification emails to ad hoc file transfer recipients and senders. To select the mail template, see [Configure adhoc file transfers](../t_st_adhocconfiguration).

SecureTransport sends the following email notifications to ad hoc file transfer recipients and senders:

-   Account enrollment notification to the recipient
-   Package delivery notification to the recipient and the sender
-   Account enrollment failure notification to the sender
-   Package delivery failure notification to the sender

The mail template uses variables in `style` attributes to select the information that SecureTransport includes in each notification.

## Add a mail template for AdHoc, Enrollment, or Advanced Routing notifications

Use the following procedure to add a mail template.

1.  Click **Setup > Mail Templates**.  
    The *Mail Template Repository* page is displayed.  
    The default mail template is loaded in the repository initially.
2.  Click **Add Mail Template**.  
    A line is added to the list.
3.  On the new line, click **Browse**.  
    A file upload window is displayed.
4.  Select a file template file to upload.
5.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Selected File** column.  
    SecureTransport uploads the mail template file and adds it to the repository.

## Download a mail template

Use the following procedure to download a mail template.

1.  Right-click the template name in the Mail Template File column and select **Save Link As** or **Save Target As**.  
    The web browser displays a dialog box.
2.  Navigate to the folder and change the file name as needed.
3.  Click **Save**.  
    The file is saved to the location you specify.

## Upload an updated mail template

After you download a mail template and update it, you can upload the update to SecureTransport.

1.  In the first column, select the mail templates for which you have updated files.
2.  On each selected line, click **Browse** and selected the updated file.  
    The file name of the updated template must be the same as the file name of the existing template.
3.  Click **Upload**.  
    SecureTransport uploads the updated files and replaces the existing files. Any references to the file templates are not changed.

## Delete mail templates

Use the following procedure to delete mail templates.

1.  In the first column, select the mail template files to delete.
2.  Click **Delete**.  
    SecureTransport displays a confirmation dialog.
3.  Click **OK** to delete the selected mail template files.

 

See next: [Mail template commands and variables](c_st_mail_template_commands_variables)
