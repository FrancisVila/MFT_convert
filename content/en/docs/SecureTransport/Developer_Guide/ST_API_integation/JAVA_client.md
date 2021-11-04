{
    "title": "Acquiring a Java Client for a Frontend API on API Gateway",
    "linkTitle": "Acquiring a Java Client for a Frontend API on API Gateway",
    "weight": "90"
}This topic provides the prerequisites and instructions for acquiring a Java client for a Frontend API on API Gateway.

## Prerequisites

The following prerequisites must be met prior to acquiring a JAVA client for a Frontend API on API Gateway:

-   Registered and published Frontend API in API Manager and its Swagger definition.

-   JRE 8 with installed Java Cryptographic Extension (JCE) 8.  

    > **Note:**
    >
    > API Gateway is configured to be accessed via a TLS secured connection only using a cipher suite that is available in JCE 8.

## Generating client source code from Swagger definition

The take the following steps to generate client source code from a Swagger definition:

1.  Go to <http://editor.swagger.io/#/>.
2.  Click **File > Paste JSON**.
3.  Paste the Swagger definition from API Manager and click **Import**.
4.  Click **Generate Client > Java**.

An archive containing the source code should start downloading.

There is a test in the `io.swagger.client.api` package that shows a general usage of the generated client code. `DefaultApi` class is the entry point to the API.

> **Note:**
>
> Missing libraries can be acquired by importing the code into a maven project.

## Configuring the code for <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> API in API Gateway

The API Gateway trust and authentication must be configured for the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> API in API Gateway.

### API Gateway trust

The client code is transferred to the API Gateway via TLS secure protocol. In addition to the uncommon cipher suite, the client code communication also uses a self-signed certificate and a not-trusted host. The certificate can be imported in the JVM’s key store, while host trust is acquired using the OK HTTP (<http://square.github.io/okhttp/>) framework code generated for HTTP request-response modeled communication.

#### Importing API Gateway certificate

To import the API Gateway certificate:

1.  Download or extract the API Gateway certificate.  
    API Manager uses the same certificate for HTTPS. It can be extracted from a browser.

2.  Locate the JRE keytool application.  
    The default location is `<jre8_home>/bin`.

3.  Execute the following command:  
    `keytool -import -v -trustcacerts -alias <alias> -file <certificate> -keystore <store_name> -storepass <password>`, where:

    -   `<alias>` - (string) - Alias for the imported certificate. The alias must be unique for the store.
    -   `<certificate>` - The file containing the certificate of API Gateway.
    -   `<store_name>` - The key store used by your JVM. The default key store is `cacerts.jks`.
    -   `<password>` - The password for the keystore. The default password for the `cacerts.jks` data key store is **changeit**.

      

    > **Note:**
    >
    > On Microsoft Windows, execute the command as an administrator.

#### Trusting API Manager host

Trusting the API Manager host can be done by providing a custom host verification:


    final DefaultApi api = new DefaultApi();
    final ApiClient apiClient = api.getApiClient();
    // allow only the API Gateway host
    apiClient.getHttpClient().setHostnameVerifier(new HostnameVerifier()
    {
        @Override
        public boolean verify(String hostname, SSLSession session) {
            // check if hostname is the IP of API Gateway
            return "10.232.3.104".equals(hostname);
        }
    });

### Authentication

Authentication is completed by the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Server , but API Gateway does not know what authentication method is being used and as a result the generated code assumes that there is no authentication. <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> REST API uses Basic HTTP authentication – username and password credentials. The Basic HTTP authentication has to be manually implemented in the code as follows:

1.  The `authentications` property in the `io.swagger.client.ApiClient` class has to contain the following mapping:  
    `"HTTPBasic" -> new HttpBasicAuth()`

2.  In the `io.swagger.client.api.DefaultApi` class, several methods make a call to `apiClient.buildCall()` method, providing a string array as a parameter called `authNames`. This array must contain the string `"HTTPBasic"`.

3.  Credentials must be also provided using instructions similar to the following:  


        final DefaultApi api = new DefaultApi();
        final ApiClient apiClient = api.getApiClient();
        apiClient.setUsername(“admin”);
        apiClient.setPassword(“admin”);

> **Note:**
>
> The credentials are provided as an example. Ensure that you are using a valid admin account or Admin API. For the Client API, ensure that you use the credentials of a valid user account.
