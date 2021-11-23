{
    "title": "Custom expressions",
    "linkTitle": "Custom expressions",
    "weight": "200"
}You can use the **Custom expression** field to define a user class based on the values of any {{< SecureTransport/componentshortname  >}} user attributes and LDAP attributes include custom attributes. This subsection describes the variables, constants and functions for user class-specific usage of Expression Language (EL).

## User attributes in user class

The following user attributes are supported:

-   `fdxUid` – User ID (UNIX-based systems only)
-   `fdxGid` – Group ID
-   `fdxHomeDir` – Home folder
-   `fdxUserType` – User type
-   `fdxShell` – User shell (UNIX-based systems only)
-   `fdxSysUser` – Name of a local or domain user of the Windows server whose credentials {{< SecureTransport/componentshortname >}} uses to access the Windows files in the session (Windows only)
-   Any custom {{< SecureTransport/componentshortname >}} user attribute defined in the LDAP domain. See [Define attribute mappings for a domain](../../../c_st_authentication/t_st_ldapsettings/t_st_define_attribute_mappings_for_domain#Define).

## LDAP specific attributes

The following variables that represent values from the {{< SecureTransport/componentshortname  >}} LDAP domain that are supported:

-   `LDAP_DOMAIN_ID` – Internal ID
-   `LDAP_DOMAIN_NAME` – Value of the **Domain Name** field
-   `LDAP_DN` – Value of the **Base DN** field
-   `LDAP_AUTH_BY_EMAIL` – Value of the **Login by Email** field, `0` for `Disabled`, `1` for `Enabled`

## SSO specific attributes

The following variables that represent SSO values for {{< SecureTransport/securetransportname  >}} that are supported:

-   `SSO.idpId` – Identity provider Identification.
-   `SSO.email` – SSO user email.
-   `SSO.uid` – UID of the SSO user.
-   `SSO.gid` – GID of the SSO user.
-   `SSO.tenant` – SSO tenant.
-   `SSO.homeDir` – Home directory of the SSO user.
-   `SSO.userName` – SSO user username.

> **Note:**
>
> UID, GID, Email and homeDir SSO attributes should be mapped to SecureTransport as fdxUid, fdxGid, fdxEmail, fdxHomeDir attributes respectively.

## Authenticated user specific attributes

The following variables that represent values from an already authenticated user in {{< SecureTransport/componentshortname  >}} are supported:

-   `DXAGENT_USERGID` - GID of the user

<!-- -->

-   `DXAGENT_USERUID` - UID of the user
-   `DXAGENT_USEREMAIL` - user email
-   `DXAGENT_BUSINESS_UNIT_NAME` - Business unit name
-   `DXAGENT_ACCOUNT_NAME` - Account name
-   `DXAGENT_ACCOUNT_ID` - Account ID
-   `DXAGENT_USERLOGINTYPE` - Account login type
-   `DXAGENT_ACCOUNT_PHONE` - Account telephone number
-   `DXAGENT_ACCOUNT_NOTES` - Account notes
-   `DXAGENT_ACCOUNT_UNLICENSED` - Account licensed property
-   `DXAGENT_ACCOUNT_TYPE` - Account type: Unspecified, Internal, Partner
-   `DXAGENT_ACCOUNT_DELIVERY_METHOD` - Adhoc delivery method
-   `DXAGENT_ACCOUNT_IMPLICIT_ENROLLMENT` - Account implicit enrollment type
-   `DXAGENT_HOMEDIR` - Account home directory
-   `DXAGENT_ACCOUNT_ATTR_USERVARS_keyname` - Account's additional attributes; the value should be surrounded by double quotes " "

> **Note:**
>
> The attributes are not supported for users instantiated from account templates.

> **Note:**
>
> DXAGENT variables will not be evaluated for PeSIT, AS2 and Publish to Account transfers, as actual user login is not performed.

## Map a user based on Login type

{{< SecureTransport/securetransportname  >}} allows you to map a user based on their login type:

-   To map a real user, use `DXAGENT_USERLOGINTYPE="REAL"`
-   To map a virtual user, use `DXAGENT_USERLOGINTYPE="VIRTUAL"`
-   To map a Siteminder user, use `DXAGENT_USERLOGINTYPE="SITEMINDER"`
-   To map the a SSO user, you can use `DXAGENT_USERLOGINTYPE="SSO"`
-   If you want to map the a LDAP user, you can use `DXAGENT_USERLOGINTYPE="LDAP"`

## Supported constants

The following constants are supported:

-   Numeric constants: `-5`, `100`, `.5`, `1.05`, `3.14159D`, `6.0221415e23`, `214748364`, `0xFFECDE5E`
-   Character constants: `'a'`, `'\u0061'`, `'\t'`, `'\u0009'`, `'\n'`, `'\b'`, `'\r'`, `'\f'`, `'\\'`, `'\"'`` `
-   String constants: `"Finance"`, `"US"`, `"^.*@finance\.example\.com$"`
-   Logical constants: `true`, `false`
-   Null constant: `null` (represents no value, so `fdxShell = null` is `true` if that `fdxShell` is not defined)

## Supported functions

The following functions are supported:

-   `isSet("A")` – true if there is a session variable named `A`
-   `memberOf(A, B$collection)` – true if `A` is a member of the multivalued session variable `B`
-   `toInt(A)` – converts `A` to an integer
-   `toString(A)` – converts `A` to an string

## Supported operators

{{< SecureTransport/componentshortname  >}} evaluates the expression based on the following operator precedence from highest to lowest:

-   Logical unary `not`
-   Arithmetic unary `+` and `-`
-   Arithmetic binary `*`, `/`, and `%` (integer remainder)
-   Arithmetic binary `+` and `-`
-   String concatenation `+`
-   Numeric, date and string comparison `>`, `>=`, `<`, `<=`, and `like`
-   Logical, numeric, date, and string comparison `=` and `<>`
-   Logical `and`
-   Logical `or`
-   Conditional expression `A ? B : C` (which has the value *`B`* if *`A`* is `true` or *`C`* if *`A`* is not `true`)

Use parentheses to group expressions and override the operator precedence.

{{< SecureTransport/componentshortname  >}} dynamically converts numeric expressions to long integers, single-precision real numbers, or double-precision real numbers when it is necessary to evaluate an operator. When an operator requires a logical value, {{< SecureTransport/componentshortname  >}} converts any value of a type other than logical to `false`.

The `like` operator matches its string left operand against a string right operand that is a Java regular expression. The result is `true` if the regular expression matches all of the left operand. The backslash (`\`) is the escape character Java regular expressions, so, in a regular expression, use two backslashes (`\\`) to match a backslash. See the examples.

## Example usage

The following expression checks for virtual users who are in one of three groups:

`fdxUserType = "virtual" and (fdxGid = 1200 or fxdGid = 1400 or fdxGid = 1500)`

The following expression tests the prefix of the user home directory on a Windows system:

`fdxHomeDir like "C:\\home\\users\\finance\\.*"`

The following two expressions return the same result, checking the email address against different regular expressions depending on the UID:

`fdxUid > 100 and fdxUid <= 200 and fdxEmail like ".*@finance\.example\.com" or fdxEmail like ".*@hr\.example\.com"`

`fdxEmail like (fdxUid > 100 and fdxUid <= 200 ? ".*@finance\.example\.com" : ".*@hr\.example\.com")`

**Related topics:**

-   [Default user classes](../c_st_default_user_classes)
-   [Manage user classes](../t_st_userclasses)
