{
    "title": "Register Address Book provider",
    "linkTitle": "Register Address Book provider",
    "weight": "150"
}Once an Address Book provider is implemented it needs to be registered into the SecureTransport system. To register an Address Book provider, a new file with the name `com.axway.st.plugins.absource.AddressBookProvider` must be created and placed inside the provider `jar` file in the `META-INF/services` folder. The file must contain the full class name of the Address Book provider.

Example:

    com.axway.st.plugins.abcustomsource.sdk.file.provider.
    AddressBookFileProvider

Once the provider is properly packaged, it must be placed inside the `<FILEDRIVEHOME>/lib/jars` folder. On Transaction Manager startup, the provider class will be dynamically loaded and the new Address Book will be registered into the SecureTransport system.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Transaction Manager must be restarted for the changes to be successfully applied.         </td>
      </tr>
</table>
