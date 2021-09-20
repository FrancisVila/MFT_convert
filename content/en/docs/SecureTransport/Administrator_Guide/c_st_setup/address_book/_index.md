{
    "title": "Address Book",
    "linkTitle": "Address Book",
    "weight": "310"
}The Address Book feature provides built-in and custom address books data sources to the SecureTransport server. End users are allowed via the ST Web Client to send messages or share folders to a predefined list (address book) of users and groups. End users are able to send or share folders directly by using the display name defined in the address book. Implementing Address Book functionality allows SecureTransport administrators to control the users’ collaboration with external (non-address book) users.

The global Address Books configuration page is found at **Setup &gt; Address Books**. There you can configure the global address book sources list, enable or disable global address books, and determine whether or not to allow address book collaboration. To configure the global address book sources list, refer to [Address Book global configuration](address_book_conf).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Address Book Sources</em> page is only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>).         </td>
      </tr>
</table>

The Address Book sources list configuration for each business unit can be inherited from the global Address Book sources list configuration or changed for the current business unit. To configure Address Book sources list for a business unit, refer to [Address Book business unit level configuration](address_book_conf).

For individual accounts the Address Book sources list can be inherited or overwritten. To configure the Address Book sources list for an account, refer to [Address Book account level configuration](address_book_conf).

Additionally, the LDAP address book settings can be configured. To configure the LDAP address settings, refer to [LDAP domains](../../c_st_authentication/t_st_ldapsettings).
