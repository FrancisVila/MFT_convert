{
    "title": "Login restrictions",
    "linkTitle": "Login restrictions",
    "weight": "270"
}Login restrictions define and restrict the rights of individuals to log in to {{< SecureTransport/securetransportname  >}} Servers or {{< SecureTransport/securetransportname  >}} Edges through the configuration and use of login restriction policies. The configured login restriction policies are applicable to user accounts, account templates, and business units in a hierarchical inheritance and precedence order.

The login restriction policy inheritance order is:

1.  If a policy is not defined on the account or account template level, then the policy of the associated business unit is used.
2.  If a policy is not defined either on the account or account template level or on the business unit level, but a default policy is set, then the default policy applies.
3.  If no policy is set on the account or template, business unit, or default levels, then access is not restricted.

The login restriction policy precedence order is:

1.  If a policy is defined on the account or account template Level, then it takes precedence over the policy assigned on the business unit level.
2.  If no policy is defined on the account or account template Level, then the policy assigned on the business unit level takes precedence.

A single user restriction policy can be selected and set as the default policy. The default policy is the suggested user restriction policy when creating a new business unit, account, or account template but it also applies to users that do not have a corresponding user account and do not match an account template. This enables login restrictions to be defined even for external users who do not have any account definition inside {{< SecureTransport/securetransportname  >}}.

Refer to the following topics to manage user accounts, account templates, and business units:

-   To manage user accounts, refer to <a href="../../accounts/useraccounts" class="MCXref xref">User accounts</a>
-   To manage account templates, refer to <a href="../../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates" class="MCXref xref">Manage account templates</a>.
-   To manger business units, refer to <a href="" class="MCXref xref">Manage business units</a>.

Refer to the following topics to manage login restrictions and create login restriction policies:

-   To manage Login Restriction Policies, refer to <a href="t_st_manloginrestictions" class="MCXref xref">Manage Login Restriction Policies</a>.
-   To mange Login Restriction Policy entries, refer to <a href="t_st_manloginrestictionpolicies" class="MCXref xref">Create Login Restriction Policy entries</a>.
