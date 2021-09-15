{
    "title": "Address Book sources",
    "linkTitle": "Address Book sources",
    "weight": "330"
}The Address Book feature has two built-in address book sources – Local source and LDAP source. These two sources become available by default when the Address Book functionality is enabled. Multiple custom address book sources can also be registered on the SecureTransport server.

## Local source

The local Address Book source includes local SecureTransport accounts with registered e-mails and has two options for specifying the address book entries:

-   Own Business Unit – This includes entries which belong to the same business unit as the account to which the local source is assigned (including sub business units).
-   All Business Units – This includes all virtual accounts in SecureTransport server which have associated email address.

All entries are populated in a tree structure; for example, there is one parent group for all entries – Parent Display Group. This parent group name is based (evaluated) on the Address book source configuration – either account, business unit, or global level. Each business unit is also considered a parent group to all accounts that belong to it. So each account produces an address book user entry with the parent group as its business unit (or the parent group defined for the local source if the account does not have a business unit) and each business unit produces an address book group entry. If there are nested business units, the result address book entries structure is nested in the same way.

## <span id="LDAP"></span>LDAP source

The LDAP source specific settings are defined in the LDAP configuration page. For configuration information on defining the Address Book Settings for a domain, refer to [Define Address Book settings for a domain](../../../c_st_authentication/t_st_ldapsettings/t_st_define_ab_settings_for_domain).

The Address Book entry map settings, as well as search query, are exposed into the LDAP configuration page. There are 3 predefined properties for an entry:

-   Display name
-   Primary email
-   Parent group

The mapping configurations allow defining new properties, which can be extracted from the LDAP object. All additionally added key value pairs are populated as custom properties of the address book entry.

When fetching new entries from the LDAP source, if a `parentGroup` mapping has been specified by the SecureTransport administrator, its value will override the `parentGroup` value defined for the LDAP source. For example, the LDAP source is configured as an Address Book data source, it is enabled, has LDAP Source as its parent group, and the `parentGroup` property has been mapped to the LDAP attribute group. All entries which are fetched from this source will override the LDAP source value and will map the value of the group attribute to the `parentGroup` property instead. In other words, only the direct parent of an entry will be displayed in its `parentGroup` property.

All entries are populated in a tree structure; for example, there will be one parent group (root) for all LDAP entries. The parent group name is based (evaluated) on the Address Book source configuration – either account, business unit, or global level. All nested parent groups will depend on the `parentGroup` attribute mapping. In other words, the tree structure of entries returned by the LDAP server will be attached as child of the evaluated root parent group, defined for the LDAP source. In that case, all LDAP groups and user entries which do not belong to a group will be considered as direct children of the root parent group. This allows all entries coming from a source to be addressed using a single display name – the source Parent Display Group.

## Custom source

For instructions on how to implement a custom Address Book source, refer to the *SecureTransport Developer's Guide*.
