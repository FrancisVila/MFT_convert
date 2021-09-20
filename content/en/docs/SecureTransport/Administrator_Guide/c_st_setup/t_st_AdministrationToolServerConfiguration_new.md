{
    "title": "Configure Administration Tool server settings",
    "linkTitle": "Configure Administration Tool server settings",
    "weight": "130"
}Use the *Admin Setting* page to configure administrator login options. You can configure the password expiration, the number of consecutive failed login attempts allowed and the length of a login session.

The following sections provide how-to instructions for changing password settings, session settings, and certificate settings:

-   [Change password settings](#change)
-   [Change session settings](#change2)

## <span id="Change"></span>Change password settings

Use the password settings to control how often an administrator needs to change the login password and to control how many consecutive failed login attempts are allowed before the administrator is prevented from logging in.

1.  Select **Setup > Admin Settings**.
2.  Type the number of days the administrator password is valid without changing it.  
    You can leave this field blank, which is the default setting. When left blank, the password never expires.
3.  Type the number of consecutive failed login attempts to allow before preventing an administrator from logging in to the server.  
    You can leave this field blank, which is the default setting. When left blank, there is no limit to the number of login attempts permitted.
4.  Click **Save** to accept the changes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the master administrator is locked out (or the wrong password is used too many times), contact <span>Axway</span> Global Support for the procedure to reset the required parameters.         </td>
      </tr>
</table>

## <span id="Change2"></span>Change session settings

Use the session settings to control how long an administrator can be logged into SecureTransport before the session expires and the administrator must log in again.

1.  Select **Setup > Admin Settings**.
2.  Type the number of minutes the session stays active. The default setting is 30 minutes.
3.  Click **Save** to accept the changes.
4.  Restart the Administration Tool server using the `stop_admin` and `start_admin` commands.