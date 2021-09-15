{
    "title": "SecureTransport Swagger REST\u00a0API  integration",
    "linkTitle": "SecureTransport Swagger REST\u00a0API  integration",
    "weight": "70"
}The SecureTransport Swagger REST API can be integrated into API Manager. Once the Swagger REST API is integrated into API Manager, the Frontend API and its Swagger definition from API Manager can be used to acquire a Java Client on API Gateway.

This topic provides the prerequisites and instructions for integrating SecureTransport Swagger REST API into API Manager.

## Prerequisites

The following prerequisites must be met prior to Swagger REST API being integrated in API Manager:

-   SecureTransport Server must be installed, configured, and running.
    -   The HTTPS and/or the Admin daemons (for the Client and the Admin APIs respectively) must be configured with certificates with CN - the IP address of the SecureTransport and no empty fields. API Gateway requires the fields to be completed.
-   API Gateway and API Manager must be installed, configured, and running on a machine other than the SecureTransport server machine.

## Limitation

When a Single Sign-On end-user logout is performed (**DELETE** request to `~/myself` resource), the server returns an **Error**.

This is caused by Swagger sending a standardized cURL request : `curl –X DELETE ~` .

The SSO logout uses **Redirects**, with a standardized **Request** from Swagger using **Redirects** is not possible. However, cURL has means to control redirect behavior through an additional option `-L`. The `-L` option instructs cURL to use the redirect method instead of re-using the initial request method: **DELETE** in this use case.

## Integration

The take the following steps to integrate Swagger REST API into API Manager:

1.  Log into API Manager with an administrator's account.
2.  Navigate to **API Registration > Backend API > New API -> Import Swagger API**.
3.  Compete the following fields:
    -   *Source:* Swagger definition URL

    -   *URL:*`https://<st_host>/api/v2.0/docs/swagger.json`

    -   <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><code>&lt;st_host&gt;</code> is the host or IP of the machine, on which <span>SecureTransport</span> Server is installed. Specifying port 444 will point to the Admin daemon – used for the Admin API.         </td>      </tr></table>

    -   *API name:* Enter the desired name.

    -   *Organization:* Pick an existing one or create a new one. To create a new one, navigate to **Client Registry > Organizations > New Organization**.

    -   *Authentication:* Enter the User credentials or Admin credentials for the Client API and Admin API respectively.

    -   <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The current version of API Manager only supports swagger definitions in JSON format.         </td>      </tr></table>
4.  Click **Import**.
5.  Navigate to **API Registration > Frontend API > New API > New API from Backend API** and select the alias of the imported API.  
    If you receive an "Internal server error", refresh the page (F5) and the new Frontend API will appear in the list. The error is probably caused by the missing optional *Host* field in the Swagger definition.
6.  On the **Frontend API** tab click on the alias of created API to configure it as follows:
    -   *Inbound:*
        -   *Security:***Pass Through**
        -   *Resource path:* The path which will be exposed to the user for the API. The path must be unique.
    -   *Outbound:*
        -   *Authentication profile:***No authentication**

        -   *Backend service URL:*`https://<st_host>/api/v2.0`

        -   <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Setting <strong>Pass Through</strong> inbound and <strong>No authentication</strong> outbound means that API Gateway will allow the <span>SecureTransport</span> Server to process authentication requests. If you want to implement custom authentication in API Manager, refer to <a href="#api%c2%a0auth">API authentication</a>.         </td>      </tr></table>
    -   *Trusted Certificates:* Click the **Add** (+) icon.
        -   *Source:***URL**
        -   *URL:*`https://<st_host>`
        -   *Use for outbound:***Yes**
        -   *Use for inbound:***No**
        -   This will import the certificate from a daemon in SecureTransport – HTTPS or Admin. This certificate should have CN: IP of the SecureTransport and no empty fields. Empty fields will cause run-time internal server errors since API Gateway is sensitive to them.
7.  Click **Save**.
8.  On the **Frontend API** tab, select the alias of new API and then click **Manage selected > Publish**.  
    The Frontend API can only be configured only if not published. To unpublish the Frontend API, select the alias of the new API and then click **Manage selected > Unpublish**.

## API description

API Manager provides Swagger definitions for Frontend APIs. To access one:

1.  Navigate to **API Catalog**.
2.  Click on the alias a Frontend API.
3.  Click **Download Swagger 2.0**.

A text file containing the Swagger definition in JSON format should start downloading.

## <span id="API auth"></span>API authentication

This section provides information how to setup basic authentication on the API Gateway for SecureTransport.

1.  Navigate to **API Registration > Frontend API >** Select the API to edit **&gt; Outbound**.
2.  Set *Authentication profile* to **HTTP Basic** and provide a valid SecureTransport username and password.
3.  Navigate to **Inbound** and set *Security* to **HTTP Basic**.
4.  Navigate to **Client registry > Applications**.
5.  Create a new application:
    1.  Specify the desired API's organization.
    2.  Under *API ACCESS*, click on **Add API** and select the desired API.
    3.  Click **Create**.
    4.  Under **Authentication > API KEYS**, create as many API keys as you need.
    5.  Each API Key and its corresponding secret can be used as username/password pair for authentication on a Frontend API.

This setup represents a simple scenario. If you would like to setup advanced authentication and authorization methods, refer to the API Gateway documentation.

 
