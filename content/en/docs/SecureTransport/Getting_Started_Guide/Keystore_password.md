{
    "title": "Change the keystore password",
    "linkTitle": "Change the keystore password",
    "weight": "60"
}Setup step 2 requires you to change the default keystore password.

{{< SecureTransport/componentshortname  >}} contains a keystore of encrypted X509 and PGP private and public keys created and used within {{< SecureTransport/componentshortname  >}}. A default keystore password is set during installation. For greater security, change the keystore password from the default one before you generate an internal certificate.

Follow these steps to change the keystore password:

1.  Select **Configure > 2-Keystore Password**.  
    The *Keystore Password* pane is displayed.  
    <img src="/Images/SecureTransport/keystore_password.png" class="maxWidth" alt="Keystore Password - Change Password" />
2.  Enter the old keystore password in the **Old Password** field. Leave this field empty if this is the first time you are changing the keystore password and {{< SecureTransport/componentshortname >}} uses the default.
3.  Enter a new password and re-enter the password in the **Confirm New Password** field.
4.  Click **Update** to change the password.  
    A message in the **Keystore Password** tab confirms that the password was changed successfully.

> **Note:**
>
> When you log in to the Administration Tool using the admin account, you can access this page by selecting Setup &gt; Certificates &gt; Keystore Password.
