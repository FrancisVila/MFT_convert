{
    "title": "Pluggable authentication",
    "linkTitle": "Pluggable authentication",
    "weight": "100"
}This section describes the capability of {{< SecureTransport/securetransportname  >}} Server to use custom authentication plug-ins for executing custom authentication logic and provides instructions on how to implement and configure a Custom Authenticator.

{{< SecureTransport/componentshortname  >}} {{< SecureTransport/componentversion  >}} provides an Pluggable Authentication SPI (Service Provider Interface ) - a set of Java interfaces and services you can use to create, configure, and register custom authenticators to a {{< SecureTransport/componentshortname  >}} Server. It allows developers to implement custom authentication logic for authenticating users and administrators.

The Pluggable authentication SPI is part of the SecureTransport Software Development Kit (SDK) which can be downloaded from {{< SecureTransport/supportwebsite  >}} at [support.axway.com](http://support.axway.com/).

To access the authentication SPI, unzip the SDK and open the `CustomAuthentication/lib` folder. The `lib `folder contains the following libraries:

-   `securetransport-plugins-authentication-services.jar`
-   `securetransport-plugins-authentication-spi.jar`

These jar libraries contain the classes you need for implementation of authentication plug-ins. Install them in the local maven repository following the instructions in the README file.

A custom authorization plug-in is deployed by dropping its JAR file into `${FILEDRIVEHOME}/plugins/authentication` directory. The latter is automatically created when you install or upgrade {{< SecureTransport/componentshortname  >}} 5.4 or higher. The jar file contains all the information required for the custom authenticator including the specific configuration metadata.

Plug-ins are discovered and registered at the Admin daemon start. After registration, an authentication plug-in is deactivated by default.

-   To enable a custom authentication plug-in for administrators, go tо the **Server configuration** page, find the `Plugins.Authentication.Admin.Registry` parameter, and remove the # symbol from the plug-in name.
-   To enable a custom authentication plug-in for end users, go tо the **Server configuration** page, find the`Plugins.Authentication.EndUser.Registry` parameter, and remove the # symbol from the plug-in name.

> **Note:**
>
> With SecureTransport 5.5, only one authentication plug-in for each role can be enabled at a time. Enabling more than one authentication plug-in will result in errors. To integrate a custom authentication plug-in for administrators and end-users refer to the Administrator Guide. .

## Authenticator

{{< SecureTransport/securetransportname  >}} currently supports the following authentication methods:

-   Basic authentication – username and password
-   Certificate authentication
-   Dual-authentication – certificate + basic authentication

The authenticator is a tool which adopts one of the following authentication methods. Authentication plug-in can have one or more authenticators which can be plugged in {{< SecureTransport/securetransportname  >}} to execute a custom authentication. It authenticates users based on input data – username, password and certificate. Upon successful authentication, the authenticator must provide user parameters that will be used by {{< SecureTransport/componentshortname  >}} – username, email, home folder, UID, GID and additional parameters.

> **Note:**
>
> Email, home folder, UID, GID are not mandatory for virtual accounts and accounts through templates but are all mandatory for external accounts The username is mandatory for all above-listed types of accounts .

If the authentication is unsuccessful, the user is not granted access to {{< SecureTransport/componentshortname  >}}. If the authenticator does not support or recognize the input data, it must forward the authentication process to another authenticator that may successfully consume it.

## Authentication Plug-in Implementation

To support any of the above authentication methods, a plug-in must implement at least one of the following interfaces:`BasicAuthenticator` or/and `CertificateAuthenticator`.

-   To support the Basic authentication method, you must provide a class that implements the `BasicAuthenticator` interface.
-   To support the certificate authentication method, you must provide a class that implements the `CertificateAuthenticator`.
-   To support dual-authentication, you must provide implementation of both interfaces.

## Implement a Basic Authentication method

Create a class that implements the *BasicAuthenticator* interface. It must have a public default constructor and implement the authenticate method, declared in the interface.


    public class BasicAuthenticatorImpl implements BasicAuthenticator {
    public BasicAuthenticatorImpl() {
            }
    @Override
    public AuthenticationResult authenticate(
        BasicAuthenticationRequest authRequest) {
            }
    }

An object of this class will be instantiated and its authenticate method will be called by {{< SecureTransport/componentshortname  >}}, every time a user tries to log in with a username and a password. The *authenticate* method’s body is the authentication logic.

*BasicAuthenticationRequest* is an interface of a bean that provides the following properties:

-   Username and password – the log-in credentials
-   Protocol – the {{< SecureTransport/securetransportname >}} daemon in which the user tries to log in – HTTP, FTP, SSH or ADMIN
-   Remote host address and host name – the IP and the host name of user’s machine
-   Edge host address – the IP of the daemon’s machine
-   The ID of the edge where the daemon is located in case of Streaming configuration
-   Additional parameters – additional attributes provided by {{< SecureTransport/securetransportname >}} (e.g. HTTP headers if the protocol is HTTP)

*AuthenticationResult* is an interface of a bean declaring the properties your return object must provide:

-   Exit code
    -   **SUCCESS** - in case of successful authentication
    -   **FAILURE** - in case of unsuccessful authentication (denying access to the user)
    -   **CONTINUE** - the implementation doesn’t support the provided data in the request or doesn’t recognize the user; the authenticated process will be delegated to other authenticators
-   Message: Human-readable information about the authentication process.
-   Result: An object of a *UserData* type in case of successful authentication

*UserData* is an interface of a bean declaring the properties you must provide – *username, UID, GID, email, homeDir* and additional attributes. When authenticating administrator users (protocol: ADMIN) only the username is required, but when authenticating end users, who are not mapped to a virtual accounts or account templates in {{< SecureTransport/componentshortname  >}} (real users) *homeDir, UID and GID* are also required.

## Implement a Certificate Authentication method

Create a class that implements the *CertificateAuthenticator* interface. It must have a public default constructor and implement the authenticate method, declared in the interface.


    public class CertificateAuthenticatorImpl implements CertificateAuthenticator {
    public CertificateAuthenticatorImpl() {
            }
    @Override
    public AuthenticationResult authenticate(
        CertificateAuthenticationRequest authRequest) {
            }
    }

An object of this class will be instantiated and its authenticate method will be called by {{< SecureTransport/componentshortname  >}} every time a user tries to log in using a certificate. The authenticate method executes the custom authentication logic.

*CertificationAuthenticationRequest* is an interface of a bean that declares the following properties:

-   Certificate – string representation of the certificate used by the user to log in; it is Base64 encoded with attached "---BEGIN CERTIFICATE---" and "---END CERTIFICATE---" tags.
-   Protocol, Remote host address and host name, Edge host address and ID, Additional parameters are described in the previous section

*AuthenticationResult* interface is described in the previous section.

## Support for a Dual-authentication method

In order to support dual-authentication, the plug-in has to provide implementations of both interfaces. In case of dual-authentication, the user will be first prompted for certificate. The plug-in certificate authenticator will be called first. If the authentication process is successful, the user will be prompted for a username and a password and the plug-in basic authenticator will be called.

If the custom Certificate authenticator returns code CONTINUE, the authentication process will be delegated to internal {{< SecureTransport/securetransportname  >}} authenticators and the Basic authenticator will not be called.

*BasicAuthenticationRequest* contains one additional field – *certificateAuthenticatedUserData*. This field will be populated while calling the plug-in Basic Authenticator in case of dual-authentication, and will contain the *UserData* with the same field values returned by the plug-in Certificate Authenticator. If the authentication is successful, the *UserData* returned by the Basic Authenticator will be used by {{< SecureTransport/componentshortname  >}}

> **Note:**
>
> Same authenticator classes will be used for Basic Authentication, Certificate authentication and Dual-authentication.

## Implement a UserRelease method

Optionally you can provide a class that will be notified by {{< SecureTransport/componentshortname  >}} that an object of a *UserData* type will not be used anymore – usually after user logout or user session expiration.

Create a class that implements the *UserReleaseListener* interface which must contain a public default constructor and a release method.


    public class UserReleaseListenerImpl implements UserRealeaseListener {
    public UserReleaseListenerImpl() {
            }
    @Override
    public void release(UserData userData) {
            }
    }

An object of this class will be instantiated an its release method will be called each time a user, that has been authenticated by the plug-in

-   has logged out
-   their session has expired or killed
-   failed second step of dual-authentication – the certificate user data will be released

The *userData*’s fields have the same values retrieved by one of the plug-ins’ authenticators.

## Implement a custom plug-in configuration

To implement a custom plug-in configuration, you must create a class that implements the interface *PluginConfiguration* and conforms to the *JavaBean convention*. The configuration itself is the fields of the class. Additional *initDefault* method must be implemented for the explicit initialization of the property values. An object of this class is instantiated on:

-   Plug-in’s first discovery and registration – initDefault method is being called, fields are being discovered and added to {{< SecureTransport/securetransportname >}} Server configuration with the default values obtained by the class getters
-   Each Authentication call – the values are read from the Server configuration and the objects fields are set using the class setters. The object is then injected in the authenticator class
-   User release call – identical to the authentication call

> **Note:**
>
> Currently the only supported field types are: String, Integer, Boolean.

An additional @*Description* annotation can be provided to every field’s getter or setter, describing what the configuration is used for. The description will appear on the {{< SecureTransport/securetransportname  >}} Server configuration admin page.

You can find a sample implementation of a Custom Authentication plug-in configuration in the `CustomAuthentication\samples` folder in the unzipped SDK folder.

An object of this class could be injected in each Authenticator class and User Listener class using the following statement:



    @Inject
    private PluginConfigurationBean mConfiguration;

The plugin-authentication-services library also provides an annotation @*Encrypted*. It indicates that a configuration value must be stored encrypted in {{< SecureTransport/securetransportname  >}} Server configuration. Put the annotation to one of the field’s accessors.

## Using the {{< SecureTransport/securetransportname  >}} Logging service

To use the logging service, provided by {{< SecureTransport/componentshortname  >}} Plug-in Authentication Services library, inject it in your Authenticator or `UserListener` class using the following statement:



    @Inject
    private LoggingService mLogger;

The *LoggingService* interface declares functionality for logging messages and exceptions with a different log level – ERROR, WARN, INFO, DEBUG, etc.

Examples:


    mLogger.info(String.format("User '%s' authenticated successfully.", username));
    mLogger.warn(String.format("Authentication of user '%s' failed - wrong password.", username));
    mLogger.warn("Problem while parsing client certificate!", e); 
    mLogger.debug("Start custom authentication process...");

The logging level can be controlled by logger in `tm-log4j.xml` and `admin-log4j.xml`.

## Using the {{< SecureTransport/securetransportname  >}} Certificate service

{{< SecureTransport/componentshortname  >}} provides a service for certificate parsing and validation against its keystore. The service is called `CertificateService `and can be injected in the plug-in’s Authenticators and `UserReleaseListener` using the following code:



    @Inject
    private CertificateService mCertificateService;

It declares the following methods:

-   `CertificateStatus getCertificateStatus(X509Certificate certificate)` – validates the certificate against the {{< SecureTransport/securetransportname >}} keystore; returns one of these enumeration values: `VALID, EXPIRED, NOT_YET_VALID, UNTRUSTED`.
-   `KeyPair getKeyPair(String certificateAlias)` – Retrieves public/private key pair from the {{< SecureTransport/securetransportname >}} keystore using certificate alias.
-   `X509Certificate parseCertificate(String certificateString)` – converts a certificate string to a `X509Certificate` object; could be used directly with the certificate, obtained from a `CertificateAuthenticationRequest`, if it is a X509 certificate.
-   `X509Certificate getCertificateBySshKey(String sshKey)` – retrieves a certificate from the {{< SecureTransport/componentshortname >}} keystore, that the provided `sshKey` corresponds to; could be used directly with the SSH key string, obtained from a `CertificateAuthenticationRequest` in case of a SSH protocol.
-   `X509Certificate getCertificateByAlias(String certificateAlias)` – retrieves certificate from the {{< SecureTransport/securetransportname >}} keystore using certificate alias.
-   `X509Certificate getCertificateById(String certificateId)` – retrieves certificate from the {{< SecureTransport/securetransportname >}} keystore using certificate’s unique identifier.
-   `X509Certificate getIssuer(X509Certificate certificate)` – retrieves certificate issuer from the {{< SecureTransport/securetransportname >}} keystore for given certificate.
-   `List<X509Certificate> getCertificateChain(X509Certificate certificate)` – retrieves certificate chain list from the {{< SecureTransport/securetransportname >}} keystore for given certificate. Can be empty, if certificate does not have a chain. The first element is the certificate itself, next element is its issuer and so on to the root certificate.
-   `Collection<X509Certificate> getCertificates(String subjectDN)` – retrieves certificate list from the {{< SecureTransport/securetransportname >}} keystore for given subject DN.
-   `Subject getCertificateSubject(X509Certificate certificate)` – extracts the domain name of the `certificate`’s subject into a bean of type `Subject`, that contains the following properties: `Common name, Country, Organization, Organization Unit, Locality, State`

This service is available in the `plugins-authentication-services` library.

## Using the SecureTransport SSLContext service

{{< SecureTransport/securetransportname  >}} provides a service for creating `javax.net.ssl.SSLContext` and `javax.net.ssl.SSLSocketFactory` objects using its internal keystore. These objects can be used for setting up secure SSL connections to other applications. This service is identical to the *Certificate service* exposed for *Custom connectors*, see [SecureTransport exposed services](../custom_connector/custom_protocol#exposed).

The service interface is called `com.axway.st.plugins.authentication.services.SSLContextService` and can be injected in the plug-in’s Authenticators and `UserReleaseListener` class, using the following code:


    @Inject
    private SSLContextService sslContextService;

The service methods are:

-   `SSLContext createSSLContext(String certId, boolean verifyPeer) throws SecurityException;`
-   `SSLContext createSSLContext(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(SSLContext sslContext, String[] protocols, String[] cipherSuites) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm, String[] protocols, String[] cipherSuites) throws SecurityException;`

These methods have the same behavior as those from the Custom connectors’ `CertificateService`.

## Using the SecureTransport

You can use expression evaluator service to evaluate and validate the expressions used in custom authenticator implementation.

To use the expression evaluator service, declare а variable with `@Inject` annotation to the interface of the expression evaluator service provided in the API:


    @Inject
    private ExpressionEvaluatorService mExpressionEvaluatorService;

This service is identical to the Expression Evaluator service exposed for Custom connectors, see [Implement a custom protocol connector](../custom_connector/custom_protocol).

## Examples of BasicAuthentication, CertificateAuthentication, and UserRelease implementations

You can find sample BasicAuthentication, CertificateAuthentication, and UserRelease implementations in the `CustomAuthentication\samples` folder in the unzipped SDK folder:

-   `BasicAuthenticatorImpl.java` contains a sample implementation of BasicAuthenticator that recognizes only users whose names start with an ‘s’. If the password matches the username, the user is authenticated successfully. Based on the protocol different user data is returned.
-   `CertificateAuthenticatorImpl.java` contains a sample implementation of implements CertificateAuthenticator that extracts the username from a X509 certificate’s subject using the provided by {{< SecureTransport/componentshortname >}}`CertificateService`. It recognizes user names starting with an ‘s’ or an ‘f’. It denies access to the ‘f’ users and returns different `UserData` objects based on the protocol.
-   `UserReleaseListenerImpl.java` contains a sample implementation of UserRealeaseListener. Objects of this class execute some release logic and log a success message in the {{< SecureTransport/securetransportname >}} Server log. They also verify that the *userData* has been created by the plug-in.

> **Note:**
>
> The delivered plug-ins are only given as examples and should not be used in real systems.

## Create a plug-in metadata file

A `META-INF/MANIFEST.MF` file must be created in the plug-in jar file. This metadata file is used by {{< SecureTransport/securetransportname  >}} to register and use the Custom Authentication implementation as a regular {{< SecureTransport/securetransportname  >}} internal Authenticator.

> **Note:**
>
> The MANIFEST.MF file is used with SPI version 1.0 only. For later versions of SPI, you will need to use the Plugin-Info.yaml file, also located in the META-INF directory.

It must contain the following properties:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Property         </th>
<th class="HeadE-Column1-Header1">Value         </th>
<th class="HeadD-Column1-Header1">          </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>Basic-Authenticator-Class</code>         </td>
         <td>The full name of the class that implements the <code>BasicAuthenticator</code> interface.         </td>
         <td>At least one of these is required.         </td>
      </tr>
      <tr>
         <td><code>Certificate-Authenticator-Class</code>         </td>
         <td>The full name of the class that implements the <code>CertificateAuthenticator</code> interface.         </td>
      </tr>
      <tr>
         <td><code>User-Release-Listener-Class</code>         </td>
         <td>The full name of the class that implements the <code>UserReleaseListener</code> interface.         </td>
         <td>Optional         </td>
      </tr>
      <tr>
         <td><code>Plugin-Configuration-Class</code>         </td>
         <td>The full name of the class that implements the <code>PluginConfiguration</code> interface.         </td>
         <td>Optional         </td>
      </tr>
      <tr>
         <td><code>Plugin-Label </code>         </td>
         <td>The label (name) of the authentication plug-in.         </td>
         <td>Required         </td>
      </tr>
      <tr>
         <td><code>Class-Path</code>         </td>
         <td>The <code>Class-Path</code> property is useful for specifying the list of the external libraries your custom connector needs to successfully run.         </td>
         <td>Optional         </td>
      </tr>
   </tbody>
</table>

If your Custom Authentication implementation depends on third party libraries, you have two implementation approaches:

-   You can use a fat jar file that stores your classes and the classes from all dependent jars into a one single jar file.
-   Add a Class-Path attribute to the `MANIFEST.MF` file, in which you must enumerate your dependent jars separated by spaces or tabs. {{< SecureTransport/securetransportname >}} will add the enumerated libraries to the Custom Authentication implementation classpath. See <https://docs.oracle.com/javase/tutorial/deployment/jar/downman.html>

> **Note:**
>
> When you are deploying your Plug-in Authentication implementation, you should only include third party dependencies, used by your implementation. You must not add APIs provided run-time by SecureTransport. This includes the SecureTransport Pluggable Authentication SPI, Plug-in Services API and JSR-330 (javax.inject) API.

### Authentication SPI versioning

Each Authentication SPI is versioned. Тhe initial SPI release is version 1.0. Every version extends the previous one and adds additional content. The SPI methods and classes added in a specific version have the **@since** annotation in their Javadoc documentation.

To declare what SPI version is used in the Authentication implementation, place the `Plugin-Info.yaml` file inside the `Meta-Inf` directory. This file contains the plug-in information, similar to the `MANIFEST.MF` file in Authentication SPI version 1.0. The description schema used in the yaml file is:


    '<SPI version>':
      <property>: <value>
      <property>: <value>
      ...................
    '<SPI version>':
      <property>: <value>
      <property>: <value>
      ...................

The convention for the indentation used is two spaces for each block.

The `Plugin-Info.yaml` file is introduced in Authentication SPI version 1.1. The old `MANIFEST.MF` file (if any) is associated with version 1.0 and is with lower priority when there is a `Plugin-Info.yaml` file.

If the version is not specified, the default one (1.0) will be used.

Only the methods and classes available in the specified version can be used.

As of publishing date of this guide, the current SPI version is **1.2**.

All previous Authentication SPI versions must be compatible with the latest {{< SecureTransport/securetransportname  >}} version, unless stated otherwise.

## Enable Logger service with authentication

In order to enable logging when using the Logger service, edit the `com.axway.st.plugins` loggers in the `tm-log4j.xml` or `admin-log4j.xml` file. For example, with pluggable authentication:


    <logger name="com.axway.st.plugins.authentication" additivity="false">      
        <level value="info" />
        <appender-ref ref="ServerLog" />
    </logger>

For fine-tuning debug logging, add the plug-in name in conjunction with the `com.axway.st.plugins` logger.

In this case, use `com.axway.st.plugins.authentication.<plugin_name>` as shown on the example:


    <logger name="com.axway.st.plugins.authentication.authentication-plugin" additivity="false">      
        <level value="debug" />
        <appender-ref ref="ServerLog" />
    </logger>
