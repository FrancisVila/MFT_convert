{
    "title": "Configure adhoc file transfers",
    "linkTitle": "Configure AdHoc file transfers",
    "weight": "140"
}Use the *AdHoc Settings* page to configure parameters and defaults for adhoc file transfers using ST Web Client.

1.  Select **Setup > AdHoc Settings**.  
    The *AdHoc Settings* page is displayed.
2.  <span id="AdHoc_Settings"></span>Provide the information as described in the following table:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Name         </th>
    <th class="HeadD-Column1-Header1">Description         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><strong>Global AdHoc Settings</strong>         </td>
          </tr>
          <tr>
             <td>Default enrollment account template         </td>
             <td>{{< SecureTransport/componentshortname  >}} uses this account template when enrolling an adhoc file transfer recipient. For information about account templates, see <a href="../../c_st_advancedaccountadministration/c_st_accounttemplates#Advanced_Accounts_2036285406_1088507">Account templates</a>.         </td>
          </tr>
          <tr>
             <td>Default notification mail template         </td>
             <td>{{< SecureTransport/componentshortname  >}} uses this mail template to create all notification emails to adhoc file transfer recipients and senders. For more information about mail templates, see <a href="../t_st_mailtemplates#SetupMenu_1217491348_1149202">Mail templates</a>.         </td>
          </tr>
          <tr>
             <td><span id="DeliveryMethod"></span>Default Package Delivery Method         </td>
             <td><p>{{< SecureTransport/componentshortname  >}} uses this delivery method when the <strong>Delivery Method</strong> field in <em>Account Setting</em> for a user account, in an account template, or in a business unit is set to <strong>Default</strong>.</p>
    <ul>
    <li><strong>Disabled</strong> – Adhoc file transfers are disabled.</li>
    <li><strong>Anonymous</strong> – The adhoc file transfer recipient receives a link to retrieve the files and is not enrolled as a user.</li>
    <li><strong>Account Without Enrollment</strong> – Do not enroll adhoc file recipients. Only existing users can receive files.</li>
    <li><strong>Account With Enrollment</strong> – The adhoc file must enroll as a {{< SecureTransport/componentshortname  >}} user before retrieving the files.</li>
    <li><strong>Custom</strong> – Select the allowed enrollment types in the <strong>Default enrollment type</strong> field. Depending on the value of the <strong>Default implicit enrollment type</strong> field, the sender chooses one of the selected enrollment types when composing the mail in ST Web Client.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><span id="EnrollmentTypes"></span>Default enrollment type         </td>
             <td><ul>
    <li><strong>Anonymous</strong> – The adhoc file transfer recipient receives a link to retrieve the files and is not enrolled as a user.</li>
    <li><strong>Challenge</strong> – The adhoc file recipient receives a link and must answer a challenge question correctly to retrieve the files. The recipient is not enrolled as a user.</li>
    <li><strong>Existing Account</strong> – Do not enroll adhoc file recipients. Only existing users can receive files.</li>
    <li><strong>Enroll Unlicensed</strong> – The adhoc file recipient must enroll as a {{< SecureTransport/componentshortname  >}} unlicensed user before retrieving the files. An unlicensed user can only reply once to the email and retrieve the files. Other user attributes are defined by the enrollment template.</li>
    <li><strong>Enroll Licensed</strong> – The adhoc file recipient must enroll as a {{< SecureTransport/componentshortname  >}} user with all the attributes specified in the default enrollment template before retrieving the files.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><span id="ImplicitEnrollmentType"></span>Default implicit enrollment type         </td>
             <td>The values displayed depend on the settings of <strong>Default Package Delivery Method</strong> and <strong>Default enrollment type</strong>. sets this value as the initial value selected in the <em>User Access</em> window when a user with the <strong>Delivery Method</strong> field set to <strong>Default</strong> composes an email.         </td>
          </tr>
          <tr>
             <td>Default Expiration Interval         </td>
             <td><p>ST Web Client displays this value as the initial value of the <strong>Expiration</strong> drop-down list in the <em>Compose Mail</em> tab. The choices are: 1 Day, 7 Days, 30 Days, 60 Days, and Never.</p>         </td>
          </tr>
          <tr>
             <td>Maximum Expiration Interval         </td>
             <td>ST Web Client displays this value as the largest value of the <strong>Expiration</strong> drop-down list in the <em>Compose Mail</em> tab. The choices are: 1 Day, 7 Days, 30 Days, 60 Days, and Never.         </td>
          </tr>
          <tr>
             <td>Package Manager Base Folder         </td>
             <td>{{< SecureTransport/componentshortname  >}} uses this working folder to process adhoc file transfers. In a cluster, all servers use the same folder, so specify the same location in shared storage. To enable adhoc file transfers, you must specify this folder. For a list of folder that are not allowed, see <a href="../../accounts/useraccounts/c_st_protected_folders_accounts#Protecte">Protected folders and accounts</a>.         </td>
          </tr>
          <tr>
             <td>Package Manager System Username<br />
    (Windows only)         </td>
             <td>If the package manager base folder is in shared storage, enter the user name of the Windows system user that {{< SecureTransport/componentshortname  >}} uses to access the package manager base folder. The user must be in the {{< SecureTransport/componentshortname  >}} password vault. If you change this field, you must not remove the previous user from the password vault.         </td>
          </tr>
          <tr>
             <td>Mailbox Folder Name         </td>
             <td>{{< SecureTransport/componentshortname  >}} creates a folder with this name in the user's home folder to store the user's mail folders. Because the mail folders are for use for adhoc file transfers only, these folders are not visible to clients. Do not modify any files in these folders or in the mail folders.         </td>
          </tr>
          <tr>
             <td><p>Anonymous Account Name</p>
    <p>Anonymous Account UID</p>
    <p>Anonymous Account GID</p>
    <p>Anonymous Account Home Folder</p>         </td>
             <td>{{< SecureTransport/componentshortname  >}} uses this account name, UID, GID, and home folder when an adhoc file transfer recipient logs in anonymously to retrieve a file. You must create this account.         </td>
          </tr>
          <tr>
             <td><strong>Email Notification Settings</strong>         </td>
          </tr>
          <tr>
             <td>Disable account enrollment notification         </td>
             <td>{{< SecureTransport/componentshortname  >}} does not send out account enrollment notifications when this option is selected. If you select this option, you must manage any account enrollment notifications externally using REST API from your email system. By default, this option is not selected.         </td>
          </tr>
          <tr>
             <td>Disable package delivery notification         </td>
             <td><p>{{< SecureTransport/componentshortname  >}} does not send out package delivery notifications when this option is selected. If you select this option, you must manage any package delivery notifications externally using REST API from your email system. By default, this option is not selected.</p>
    <blockquote>
    <p><strong>Note:</strong></p>
    <p>Package delivery notifications can also be disabled by the end user. If you do not select this option, the end user can disable package delivery notifications. If you select this option, the end user cannot override your selection and package delivery notifications will be disabled even if they are enabled by the end user.</p>
    </blockquote>         </td>
          </tr>
       </tbody>
    </table>
3.  Click **Save**.

Two server configuration parameters control handling of human-to-system (H2S) transfers:

-   By default, value of the `PackageManager.DualDeliveryDisabled` server configuration parameter is **true** and {{< SecureTransport/componentshortname >}} stores the files attached to an H2S email in the target folder and processes them but does not send the email to the system user. If value of `PackageManager.DualDeliveryDisabled` is **true**, SecureTransport also sends the email to the system account. If the email recipients also include H2H addresses, {{< SecureTransport/componentshortname >}} sends the email to the those recipients regardless of the value of `PackageManager.DualDeliveryDisabled`.
-   By default, value of the `PackageManager.BodyRoutingDisabled` server configuration parameter is **true** and {{< SecureTransport/componentshortname >}} ignores the body of an H2S email. If value of `PackageManager.BodyRoutingDisabled` is **false**, SecureTransport puts the body of the email in a text file with a name of the form `uniqueID_body_wap.txt` and stores it with the files attached to an H2S email in the target folder.

The following topics provide how-to instructions for changing the package manager base folder and describe the Package Retention Maintenance application.

-   [Change the package manager base folder](t_st_change_package_manager_base_folder)
-   [Package Retention Maintenance application](../../applications/applicationspackageretentionmaintenance)
