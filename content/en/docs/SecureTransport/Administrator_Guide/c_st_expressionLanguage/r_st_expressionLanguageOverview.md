{
    "title": "Expression Language overview",
    "linkTitle": "Expression Language overview",
    "weight": "270"
}Many features of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> use expressions. The expression language <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses is based on the Sun JSP Expression Language. Only the syntax listed in this appendix is supported by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, any other syntax is not guaranteed to function properly.

The following <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> features can use the expression language:

-   Transfer site post-transmission actions
-   Subscription post-transmission actions
-   PGP
-   Account templates

> **Note:**
>
> If an account template and its transfer site are defined using expressions, you cannot restart failed transfers for that account template using the Resubmit button on the File Tracking page.

This appendix provides a list of the supported syntax with examples.

> **Note:**
>
> When creating expressions that use file paths you must use the forward slash (/) regardless of the platform where the file path is located. For example, instead of writing c:\\tmp\\${stenv\['loginname'\], write c:/tmp/${stenv\['loginname'\].
