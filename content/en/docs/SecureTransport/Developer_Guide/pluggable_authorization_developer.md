{
    "title": "Pluggable Authorization",
    "linkTitle": "Pluggable authorization",
    "weight": "110"
}This section describes the capability of {{< SecureTransport/componentshortname  >}} Server to use custom authorization plug-ins for executing custom authorization logic and provides instructions on how to implement and configure such a plug-in.

{{< SecureTransport/securetransportname  >}} version 5.4 or higher provides an Authorization SPI that you can use to create, configure, and register custom *authorizers* in a {{< SecureTransport/componentshortname  >}} Server. It is part of the SecureTransport Software Development Kit (SDK) which can be downloaded from {{< SecureTransport/supportwebsite  >}} at [support.axway.com](http://support.axway.com/).

To access the Authorization SPI, unzip the SDK and open the `CustomAuthorization/lib` folder. The `lib `folder contains the following libraries:

-   `securetransport-plugins-authorization-services.jar`
-   `securetransport-plugins-authorization-spi.jar`

These jar libraries contain the classes you need for implementation of authorization plug-ins. Install them in the local maven repository following the instructions in the README file.

A custom authorization plug-in is deployed by dropping its JAR file into `${FILEDRIVEHOME}/plugins/authorization` directory. The latter is automatically created when you install or upgrade {{< SecureTransport/componentshortname  >}} 5.4 or higher. The JAR file should contain all the information required for the custom authorization, including the specific configuration metadata. After deploying the plug-in, you must restart the Admin and TM daemons of all nodes.

Plug-ins are discovered and registered at the Admin daemon start. After registration, an authorization plug-in is deactivated by default. To enable it, go tо the **Server configuration** page, find the `Plugins.Authorization.Registry` parameter, and remove the # symbol from the plug-in name.

> **Note:**
>
> Only one authorization plug-in can be enabled at a time with SecureTransport version 5.4 or later. Enabling more than one authorization plug-in will result in errors.

{{< SecureTransport/componentshortname  >}} custom authorization currently supports the following actions:

-   Upload a file
-   Download a file
-   List content of a directory
-   Change permissions (file or directory)
-   Rename a file
-   Delete a file
-   Create a directory
-   Delete a directory

All of the above operations are defined by the `CustomAuthorizer` interface from the Authorization SPI.

Additionally, one more operation is supported - file filtering operation defined by `CustomFileFIlter` interface from the Authorization SPI.

## Create a plug-in metadata file

A `META-INF/MANIFEST.MF` file must be created in the plug-in’s JAR file. This metadata file is used by {{< SecureTransport/componentshortname  >}} to register and use the Custom Authorization implementation as a regular {{< SecureTransport/componentshortname  >}} internal Authorizer.

It can contain the following properties:

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
         <td>Authorizer-Class         </td>
         <td>The full name of the class that implements the interface.         </td>
         <td>Required         </td>
      </tr>
      <tr>
         <td>Custom-File-Filter-Class         </td>
         <td>The full name of the class that implements the interface. Requires interface implementation in order to be used.         </td>
         <td>Optional         </td>
      </tr>
      <tr>
         <td>Plugin-Configuration-Class         </td>
         <td>The full name of the class that implements the interface.         </td>
         <td>Optional         </td>
      </tr>
      <tr>
         <td>Plugin-Label         </td>
         <td>Name of the custom plug-in.         </td>
         <td>Required         </td>
      </tr>
   </tbody>
</table>

If your Custom Authorization implementation depends on third party libraries, you have two implementation approaches:

1.  You can use a fat JAR file that stores your classes and the classes from all dependent JARs into one single JAR file.
2.  Add a Class-Path attribute to the `MANIFEST.MF` file, in which you must enumerate your dependent JARs separated by spaces or tabs. {{< SecureTransport/componentshortname >}} will add the enumerated libraries to the Custom Authorization implementation class path. See <https://docs.oracle.com/javase/tutorial/deployment/jar/downman.html>

### Authorization SPI versioning

Each Authorization SPI is versioned. Тhe initial SPI release is version 1.0. Every version extends the previous one and adds additional content. The SPI methods and classes added in a specific version have the **@since** annotation in their Javadoc documentation.

To declare what SPI version is used in the Authorization implementation, place the `Plugin-Info.yaml` file inside the `Meta-Inf` directory. This file contains the plug-in information, similar to the `MANIFEST.MF` file in Authorization SPI version 1.0. The description schema used in the yaml file is:


    '<SPI version>':
      <property>: <value>
      <property>: <value>
      ...................
    '<SPI version>':
      <property>: <value>
      <property>: <value>
      ...................

The convention for the indentation used is two spaces for each block.

The `Plugin-Info.yaml` file is introduced in Authorization SPI version 1.1. The old `MANIFEST.MF` file (if any) is associated with version 1.0 and is with lower priority when there is a `Plugin-Info.yaml` file.

If the version is not specified, the default one (1.0) will be used.

Only the methods and classes available in the specified version can be used.

The current SPI version, introduced along with {{< SecureTransport/securetransportname  >}} {{< SecureTransport/componentversion  >}}, is **1.3**.

All previous Authorization SPI versions must be compatible with the latest {{< SecureTransport/securetransportname  >}} version, unless stated otherwise.

## Implement a CustomAuthorizer

To support any authorization operation, a plug-in must implement `CustomAuthorizer` interface. Create a class that implements the `CustomAuthorizer` interface. It must have a public default constructor and implement the declared methods which are the authorization operations.

All methods accept a `DataEnvironment` as a parameter and must return `AuthorizationResult`.

`DataEnvironment` is an interface that defines the current {{< SecureTransport/componentshortname  >}} data for a single authorization operation. It consists of:

-   `AccountDataEnv` – contains information about the currently logged account

<!-- -->

-   `SessionDataEnv`– contains information about the current session environment

<!-- -->

-   `FlowDataEnv`– contains information about the flow data from the current target

<!-- -->

-   `HttpDataEnv`– contains information about all HTTP headers in case the current authorization action is done via HTTP

<!-- -->

-   `TransferDataEnv`– contains information about the current transfer
-   `AuthenticationDataEnv`– contains authentication information for the currently logged account. The account in {{< SecureTransport/componentshortname >}} can be logged using one of the following authentication paths: LDAP, authentication plug-in, SSO, or using the {{< SecureTransport/componentshortname >}} build-in authentication mechanisms. In case an account is logged using an external authentication agent, or an external user repository (LDAP), the respective information will be available in this authentication data environment. In case an account is logged via the {{< SecureTransport/componentshortname >}} internal authentication agents, the authentication data will be part of `AccountDataEnv`.

`AuthorizationResult` is an interface that defines the result an authorization operation must return. It provides the following properties:

-   Exit code
    -   `AUTHORIZATION_CONTINUE` – in case of successful authorization or in case of default behavior
    -   `AUTHORIZATION_DENY` – in case of unsuccessful authorization
-   Message: Human - readable information about the executed authorization operation

> **Note:**
>
> Make sure that you will not return null as an AuthorizationResult. In that case the authorization action will be denied.

Put your authorization logic inside and return appropriate result for the methods you want to implement.

If you don’t need authorization of particular operations, you can simply implement them to return a value of `AuthorizationResult.ExitCode.AUTHORIZATION_CONTINUE`.

Your custom authorizer implementation will be able to use two {{< SecureTransport/componentshortname  >}} services – `LoggingService` and `StfsService`. Both of them can be used by injecting them as class members using the standard java injection annotation (see the example below). The logging service provides logging capabilities specified by your administrator. The STFS service provides a way to read the basic filesystem attributes that are stored for a files transferred by {{< SecureTransport/componentshortname  >}}.

For more information about the possible {{< SecureTransport/componentshortname  >}}-specific file attributes, please refer to `StSpecificFileAttributes` interface in `securetransport-program-api`.

### Example of a CustomAuthorizer implementation

You can find a sample implementation of a `CustomAuthorizer` interface in the `CustomAuthorization\samples` folder in the unzipped SDK folder.

## Implement a CustomFileFilter

In order a plug-in to support file filter operation it must implement `CustomFileFilter` interface. Create a class that implements the `CustomFileFilter` interface. It must have a public default constructor and implement the declared method.

The method `doFilter` that must be implemented accepts 2 parameters – sorted set of Path objects and a `DataEnvironment` object. Its return type is set of Path objects which will be the filtered result.

Your file filter implementation will be able to use two {{< SecureTransport/componentshortname  >}} services – `LoggingService` and `StfsService`. Both of them can be used by injecting them as class members using the standard java injection annotation (see the example below). The logging service provides logging capabilities specified by your administrator. The STFS service provides a way to read the basic filesystem metadata attributes that are stored for a files transferred by {{< SecureTransport/componentshortname  >}}.

All custom file filter implementations are restricted to return no more than the target files (or part of them) which are going to be filtered. Therefore, only file deletions from the set are supported. Any experiment in adding any files to the returned set will result in a non - filtered output (like there’s no file filter implementation) in {{< SecureTransport/componentshortname  >}} and an error.

> **Note:**
>
> If, for some reasons, the doFilter return null, no filter will be applied, and the original files will be listed.

> **Note:**
>
> Do not try to add files in the targetFiles. This will cause exception and the File Filter process will fail and no custom file filtering will be applied.

### Example of a CustomFileFilter implementation

You can find a sample implementation of a `CustomFileFilter` interface in the `CustomAuthorization\samples` folder in the unzipped SDK folder.

## Performance considerations

Below you can find information on how often the authorization plug-in is called depending on some of the supported protocols:

**Over FTPS**:

\- For an upload operation the plug-in is called once to authorize the upload event.

\- For a download operation the plug-in is called once to authorize the download event.

**Over SFTP**:

\- For an upload operation the plug-in is called four times - once to authorize the upload operation and three times for the list operation.

\- For a download operation the plug-in is called once to authorize the download event.

**Over HTTPS**:

\- For an upload operation the plug-in is called once to authorize the upload event.

\- For a download operation the plug-in is called once to authorize the download event.

> **Note:**
>
> These results may vary depending on the client being used.

## Using the {{< SecureTransport/securetransportname  >}} Certificate service

{{< SecureTransport/componentshortname  >}} provides a service for certificate parsing and validation against its keystore. The service is called `CertificateService `and can be injected in the plug-in’s `CustomAuthorizer` and `CustomFileFilter` using the following code:



    @Inject
    private CertificateService mCertificateService;

It declares the following methods:

-   `CertificateStatus getCertificateStatus(X509Certificate certificate)` – validates the certificate against the {{< SecureTransport/securetransportname >}} keystore; returns one of these enumeration values: `VALID, EXPIRED, NOT_YET_VALID, UNTRUSTED`.
-   `KeyPair getKeyPair(String certificateAlias)` – Retrieves public/private key pair from the {{< SecureTransport/securetransportname >}} keystore using certificate alias.
-   `X509Certificate getCertificateByAlias(String certificateAlias)` – retrieves certificate from the {{< SecureTransport/securetransportname >}} keystore using certificate alias.
-   `X509Certificate getCertificateById(String certificateId)` – retrieves certificate from the {{< SecureTransport/securetransportname >}} keystore using certificate's unique identifier.
-   `X509Certificate getIssuer(X509Certificate certificate)` – retrieves certificate issuer from the {{< SecureTransport/securetransportname >}} keystore for given certificate.
-   `List<X509Certificate> getCertificateChain(X509Certificate certificate)` – retrieves certificate chain list from the {{< SecureTransport/securetransportname >}} keystore for given certificate. Can be empty, if certificate does not have a chain. The first element is the certificate itself, next element is its issuer and so on to the root certificate.
-   `Collection<X509Certificate> getCertificates(String subjectDN)` – retrieves certificate list from the {{< SecureTransport/securetransportname >}} keystore for given subject DN.
-   `Subject getCertificateSubject(X509Certificate certificate)` – extracts the domain name of the `certificate`’s subject into a bean of type `Subject`, that contains the following properties: `Common name, Country, Organization, Organization Unit, Locality, State`

## Using the {{< SecureTransport/securetransportname  >}} SSLContext service

{{< SecureTransport/securetransportname  >}} provides a service for creating `javax.net.ssl.SSLContext` and `javax.net.ssl.SSLSocketFactory` objects using its internal keystore. These objects can be used for setting up secure SSL connections to other applications. This service is identical to the *Certificate service* exposed for *Custom connectors*, see <a href="../custom_connector/custom_protocol#exposed" class="MCXref xref">SecureTransport exposed services</a>.

The service interface is called `com.axway.st.plugins.authorization.services.SslContextService` and can be injected in the plug-in’s `CustomAuthorizer` and `CustomFileFilter` class, using the following code:


    @Inject
    private SsLContextService sslContextService;

The service methods are:

-   `SSLContext createSSLContext(String certId, boolean verifyPeer) throws SecurityException;`
-   `SSLContext createSSLContext(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(SSLContext sslContext, String[] protocols, String[] cipherSuites) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm, String[] protocols, String[] cipherSuites) throws SecurityException;`

These methods have the same behavior as those from the Custom connectors’ `CertificateService`.

## Using the SecureTransport

You can use expression evaluator service to evaluate and validate the expressions used in custom authorization implementation.

To use the expression evaluator service, declare а variable with `@Inject` annotation to the interface of the expression evaluator service provided in the API:


    @Inject
    private ExpressionEvaluatorService mExpressionEvaluatorService;

This service is identical to the Expression Evaluator service exposed for Custom connectors, see <a href="../custom_connector/custom_protocol" class="MCXref xref">Implement a custom protocol connector</a>.

## Enable Logger service with authorization

In order to enable logging when using the Logger service, edit the `com.axway.st.plugins` loggers in the `tm-log4j.xml` file. For example, with pluggable authorization:


    <logger name="com.axway.st.plugins.authorization" additivity="false">
        <level value="info" />
        <appender-ref ref="ServerLog" /> 
    </logger>

For fine-tuning debug logging, add the plug-in name in conjunction with the `com.axway.st.plugins` logger.

In this case, use `com.axway.st.plugins.authorization.<plugin_name>` as shown on the example:


    <logger name="com.axway.st.plugins.authorization.authorization-plugin" additivity="false">
        <level value="debug" />
        <appender-ref ref="ServerLog" />
    </logger>
