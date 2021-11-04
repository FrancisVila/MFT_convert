{
    "title": "Define LDAP search criteria for a domain",
    "linkTitle": "Define LDAP search criteria for a domain",
    "weight": "320"
}For information about how <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses the search criteria, see <a href="../../c_st_ldap_connections_binds_searches#LDAP2" class="MCXref xref">LDAP connections, binds, and searches</a>.

> **Note:**
>
> A specific LDAP configuration is required for Active Directory. For details, see LDAP and Active Directory configuration.

If you do not have the *New LDAP Domain* page open, select **Authentication &gt; LDAP Domains** and click the domain name in the Domains List to open the *LDAP Domain* page.

Under *LDAP Searches*, there are two interchanging ways to proceed:

-   do not use the **Generic LDAP Search filter** (default) – uses the Alias Query for LDAP search
-   use the **Generic LDAP Search filter** check-box – enables two options:
    -   Generic Search Filter by any LDAP attribute without appending
    -   Generic Search Attribute used for user configuration mapping

For more information, see the dedicated subtopics that follow.

## Do not use Generic LDAP search

Add the LDAP search without selecting the **Use Generic Search filter** check-box.

Fill in the search criteria as described below:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Valid values and notes         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Base DN         </td>
         <td>Define the base DN for the searches         </td>
         <td><p>A valid DN, such as,</p>
<p><code>OU=Sales</code>, <code>DC=ldaps1</code>, <code>DC=Example</code>, <code>DC=com</code></p>         </td>
      </tr>
      <tr>
         <td>Search Attributes         </td>
         <td>Select the LDAP attribute to use for the searches         </td>
         <td>User ID (<code>uid</code>), Common Name (<code>cn</code>), or SAM-Account-Name (<code>sAMAccountName</code>)         </td>
      </tr>
      <tr>
         <td>Alias Query         </td>
         <td>Define a filter using values from an email address used as a login user name         </td>
         <td><p>The query to be used with the LDAP search. Read further this subtopic for additional info on syntax and usage.</p>         </td>
      </tr>
   </tbody>
</table>

Once you are done, click **Save**.

The **Alias Query** field is used to perform real user look-up by email address to filter (limit) the search. If the **Alias Query** filter is selected, the search is performed not only by email but by email OR the specified filter in the **Alias Query** field. The real user look-up also returns only PERSON entities and no other object classes. So, you do not have to add attribute (`objectClass=Person`) in the field because <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> inserts it in the filter. The value of the **Alias Query** field uses the search filter syntax described in *RFC 4515: Lightweight Directory Access Protocol (LDAP): String Representation of Search Filters (June 2006)*, (<http://www.rfc-editor.org/rfc/pdfrfc/rfc4515.txt.pdf>).

The basic syntax of a search filter is:

(`attribute search_operator value`)

For example:

(`buildingname>=alpha`)

In this example, buildingname is the attribute, `>=` is the operator, and `alpha` is the value. You can also define filters that use different attributes combined together with logical operators.

## Use Generic LDAP search filter

Select the **Use Generic Search filter** check-box and observe the following changes in the *LDAP Searches* options:

-   the **Search Attribute** drop-down list is replaced with the **Generic Search Attribute** input text box
-   **Alias Query** input text box is replaced by **Generic Search Filter** input text box

You can add any Generic Search attribute to use in the Generic search filter query. Note that the Generic LDAP search is used as it is and no additional attributes are appended.

<img src="/Images/SecureTransport/LDAP-search-generic.png" class="maxWidth" alt="Generic LDAP search filter" />

Fill in the search criteria as described below:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Valid values and notes         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Base DN         </td>
         <td>Define the base DN for the searches         </td>
         <td><p>A valid DN, such as,</p>
<p><code>OU=Sales</code>, <code>DC=ldaps1</code>, <code>DC=Example</code>, <code>DC=com</code></p>         </td>
      </tr>
      <tr>
         <td>Generic Search Attribute         </td>
         <td>Specify any LDAP property for user configuration mapping         </td>
         <td>Example values include: Common Name (<code>cn</code>), <code>displayName</code>, <code>givenName</code>, <code>sAMAccountName</code>, User ID (<code>UID</code>)
<p>Use the tooltip for example usage.</p>         </td>
      </tr>
      <tr>
         <td>Generic Search Filter         </td>
         <td>Specify the query that will be used for performing LDAP search         </td>
         <td><p>Basic prefix logical operators (&amp;, |, !) can be used.</p>
<p>SecureTransport allows referencing the following values by replacing them:</p>
<ul>
<li>%s – Complete email address. ( SecureTransport replaces %s in the value with the complete email address.)</li>
<li>%u – User name. (SecureTransport replaces %u with the user name.).</li>
<li>%keyFromPlugin – (It will be replaced with the value of "keyFromPlugin" coming from the plugin context.)</li>
</ul>
<p>Use the tooltip to see the correct query syntax and the accepted values.</p>         </td>
      </tr>
   </tbody>
</table>

Once you are done, click **Save**.

> **Note:**
>
> The Generic LDAP search filter can access the Plugin Context, part of the PluginUserData object.Values from this plugin context are accessible using the syntax as in the following example: (mail=%subjectAltNameEmail).As subjectAltNameEmail is the key and if its value is "someemail@mail.com" the generic search filter evaluates to mail=someemail@mail.com

  
The following topics provide basic prefix logical operators, attribute names, search filter operators, special characters in search filters, special values, and LDAP configuration example using the Alias Query filter:

-   <a href="#Basic" class="MCXref xref">Basic prefix logical operators</a>
-   <a href="#Attribut" class="MCXref xref">Attribute names</a>
-   <a href="#Search" class="MCXref xref">Search filter operators</a>
-   <a href="#Special" class="MCXref xref">Special characters in search filters</a>
-   <a href="#Special2" class="MCXref xref">Special values</a>
-   <a href="#LDAP" class="MCXref xref">LDAP configuration using the Alias Query filter</a>

**Related topics:**

-   <a href="../t_st_create_domain" class="MCXref xref">Create an LDAP domain</a>
-   <a href="../t_st_define_ldap_user_settings_for_domain" class="MCXref xref">Define LDAP user settings for a domain</a>
-   <a href="../t_st_define_attribute_mappings_for_domain" class="MCXref xref">Define attribute mappings for a domain</a>
-   <a href="../t_st_manage_dn_filters_for_domain" class="MCXref xref">Manage DN filters for a domain</a>
-   <a href="../t_st_add_dn_filter" class="MCXref xref">Manage DN filters</a>
-   <a href="../t_st_define_ab_settings_for_domain" class="MCXref xref">Define Address Book settings for a domain</a>
-   <a href="../t_st_edit_domain" class="MCXref xref">Edit a domain</a>
-   <a href="../t_st_delete_domains" class="MCXref xref">Delete domains</a>
-   <a href="../t_st_configure_default_domains" class="MCXref xref">Configure default domains</a>
-   <a href="../c_st_ldap_domains_example" class="MCXref xref">LDAP domains example</a>
-   <a href="../c_st_secure_ldap" class="MCXref xref">Secure LDAP</a>
-   <a href="../c_st_ldap_active_directory_configuration" class="MCXref xref">LDAP and Active Directory configuration</a>

<span id="Basic"></span>

## Basic prefix logical operators

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Operator         </th>
<th class="HeadE-Column1-Header1">Symbol         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>AND         </td>
         <td>&amp;         </td>
         <td>All specified filters must be true for the statement to be true. For example: <code>(&amp;(filter)(filter)(filter)...)</code>         </td>
      </tr>
      <tr>
         <td>OR         </td>
         <td>|         </td>
         <td>At least one specified filter must be true for the statement to be true. For example: <code>(|(filter)(filter)(filter)...)</code>         </td>
      </tr>
      <tr>
         <td>NOT         </td>
         <td>!         </td>
         <td>The specified statement must not be true for the statement to be true. Only one filter is affected by the NOT operator. For example: <code>(!(filter))</code>         </td>
      </tr>
   </tbody>
</table>

Logical expressions are evaluated in the following order: - Innermost to outermost parenthetical expressions first - All expressions from left to right. So, you can use parentheses ( and ) to specify the order of operations.

For example:

The following example returns users that match attribute `objectClass` value with `Person` and attribute `cn` matches `Babs J*` where `*` means matching of zero or more characters.

`(&(objectClass=Person)(cn=Babs J*))`

The following example returns entries containing attribute values that do not match the specified value.

`(!(cn=Tim Howes))`

<span id="Attribut"></span>

## Attribute names

Attribute names depend on the type of LDAP server. For Active Directory servers where the standard alias attribute is `proxyAddresses` an example for the filter is `(proxyAddresses=smtp\3A%s)`. For other LDAP servers an example can be `(|(cn=%u)(mail=%s))`. This will find all users with given primary email address or common name.

Examples for attributes:

<table>
   <tbody>
      <tr>
         <td>uid         </td>
         <td>User ID         </td>
      </tr>
      <tr>
         <td>cn         </td>
         <td>Common Name         </td>
      </tr>
      <tr>
         <td>sn         </td>
         <td>Surname         </td>
      </tr>
      <tr>
         <td>l         </td>
         <td>Location         </td>
      </tr>
      <tr>
         <td>ou         </td>
         <td>Organizational unit         </td>
      </tr>
      <tr>
         <td>o         </td>
         <td>Organization         </td>
      </tr>
      <tr>
         <td>dc         </td>
         <td>Domain Component         </td>
      </tr>
      <tr>
         <td>st         </td>
         <td>State         </td>
      </tr>
      <tr>
         <td>c         </td>
         <td>Country         </td>
      </tr>
   </tbody>
</table>

<span id="Search"></span>

## Search filter operators

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Search type         </th>
<th class="HeadE-Column1-Header1">Operator         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Equality         </td>
         <td><code>=</code>         </td>
         <td><p>Returns entries containing attribute values that exactly match the specified value.</p>
<p>For example:</p>
<p><code>cn=Bob Johnson</code></p>         </td>
      </tr>
      <tr>
         <td>Substring         </td>
         <td><code>=string*string</code>         </td>
         <td><p>Returns entries containing attributes containing the specified substring.</p>
<p>For example:</p>
<p><code>  cn=Bob*</code></p>
<p><code>cn=*Johnson</code></p>
<p><code>cn=*John*</code></p>
<p><code>cn=B*John</code></p>
<p>The asterisk (<code>*</code>) indicates zero (0) or more characters.</p>         </td>
      </tr>
      <tr>
         <td>Greater than or equal to         </td>
         <td><code>&gt;=</code>         </td>
         <td><p>Returns entries containing attributes that are greater than or equal to the specified value.</p>
<p>For example:</p>
<p><code>buildingname &gt;= alpha</code></p>         </td>
      </tr>
      <tr>
         <td>Less than or equal to         </td>
         <td><code>&lt;=</code>         </td>
         <td><p>Returns entries containing attributes that are less than or equal to the specified value.</p>
<p>For example:</p>
<p><code> buildingname &lt;= alpha</code></p>         </td>
      </tr>
      <tr>
         <td>Presence         </td>
         <td><code>=*</code>         </td>
         <td><p>Returns entries containing one or more values for the specified attribute.</p>
<p>For example:</p>
<p><code>cn=*</code></p>
<p><code>telephonenumber=*</code></p>
<p><code>manager=*</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Special"></span>

## Special characters in search filters

Use backslash (`\`) followed by two hexadecimal digits to specify any special character or non-ASCII UTF-8 characters.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Special character         </th>
<th class="HeadE-Column1-Header1">Value with special character         </th>
<th class="HeadD-Column1-Header1">Example filter         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>*</code>         </td>
         <td><code>Five*Star</code>         </td>
         <td><code>(cn=Five\2aStar</code>)         </td>
      </tr>
      <tr>
         <td><code>\</code>         </td>
         <td><code>c:\File</code>         </td>
         <td><code>(cn=c:\5cFile)</code>         </td>
      </tr>
      <tr>
         <td><code>()</code>         </td>
         <td><code>John (2nd)</code>         </td>
         <td><code>(cn=John \282nd\29)</code>         </td>
      </tr>
      <tr>
         <td><code>NUL</code>         </td>
         <td><code>0004</code>         </td>
         <td><code>(bin=\00\00\00\04)</code>         </td>
      </tr>
      <tr>
         <td>non-ASCII UTF-8 characters         </td>
         <td>          </td>
         <td><code>sn=Lu\c4\8di\c4\87)</code>         </td>
      </tr>
   </tbody>
</table>

<span id="Special2"></span>

## Special values

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> enables to reference the following values by replacing them:

`%s` – Complete email address. ( <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> replaces `%s` in the value with the complete email address.)

`%u` – User name. (SecureTransport replaces `%u` with the user name.)

`%d` – Domain name. (SecureTransport replaces `%d` with the domain.)

Examples:

`(proxyAddresses=smtp\3A%s) - proxyAddresses`

Active Directory attribute must be smtp: followed by the email address.

`(proxyAddresses=smtp:testuser@domain.com) (|(cn=%u)(mail=%s))`

Either the cn attribute is the user name or the mail attribute is the email address.

`(|(cn=testuser)(mail=testuser@domain.com))`

<span id="LDAP"></span>

## LDAP configuration using the Alias Query filter

1.  Enable `Login by Email` in the *LDAP User Settings* pane on the *LDAP Domain Settings* page.
2.  For two LDAP users a1 and b1, having the same settings, add new LDAP attributes:
    -   For user a1 add attribute: `mobile = a1@st1.lab.sofi.axway.int`
    -   For user b1 add attribute: `mail = b1@st1.lab.sofi.axway.int`
3.  The users exist on same domain in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. So, create two new attributes in the *Attributes List* section on the *LDAP Domain Settings* page and map them to the LDAP attributes:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1"><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> attribute name         </th>
    <th class="HeadD-Column1-Header1">LDAP attribute name         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><code>fdxAuthByEmail</code>         </td>
             <td><code>mail</code>         </td>
          </tr>
          <tr>
             <td><code>fdxAuthByOwn</code>         </td>
             <td><code>mobile</code>         </td>
          </tr>
       </tbody>
    </table>
4.  Alias Queries examples:
    -   No matter what search criteria the administrator has to set in the **Alias Query** field, the LDAP user can always authenticate using his `uid` (User ID), `cn` (Common Name) and `sAMAccountName` (SAM-Account-Name) search attributes.
    -   Using an `&` operation joins all filters together and all conditions should be true.
    -   Using and `|` requires at least one true condition.
    -   If we filter an e-mail with `%u` (username) only, the user with this attribute will be allowed to login only by providing a username. Try the following queries:
        -   `(mail=%u)` - the result filter will be `(&(objectClass=Person)(mail=%u))`. User b1 has mail attribute which represents the full e-mail. So, it is different from the username (`%u`) and e-mail login for user b1 will fail.
        -   `(&(mobile=%u)(mail=%u))` - the result filter will be `(&(objectClass=Person)(&(mobile=%u)(mail=%u)))`. User b1 has mail attribute and user a1 has mobile attribute different from the username, so e-mail login for users a1 and b1 will fail.
    -   If we filter an e-mail with `%s` (full e-mail address) only, the user with this attribute will be allowed to login by providing both a username or a password. Try the following queries:
        -   If **no query** is set, the result filter will be `(&(objectClass=Person)(mail=%s))`. The mail authentication of user a1, with only mobile attribute defined, fails, because we haven't set an e-mail login permissions for the mobile attribute in the search filter. Mail authentication for b1 is successful because by default SecureTransport searches by e-mail with filter `(mail=%s)`.
        -   `(mobile=%s)` - We haven't provided additional filtering for mail attribute. The result filter will be `(&(objectClass=Person)(|(mobile=%s)(mail=%s))`. E-mail login for user b1 will be successful. In the filter we have `(mail=%s)` and user b1 have mail attribute references the full e-mail address. For user a1 we have mobile attribute which references the full e-mail address, so e-mail login for a1 will also be successful.
        -   `(&(mail=%u)(mobile=%s))` - the result filter will be `(&(objectClass=Person)(&(mail=%u)(mobile=%s)))`. Mail attribute in the filter allows only username login, so e-mail authentication for user b1 which mail attribute references the full e-mail address will fail. Mobile attribute in the filter allows full e-mail authentication, so for user a1 the e-mail authentication will be successful.
    -   Filter with `%d` (domain name) identifies domain name:
        -   `(mobile=%u@%d) equals (mobile=%s)` - the result filter will be `(&(objectClass=Person)(|(mobile=%u@%d)(mail=%s)))`. The search filter allows user a1 with mobile attribute to authenticate using the full e-mail. User b1 will be also authenticated successfully with his mail attribute.
        -   `(|(mobile=%u@%d)(mail=%u))` - the result filter will be `(&(objectClass=Person)(|(mobile=%u@%d)(mail=%u)))`. The search filter allows user a1 with attribute mobile to be authenticated by full e-mail address and denies user b1 authentication with the full e-mail.
    -   If we have two different mail addresses for one account - for example: attribute `mail = x@a.b` and attribute `mobile = y@a.b` the login will be successful by default for `x@a.b`, unless we define the following query `(mobile=%s)`.

> **Note:**
>
> In Active Directory the proxyAddress is the only possible property that we can use for mail attribute (after the primary mail), so we can use filtering with the following query: (proxyAddresses=smtp\\3A%s).
