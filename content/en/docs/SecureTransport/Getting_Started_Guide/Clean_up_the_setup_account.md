{
    "title": "Clean up the setup account",
    "linkTitle": "Clean up the setup account",
    "weight": "120"
}The initial configuration of SecureTransport is now complete. As a final step, clean up the Setup account either by removing it or by changing the password. You can use the default administrator account for additional configuration tasks.

1.  Log out of the Administration Tool.
2.  Log in using the default user name, `admin` and default password `admin`.
3.  Select **Accounts > Administrators**.
4.  Take one of the following actions:
    -   Remove the Setup Administrator by clicking the check box next to it and then **Delete**.
    -   Change the password for the Setup Administrator by clicking the administrator entry and setting the desired password in the *Administrator Account Status* pane.

For the best security, change the default password of the `account`, `admin`, and `application` administrator accounts.

For more information on the ****Accounts &gt; Administrators** ** settings, refer to the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Once you have made the configuration changes using the Administration Tool, run <code>stop_all</code> to stop all <span>SecureTransport</span> services, then run <code>start_all</code> to restart them. For information on stopping and starting <span>SecureTransport</span> services, refer to the <span data-cshid="admin" data-version="5.3.5"><em><span>SecureTransport</span> Administrator's Guide</em></span>.         </td>
      </tr>
</table>