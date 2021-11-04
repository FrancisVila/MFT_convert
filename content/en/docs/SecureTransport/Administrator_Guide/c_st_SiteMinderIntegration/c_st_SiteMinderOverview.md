{
    "title": "SiteMinder overview",
    "linkTitle": "SiteMinder overview",
    "weight": "120"
}Netegrity SiteMinder is a third-party application that controls user access to secured applications and provides a Single Sign-On (SSO) portal. A Single Sign-On portal is a Web gateway or proxy that enables users to access multiple secured Web applications using a single user name and password that are provided once only at the start of the user session.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can be integrated into a SiteMinder SSO environment. When integrated, users can authenticate for HTTP and HTTPS using SiteMinder SSO. They can authenticate for other protocols though SiteMinder using user name and password, but not using SSO.

The following illustration shows how <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can be integrated into a typical SiteMinder environment.

<img src="/Images/SecureTransport/SiteMinder_SampleIntegrationModel.png" class="maxWidth" alt="Integration of SecureTransport into a SiteMinder deployment" />

<span class="autonumber"></span>Integration of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> into a SiteMinder deployment

Typically, in a SiteMinder SSO environment, users log onto the SSO portal using a Browser Client. The SSO portal directly handles all user authentication and access control for the secured Web applications in the SiteMinder network. However, because <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports command line clients, it requires more control over authentication and authorization than a typical Web application. The following topic describes how <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user authentication and authorization is handled in a SiteMinder environment.
