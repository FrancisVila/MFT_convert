{
    "title": "Setup test",
    "linkTitle": "Setup test",
    "weight": "130"
}To test your setup, follow these simple steps:

1.  [Create a test account](#create)
2.  [Access test account](#access)
3.  [Transfer test file](#transfer)
4.  [Verify file transfer](#verify)

## <span id="Create"></span>Create test account

The first task to test the SecureTransport installation and initial configuration is to create a test user account.

1.  Log into the Administration Tool as an administrator.

2.  Select **Accounts > User Accounts**.

3.  Click **New Account**.  
    The *New User Account* page is displayed. The New User Account page shown is from a SecureTransport instance running on Windows. The *Real Users* field is the *UID* field for a SecureTransport instance running on UNIX.  
    
    ![New User Account](statusdetail.png)

4.  Enter or select the following information.  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Configurable item</th>
         <th>Enter or select</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Account Name:         </td>
         <td>Test         </td>
      </tr>
      <tr>
         <td>Email Contact:         </td>
         <td>test@axway.com         </td>
      </tr>
      <tr>
         <td>Phone Contact:         </td>
         <td>[blank]         </td>
      </tr>
      <tr>
         <td>Account Type:         </td>
         <td>Unspecified         </td>
      </tr>
      <tr>
         <td>Business Unit:         </td>
         <td>No Business Unit         </td>
      </tr>
      <tr>
         <td>HTML Template:         </td>
         <td>ST Web Client         </td>
      </tr>
      <tr>
         <td>Routing Mode:         </td>
         <td>Reject         </td>
      </tr>
      <tr>
         <td>Encrypt Mode:         </td>
         <td>Unspecified         </td>
      </tr>
      <tr>
         <td>File archiving policy         </td>
         <td>Default         </td>
      </tr>
      <tr>
         <td>Real User (Windows):         </td>
         <td>[blank]         </td>
      </tr>
      <tr>
         <td>UID (UNIX):         </td>
         <td>6000         </td>
      </tr>
      <tr>
         <td>GID:         </td>
         <td>7000         </td>
      </tr>
      <tr>
         <td>Current Home:         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Change Home To*:         </td>
         <td>
            <p>c:\home\users\Test </p>
         </td>
      </tr>
      <tr>
         <td>Change Home To* (UNIX):         </td>
         <td>/home/users/Test         </td>
      </tr>
      <tr>
         <td>Home Folder Access Level:           </td>
         <td>Private         </td>
      </tr>
      <tr>
         <td>Notes:         </td>
         <td>[blank]         </td>
      </tr>
      <tr>
         <td>Adhoc Settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Delivery Method:         </td>
         <td>Default         </td>
      </tr>
      <tr>
         <td>Login Settings:         </td>
         <td>[checked]         </td>
      </tr>
      <tr>
         <td>Login Name:         </td>
         <td>Test         </td>
      </tr>
      <tr>
         <td>Allow this account to login by email         </td>
         <td>[unchecked]         </td>
      </tr>
      <tr>
         <td>Allow this account to submit transfers using the Transfers RESTful API         </td>
         <td>[unchecked]         </td>
      </tr>
      <tr>
         <td>Password is stored locally (not in external directory)         </td>
         <td>[checked]         </td>
      </tr>
      <tr>
         <td>New Password*:         </td>
         <td>axway         </td>
      </tr>
      <tr>
         <td>Re-enter Password*:         </td>
         <td>axway         </td>
      </tr>
      <tr>
         <td>Require user to change password on next login         </td>
         <td>
            <p>[unchecked]</p>
         </td>
      </tr>
      <tr>
         <td>Require user to set new secret question on next login         </td>
         <td>[unchecked]         </td>
      </tr>
      <tr>
         <td>Password Settings:          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Require user to change password every  ___ days         </td>
         <td>[blank]         </td>
      </tr>
      <tr>
         <td>Lock account after ___ failed login attempts         </td>
         <td>[blank]         </td>
      </tr>
      <tr>
         <td>Lock account after ___ successful logins         </td>
         <td>[blank]         </td>
      </tr>
      <tr>
         <td>Additional Attributes         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Add Attribute         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Attribute         </td>
         <td>userVars.1         </td>
      </tr>
      <tr>
         <td>Value         </td>
         <td>test2@axway.com         </td>
      </tr>
   </tbody>
</table>

5.  Click **Save**.  
    The *User Account: Test* page is displayed.

6.  Click **Close**.  
    Observe that the **Test** user account was added to the *User Accounts* page.  
    
    ![View Accounts - Create and maintain user accounts.](statusdetail.png)

## <span id="Access"></span>Access test account

The second task is to access the test account using the ST Web Client.

1.  From your Internet browser, enter the HTTPS address to the SecureTransport installation using the IP address of the SecureTransport installation.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the default port (443) is used for HTTPS protocol, it is not necessary to enter the port number since it is the standard port for the HTTPS protocol. If a non-standard port number is used for HTTPS protocol, you must enter the port number.         </td>
      </tr>
</table>

2.  Following the instructions for your browser, add a certificate exception for the ST Web Client instance.
      
    The *ST Web Client Login* page is displayed.

3.  Enter **User ID:** *Test* and **Password:** *axway*.

4.  Click **Log in**.

## <span id="Transfer"></span>Transfer test file

The third task is to transfer a test file.

1.  Click **Upload**.
2.  Navigate to a test file to upload and click **Open**.
3.  Verify that the test file appears on the *Your files* list.  
    
    ![Verify upload.](statusdetail.png)

## <span id="Verify"></span>Verify file transfer

The fourth and final task is to verify the file transfer.

1.  Log in to the SecureTransport installation as an administrator.
2.  Navigate to **Operations > File Tracking**.
3.  Verify that the test file was successfully uploaded.  
    
    ![File Tracking - Test file verify.](statusdetail.png)
4.  Click the Check icon (![Check](statusdetail.png)) or click the **File Name** to review the details of the file transfer.  
    The *Status Detail* page is displayed.  
    
    ![Status Detail](statusdetail.png)
5.  Click **Close** when you are finished reviewing the transfer status details.
