{
    "title": "Session terminates due to CSRF protection",
    "linkTitle": "Session terminates due to CSRF protection",
    "weight": "330"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> implements token-based cross-site request forgery (CSRF) protection. This prevents a user who is logged in to a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> web client from
causing unwanted modification of user data,
such as uploading or deleting a file, by opening a malicious web page or clicking a crafted link in another
browser tab or window. When the CSRF protection detects a violation, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> marks the session as expired and logs out the user.

If an HTTP client identifies itself with a User-Agent string, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> matches the string against a white list of clients represented by a Perl-compatible regular expression. If the User-Agent string matches, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not perform CSRF protection. By default, the white list is `(^SecureTransport|^Axway/SecureClient|^Axway/EndPoint|Java|^curl/|^Jakarta Commons\-HttpClient)`.

To configure a different white list, save the regular expression in the `Http.UserAgentWhiteList` server configuration parameter. To exclude another client from CSRF protection, add a pattern that matches the User-Agent string for that client to the regular expression. For example, to exclude Wget in addition to the clients in default, set the value of the `Http.UserAgentWhiteList` server configuration parameter to `(^SecureTransport|^Axway/SecureClient|^Axway/EndPoint|Java|^curl/|^Jakarta Commons\-HttpClient|^Wget)`. If the value of the `Http.UserAgentWhiteList` server configuration parameter is empty, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses the default white list.

**Related topics:**

-   <a href="../t_st_license_issues" class="MCXref xref">License issues</a>
-   <a href="../t_st_connectivity_to_server_failed" class="MCXref xref">Connectivity to server failed</a>
-   <a href="../t_st_siteminder_issues" class="MCXref xref">SiteMinder issues</a>
-   <a href="../c_st_ldap_issues" class="MCXref xref">LDAP issues</a>
-   <a href="../c_st_file_system_commands_not_functional" class="MCXref xref">File system commands not functional</a>
-   <a href="../c_st_cannot_log_edge" class="MCXref xref">Cannot log in to SecureTransport Edge</a>
-   <a href="../c_st_client_certificate_authentication_fails" class="MCXref xref">Client certificate authentication fails</a>
