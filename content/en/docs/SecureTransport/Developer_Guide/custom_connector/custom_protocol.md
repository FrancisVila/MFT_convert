{
    "title": "Implement a custom protocol connector",
    "linkTitle": "Implement a custom protocol connector",
    "weight": "100"
}The {{< SecureTransport/componentshortname  >}} Pluggable Transfer Site SPI provides the interface `com.axway.st.plugins.site.Connection` which should be implemented in order to transfer files to and from the partner.  
The Connection interface version 1.0 declares the following methods:

-   `void getFile(DestinationFile file) throws IOException;`
-   `void putFile(SourceFile file) throws IOException;`
-   `void finalizeExecution() throws IOException;`
-   `List<FileItem> list() throws IOException;`

The Connection interface version 1.1 adds the following methods:


    List<String> getProtocolCommands();
    String getAdditionalInfo(); 
    FlowAttributesData getFlowAttributesData();

The Connection interface is extended by `com.axway.st.plugins.site.CustomSite` abstract class which is also part of Pluggable Transfer Site SPI. Its main purpose is to hold a UIBean instance containing connection parameters as key-value pairs saved into the database as custom transfer site properties. The parameters are loaded from the database by {{< SecureTransport/componentshortname  >}} and populated in the UIBean instance inside the specific `CustomSite` implementation when starting server-initiated transfers.

The following steps should be followed to create the custom protocol connector:

1.  Define a class that extends the `com.axway.st.plugins.site.CustomSite`:  


        import com.axway.st.plugins.site.CustomSite
        public class FTPSite extends CustomSite {
        }

2.  Define the UIBean instance that will hold the connector parameters:  


        /** The UIBean implementation. */
        private FtpBean mFtpBean = new FtpBean();

3.  Define the default constructor for `FTPSite` class which should set the instantiated `FtpBean` as the UIBean instance in the `CustomSite` parent class.  
    When {{< SecureTransport/componentshortname >}} starts the transfer, it will populate the connection properties into UIBean instance defined in the `CustomSite` class:  


        public FTPSite() {
              setUIBean(mFtpBean);
        }

<span id="SPI1.5"></span>In addition there is a way to report the download information. This information consists of two attributes: *remote download folder* and *remote download pattern* via the following annotations, which are part of site SPI: `RemoteDownloadFolder `and `RemoteDownloadPattern`.

-   `RemoteDownloadFolder `- During the execution of the `list()` method, this attribute can be used to distinguish the remote download folder, if any.
-   `RemoteDownloadPattern `- During the execution of the `list()` method, this attribute can be used to distinguish the remote download pattern, if any.

> **Note:**
>
> The annotated field must be of type String. Also, this annotation takes effect only when used in implementation instance of CustomSite.

The reported information will be used for correct Sentinel reporting during pull actions.

## Site SPI versioning

Each Site SPI is versioned. The initial SPI release is version 1.0. Every version extends the previous one and adds additional content. The SPI methods and classes added in a specific version have the **@since** annotation in their Javadoc documentation. To declare what SPI version is used in Site implementation, place the `Plugin-Info.yaml` file inside the `Meta-Inf` directory. This file contains the plug-in information, similar to the `MANIFEST.MF` file in Site SPI version 1.0. The `Plugin-Info.yaml` file is introduced in Site SPI version 1.1. The old `MANIFEST.MF` file (if any) is with higher priority.  
If the version is not specified, the default one (1.0) will be used.

You can use only the methods and classes available in the specified version.

The current SPI version is **1.8**.

### Connection interface implementation version 1.0

{{< SecureTransport/componentshortname  >}} calls `putFile` (`SourceFile` file) method from the Connection interface when executing server-initiated push. The `SourceFile` instance will contain the `InputStream` to read the local file content that will be sent, the remote file name to write the content to, and the size of the local file (number of bytes the `InputStream` could read). Generally, the implementation of `putFile()` method should connect to the remote partner and write the content from the local file input stream to the remote file. The parameters for the connection can be retrieved from the already defined UIBean instance.

When calling `getInputStream(RemotePartner descriptor)` from the `SourceFile` instance, you must pass a `com.axway.st.plugins.site.RemotePartner` instance as argument. This instance should hold the connection parameters which will be reported by {{< SecureTransport/componentshortname  >}} File Tracking. Currently, these parameters are the remote host, the remote folder to which the file will be pushed, the parameter that shows whether the remote connection is secure and the new remote file name which should be reported as Post Transmission Action if such is configured in transfer site. In SPI v1.3 two additional parameters were introduced – one for identifying the network connection port and one for identifying the remote impersonated entity.

Let's assume you have an `FTPConnector` interface and a simple FTP client implementation based on your interface which has the following methods:

-   `connect(FtpBean ftpBean)`
-   `upload(InputStream inputStream, String remoteDir, String remoteFile)`

The `connect()` method retrieves connection parameters from the `FtpBean` instance and uses them to configure the FTP client and then connects to the remote partner.The `upload()` method sends the content from the `inputStream` to the remote partner and saves it to `remoteFile` in the `remoteDir`.

> **Note:**
>
> The remoteDir is actually the remote upload folder to which the file will be sent. The Send To Partner step in the Advanced Routing cannot overwrite the upload folder of a Custom Transfer Site.

The Send to Partner step can override the upload folder configured in the transfer site only if the transfer site explicitly allows upload folder overriding which is configurable in all built-in transfer sites. For the custom transfer sites, the overriding of the upload folder by the Send to Partner step **is not** allowed and **is not** configurable. If the Send to Partner step is configured to override the upload folder of custom transfer site, the overriding is ignored.

So, in the `putFile` method implementation inside the `FTPSite` class, you should connect to the remote partner and then upload the file.

> **Note:**
>
> Do not disconnect from the remote partner.

First, you should use the `connect()` method to connect to the FTP server:


    /** The FTP client implementation. Allows connecting/disconnecting/transferring files. */
    private AbstractFTPConnector mFtpConnection;
    /** Connects to a FTP server.
     *
     * @throws IOException on error
     */
    public String connect() throws IOException {
        mFtpConnection = new FTPConnectorBuilder().build(mFtpBean);
        mFtpConnection.setCertificateService(mCertificateService);
        mFtpConnection.setProxyService(mProxyService);
        return mFtpConnection.connect();
    }

Then use it in the `putFile()` method to upload the file:


    @Override
    public void putFile(SourceFile file) throws IOException {
        String resolvedHost = "127.0.0.1";
        if (mFtpConnection == null) {
            resolvedHost = connect();
        }
        RemotePartner descriptor = new RemotePartner(resolvedHost, 
        mFtpBean.getPartnerUploadFolder(),
                mFtpBean.isFtps(), getSentFileAs());
        mFtpConnection.upload(file.getInputStream(descriptor), 
        descriptor.getRemoteHost(), file.getName());
    }
    /**
     * Gets the "Send File As" value or
     * return empty string if "Send File As" option is not enabled.
     *
     * @return "Send File As" value or, if no value is found it returns 
       empty string
     */
    private String getSentFileAs() {
        String resultFileAs = "";
        if (mFtpBean.isSendFileAsEnabled()) {
            resultFileAs = mFtpBean.getSendFileAs();
            }
        return resultFileAs;
    }

#### List() method

The `list()` method implementation from the Connection interface should return the list of files that are going to be downloaded from the remote partner". These files should be described using the `com.axway.st.plugins.site.FileItem` class. This class holds the remote file name that should be downloaded and the name which will be used to save the downloaded files.

When {{< SecureTransport/componentshortname  >}} starts the server-initiated pull transfer, the `list()` method from the Connection interface is always called before the file pull. The parameters for configuring file pull are `remoteDir` and `remotePattern` where the pattern could be a filename or expression. After the `list()` method returns the list of files that should be downloaded, described using the `FileItem` class, {{< SecureTransport/componentshortname  >}} calls the `getFile()` method from Connection interface for every item in the list. In the `list()` method, you can implement a logic for listing files in a predefined remote directory only, or recursively listing all files in a specific directory. It is important to remember that the file names (and paths in case of recursive listing), returned by the `list()` method, should be relative to the predefined remote directory.

In the following example, the `FtpBean` and `FtpConnector` will be used to implement the `list()` method:

Let's assume you have an `FTPConnector` interface and a simple FTP client implementation based on your interface which has the following methods:

-   `connect(FtpBean ftpBean)`
-   `listFiles(String remoteDir, String remotePattern)`

The `connect()` method will retrieve connection parameters from the `FtpBean` instance and use them to configure the FTP client and then connect to the remote partner.

The `listFiles()` method returns the list of file names matching the `remotePattern` inside the `remoteDir` folder.

In the `list()` method implementation you must first connect to the remote partner, then execute the `listFiles()` method to get the list of file names that match the specific pattern and then construct the result list of the `FileItem` instances.

First, you should use the `connect()` method to connect to the FTP server:


    /** The FTP client implementation. Allows connecting/disconnecting/transferring files. */
    private AbstractFTPConnector mFtpConnection;
    /** Connects to a FTP server.
     *
     * @throws IOException on error
     */
    public String connect() throws IOException {
        mFtpConnection = new FTPConnectorBuilder().build(mFtpBean);
        mFtpConnection.setCertificateService(mCertificateService);
        mFtpConnection.setProxyService(mProxyService);
        return mFtpConnection.connect();
    }

Then use it to list the files from the remote partner that match the specified criteria (remote folder and file name pattern) defined in the `FtpBean` instance.

> **Note:**
>
> Do not disconnect from the external server.


    @Override
    public List<FileItem> list() throws IOException {
        if (mFtpConnection == null) {
            connect();
        }
        List<String> names = mFtpConnection.listFiles(mFtpBean.getPartnerDownloadFolder(),
                mFtpBean.getPartnerDownloadPattern());
        List<FileItem> result = new ArrayList<FileItem>();
        if (names != null && names.size() > 0) {
            for (String name : names) {
                result.add(new FileItem(name));
            }
        }
        return result;
    }

Note that in the example above, the file will be saved locally with the same name as the name of the remote file when pulled.

If you want to save the file with a different name, you can use the other constructor from the `FileItem` class when creating the `FileItem` instance the files:

-   `new FileItem(String fileName, String receiveFileAs);`

#### getFile(DestinationFile file) method

The next method that should be implemented is `getFile(DestinationFile file)`. {{< SecureTransport/componentshortname  >}} calls the `getFile(DestinationFile file)` method from the Connection interface when executing a server-initiated pull. The `DestinationFile` instance will contain the `OutputStream` to write the remote file content to and the remote file name which will be pulled.  
Generally, the `getFile()` method should write the content of the remote file to the output stream held by the `DestinationFile` instance. When calling the `getOutputStream(RemotePartner descriptor);` from `DestinationFile` instance, you must pass the `com.axway.st.plugins.site.RemotePartner` instance as an argument. This instance should hold the connection parameters which will be reported by SecureTransport File Tracking. Currently, these parameters are the remote host, the remote folder from which the file will be downloaded, and the parameter that shows whether the remote connection is secure.

Let's assume you have an `FTPConnector` interface and a simple FTP client implementation based on your interface which has the following methods:

-   `connect(FtpBean ftpBean)`
-   `download(OutputStream outputStream, String remoteDir, String remoteFile)`

The `connect()` method retrieves the connection parameters from the `FtpBean` instance and uses them to configure the FTP client and then connects to the remote partner.

The `download()` method retrieves the content from the `remoteFile` which is in the `remoteDir` and writes its content to the `outputStream` instance.

So, in the `getFile` method implementation inside the `FTPSite` class, you should first connect to the remote partner and then download the file.

First, you should use the `connect()` method to connect to the FTP server:


    /** The FTP client implementation. Allows connecting/disconnecting/transferring files. */
    private AbstractFTPConnector mFtpConnection;
    /** Connects to a FTP server.
     *
     * @throws IOException on error
     */
    public String connect() throws IOException {
        mFtpConnection = new FTPConnectorBuilder().build(mFtpBean);
        mFtpConnection.setCertificateService(mCertificateService);
        mFtpConnection.setProxyService(mProxyService);
        return mFtpConnection.connect();
    }

Then use it in the `getFile()` method to download the file.

> **Note:**
>
> Do not disconnect from the external server.


    @Override
    public void getFile(DestinationFile file) throws IOException {
        String resolvedHost = "127.0.0.1";
        if (mFtpConnection == null) {
            resolvedHost = connect();
        }
        mFtpConnection
            .download(
                file.getOutputStream(
                        new RemotePartner(resolvedHost, 
               mFtpBean.getPartnerDownloadFolder(), mFtpBean.isFtps())),
                mFtpBean.getPartnerDownloadFolder(), file.getName());
    }

#### public void finalizeExecution() throws IOException; method

The last method from Connection interface which you should implement is:

-   `public void finalizeExecution() throws IOException;`

This method is called by {{< SecureTransport/componentshortname  >}} when finalizing the server-initiated transfer after executing the `list` method, `getFile` method, and `putFile` method regardless if they are completed successfully or not.

In this method you should release any occupied resource, for instance disconnecting the specific client from the remote partner.

> **Note:**
>
> If the external server requires an explicit logout, it needs to be implemented either here or in the disconnect implementation.


    @Override
    public void finalizeExecution() throws IOException {
        if (mFtpConnection != null) {
            mFtpConnection.disconnect();
            mFtpConnection = null;
        }
    }

### Connection interface implementation version 1.1

Connection interface version 1.1 includes all functionality, introduced in version 1.0 and adds the following methods:

#### public List&lt;String> getProtocolCommands(); method

This method is called by SecureTransport after the Server-initiated transfer (SIT) ends. The purpose of this method is to return the protocol commands logged (or captured) by the client during the transfer process. This method must be used along with `CommandLoggingService`, and more correctly method `getProtocolCommands()`.

{{< SecureTransport/componentshortname  >}} logs the protocol commands as normal protocol commands for the current transfer.

> **Note:**
>
> The restrictions for custom logged protocol commands are the same as the ones logged by SecureTransport.


    @Override
    public List<String> getProtocolCommands() {
        return mCommandLoggingService.getProtocolCommands();
    }

#### public String getAdditionalInfo(); method

You can use this method to log any additional information about the transfer. This method is called on Server-initiated transfers end. The logged information is shown on the *File Tracking* page under the **Additional Information** section. This method must be used along with `AdditionalInfoLoggingService`, and more correctly method `getAdditionalInfo()`.

> **Note:**
>
> The total size of the message that can be logged should not exceed 4096 characters. If bigger, the exceeding part will be truncated.


    @Override
    public String getAdditionalInfo() {
        return mAdditionalInfoLogService.getAdditionalInfo();
    }

#### public FlowAttributesData getFlowAttributesData(); method

Gets the flow attributes for the current transferred file. This serves two purposes. First it is populated with existing flow attributes for the file being transferred by the server. Called second time when transfer is finished to persist the attributes stored in it.

For more information about flow attributes, see the {{< SecureTransport/componentshortname  >}} Administrator's guide, *Mail template commands and variables* section &gt; *Flow attributes* subsection.

<span id="Connection_Interface_1.3"></span>

### Connection interface implementation version 1.3

Connection interface version 1.3 includes all functionality, introduced in version 1.1. It also provides:

-   extended `RemotePartner `class with two additional properties and a builder utility
-   ability to notify {{< SecureTransport/securetransportname >}} for executed post-transmission actions (PTAs) to report them in {{< SecureTransport/securetransportname >}} File Tracking.

#### integer RemotePartner#remotePort; field

This object variable is meant to contain the partner’s port, used for the remote connection.

#### string RemotePartner#remoteContainer; field

This object variable is meant to identify the remote impersonated entity. Could be a user, business unit, email address, group, resource, etc.

#### static class RemotePartner.Builder; utility

This utility is meant to construct RemotePartner objects using any set of RemotePartner properties. Typical usage:


    RemotePartner remotePartner = new RemotePartner.Builder()
         .host("192.168.10.2")
         .port(21)
         .container("user2")
         .folder("/download")
         .secureConnection(true)
         .build();

#### void CustomSite#notifyPTAExecuted(PTAInfo); utility method

This method should be called by CustomSite implementations after a PTA is executed to report it in {{< SecureTransport/componentshortname  >}} File Tracking. Post-transmission actions are usually executed after an actual transfer, so this method could be effectively called after calling `SourceFile#getInputStream(…)` or `DestinationFile#getOutputStream(…)` in case of upload or download respectfully.

#### class PTAInfo; bean

Objects of type `PTAInfo `describe an executed post-transmission actions. The object fields are:

-   `String actionType` – the type of the executed operation; required; typical actions are: MOVE, DELETE, SHARE, etc.; types, longer than 20 chars, are being trimmed by {{< SecureTransport/securetransportname >}}
-   `PTACompletionStatus completionStatus – SUCCESS/FAILURE;` required; indicates if the execution of the PTA succeeded or failed
-   `String result` – the product of the executed action; typically, a file-name
-   `String comment` – human-readable information about the executed action; comments, longer than 1024 bytes are being trimmed by {{< SecureTransport/securetransportname >}}

Typical usage:


    notifyPTAExecuted(
       new PTAInfo(
           "MOVE",
           PTACompletionStatus.SUCCESS,
           "/download/success/file.txt",
           "File 'file.txt' has been successfully moved to '/download/success/'."));

<span id="Connection_Interface_1.4"></span>

### Connection interface implementation version 1.4

Connection interface version 1.4 includes all the functionality, introduced in version 1.3. It also provides:

-   Extended proxy functionality, where {{< SecureTransport/componentshortname >}} can deny or blacklist proxies

#### ProxyInfo getProxyInfo(); method

This method is meant to hold and return the proxy instance (if any) used when performing Server-initiated transfers. {{< SecureTransport/componentshortname  >}} needs it to be able to determine which proxy to deny or blacklist if transfers via this proxy are failing often in a predefined period of time. If a proxy is not used, this method can simply return null. The `ProxyInfo` object can be easily obtained using the [Proxy Service](#Proxy).

### 

Connection interface version includes all functionality, introduced in version 1.4. It also provides:

-   Two new annotations `@RemoteDownloadPattern` and `@RemoteDownloadFolder` to notify {{< SecureTransport/securetransportedgename >}} that these are the download folder and pattern to be used in {{< SecureTransport/companyname >}} Sentinel.

### 

Connection interface version includes all functionality, introduced in version 1.5. It also provides:

-   Two new services - `TransferAttributesData` and `AccountAttributesData` that can be used for reading transfer and account-related attributes for the currently transferred file.

<span id="Connecti"></span>

### 

Connection interface version includes all functionality, introduced in version 1.6. It also provides:

-   `SSLContextService`, which constructs `SSLContext`, `SSLSocketFactory` objects, to be used when connecting over secure connection to a remote partner.

<span id="Connecti2"></span>

### Connection interface implementation version 1.8

Connection interface version includes all functionality, introduced in version 1.7. It also provides:

-   `StorageService`, which allows data storing and retrievement during the execution of Transfer Site methods.

## Exception handling

{{< SecureTransport/componentshortname  >}} will only retry the transfer by default if some of the Connection interface methods throw an `IOException` instance if there are retry attempts remaining. The {{< SecureTransport/componentshortname  >}} Pluggable Transfer Site SPI provides a special exception named `TransferFailedException`, which is of type `java.io.IOException`. This exception indicates a transfer failure; if the error is permanent (for example, an authentication failure) and is not expect to be resolved on retry, an `isPermanentFailure` flag should be raised. Otherwise, it should be left set to false, (for example, on connection timeout or any other transient error), allowing the transfer to succeed on the next retry. Generally, any exception caused by configuration or miss configuration is an exception that should not be retried. If an error occurs while implementing your Custom Connector, a `TransferFailedException` instance should be thrown with the flag set to indicate if the exception is permanent or temporary. There are two available constructors for instantiating `com.axway.st.plugins.site.TransferFailedException`:

-   `public TransferFailedException(String message, Throwable cause);`
-   `public TransferFailedException(String message, Throwable cause,  boolean isPermanentFailure);`

The first one will set the `isPermanetFailure` flag to false and will force the SecureTransport to retry the transfer if retry attempts are available. The number of retries and the interval between retries for a transient failure of transfer can be configured by a {{< SecureTransport/componentshortname  >}} administrator. For more information about configuring retry parameters for server-initiated transfers, refer to the *{{< SecureTransport/componentshortname  >}} Administrator's Guide*.

> **Note:**
>
> Only adminstrator configurable retries should be attempted. Internal retries should not be attempted. Internal retries are hidden from SecureTransport and no file tracking information will be generated.

<span id="exposed"></span>

## {{< SecureTransport/componentshortname  >}} exposed services

The {{< SecureTransport/componentshortname  >}} Pluggable Transfer Site SPI also exposes services from {{< SecureTransport/componentshortname  >}} Server that can be consumed by the Custom Connector implementation. The implementation can `@Inject` the service interface in its extension of `CustomSite` class and then consume the service via provided interface.

### Certificate Service

To use the certificate service, declare a variable with `@Inject` annotation (`javax.inject.Inject`) to the interface of the certificate service provided in the API:


    @Inject
    private CertificateService certificateService;

The certificate service provides capabilities for:

-   `CertificateStatus getCertificateStatus(X509Certificate certificate);`
-   `Subject getCertificateSubject(X509Certificate certificate) throws CertificateException;`
-   `KeyPair getKeyPairByAlias(String certificateAlias) throws CertificateException;`
-   `KeyPair getKeyPairById(String certId) throws SecurityException;`
-   `X509Certificate getCertificateByAlias(String certificateAlias) throws CertificateException;`
-   `X509Certificate getCertificateById(String certificateId) throws SecurityException;`
-   `X509Certificate getIssuer(X509Certificate certificate) throws CertificateException;`
-   `List<X509Certificate> getCertificateChain(X509Certificate certificate) throws CertificateException;`
-   `Collection<X509Certificate> getCertificates(String subjectDN) throws CertificateException;`

<span id="Proxy"></span>

### Proxy Service

To use the proxy service, declare a variable with `@Inject` annotation to the interface of the proxy service provided in the API:


    @Inject
    private ProxyService proxyService;

The proxy service provides capabilities for:

-   `ProxyInfo getProxy(ProxyType proxyProtocol, String dmzName) throws NoSuchZoneException;`
-   `boolean isRemoteDnsResolutionEnabled(String zoneName) throws NoSuchZoneException;`
-   `String getPublicURLPrefix(String zoneName) throws NoSuchZoneException`

The `getProxy` method of the proxy service will return a "`null`" object, if there is no proxy with the specified type defined in the selected DMZ zone. The specific custom connector implementation decides whether to use this proxy for the transfer or not.The default {{< SecureTransport/componentshortname  >}} zone is **Private**.

<span id="SSL"></span>

### 

To use the SSL context service, declare a variable with `@Inject` annotation (`javax.inject.Inject`) to the interface of the certificate service provided in the API:



    @Inject
    private SSLContextService sslContextService;

The SSL context service provides capabilities for:

-   `SSLContext createSSLContext(String certId, boolean verifyPeer) throws SecurityException;`
-   `SSLContext createSSLContext(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(SSLContext sslContext, String[] protocols, String[] cipherSuites);`
-   `SSLSocketFactory configSSLContextFactory(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm, String[] protocols, String[] cipherSuites) throws SecurityException;`

### Logging Service

You can use this service to log messages on different levels in the {{< SecureTransport/componentshortname  >}} Server Log.

The log levels are DEBUG, INFO, WARN, ERROR and FATAL.

Every level has two methods: one with a logged message only and another with a logged message with an exception.

For more information, see the documentation for the associated methods.

The logged message appears in the {{< SecureTransport/componentshortname  >}} Server Log. It starts with the following pattern `[TRANSFER_SITE]:[plugin_name OR protocol_name]`.

For more information about the third-party libraries logging, see [Third-party libraries logging]().

<span id="Addition"></span>

### Additional Info Logging Service

To use the additional information logging service, declare a variable with an `@Inject` annotation to the interface of the additional information logging service provided in the API:


    @Inject
    private AdditionalInfoLoggingService mAdditionalInfoLogService;

The additional information logging service capabilities are:

-   `void append(String info)` - adds/appends an info message. Every appended message is delimited with the particular system line separator.
-   `String getAdditionalInfo();` - gets the additional information.

You can add additional information by calling the `append `method with the information you want to be logged. You can call the `append `method multiple times. The different messages will be separated by a new line.

<span id="Command"></span>

### Command Logging Service

The service provides protocol commands logging capabilities in {{< SecureTransport/componentshortname  >}}.To use the command logging service, declare а variable with `@Inject` annotation to the interface of the command logging service provided in the API:



        @Inject
        private CommandLoggingService  mCommandLoggingService;

The basic capabilities of this service are:

-   `void append(String command);` - appends the command to the buffer of commands.
-   `List<String>``getProtocolCommands();` - gets the protocol commands.

You can use the `append `method to log a single protocol command. You can call the `append `method multiple times. The logged protocol commands will appear in {{< SecureTransport/componentshortname  >}} Transfer Log as an ordinary protocol command.

### Flow Attributes Data service

#### FlowAttributesData

This serves a container for flow attributes. This container can be used for reading/writing flow attributes for the current transferred file. To use the flow attributes container, declare a variable with `@Inject` annotation to the interface of the flow attributes data service provided in the API:



    @Inject
        public FlowAttributesData  mFlowAttributesData;

The `FlowAttributesData` object has the following capabilities:

-   `Map<String, Object> getFlowAttributes();` - gets the flow attributes populated by the server.Return the key-value pairs of flow attributes for the current transfered file.
-   **void** `setFlowAttributes(Map<String, Object> flowAttributes);` - sets the flow attributes to be persisted by the server.

Sets the flow attributes for the current transferred file. If the attribute already exists, it will be overwritten.

### Expression Evaluator Service

#### ExpressionEvaluatorService

You can use expression evaluator service to evaluate and validate the expressions used in site connection implementation. To use the expression evaluator service, declare а variable with `@Inject` annotation to the interface of the expression evaluator service provided in the API:



    @Inject
        
    private ExpressionEvaluatorService mExpressionEvaluatorService;

The expression evaluator service has the following capabilities:

-   **void** `loadExpressionService(Map<String, Object> context);` - loads the expression service with an appropriate context.
-   `String evaluateString(String expression);` - evaluates the Expression and returns the string result.  
    This is a convenience method that will simply evaluate the expression with a return class of String.class. This is by far the most common usage of the `evaluateString` method.
-   **public** `<T> T evaluateObject(String expression, Class<T> expectedType) throws InvalidExpressionException;`: evaluates expression to specific type of object. If the expression is not valid, an `InvalidExpressionException` will be thrown.
-   **void** `validateExpression(String expression)`**throws** `InvalidExpressionException;`: validate the given expression. If the expression is not valid an `InvalidExpressionException` will be thrown.
-   `public String evaluatePathString(String expression)`**throws** `InvalidExpressionException;`: evaluates the expression and return the string result.

According to the JSR specification for Expression Language symbol '`\`' escapes both `#{}` and `${}` expressions. So, in Windows, all '`\`' are replaced by '`/`' as problems might appear with such paths: `c:\smth\${smth}`.

After evaluation symbols '\\' are returned. Expression escaping is not supported. If the expression is not valid an `InvalidExpressionException` will be thrown.

If you want to load in expression evaluator the evaluation context, use the `loadExpressionService` method and pass the evaluation context. This context will be accessible using the following variable `${['<key>']}` or `${plugin.<key>}`, where `<key>` is existing key from the provided evaluation context. If `<key>` is one word, use `${plugin.<key>}` . Otherwise, use `${plugin['<key>']}`.  

You can use a collection of already built-in functions in expression evaluator. For a full list with examples about the built-in functions, see [Expression language support]().

> **Note:**
>
> The expression evaluator service is not applicable with 'Account Templates' sites.

<span id="Transfer"></span>

### Transfer Attributes Data service

#### TransferAttributesData

This service is available with SecureTransport Pluggable Transfer Site SPI version 1.6 and serves as a container for transfer attributes. This container can be used for reading transfer attributes for the currently transferred file.

The transfer attributes contain properties, submitted through the REST API when triggering a SIT PULL, as well as:

-   `fulltarget` - the absolute path of the transferred file. When used in a route, it points to the file inside the sandbox folder.
-   `route_source_full_target` - the absolute path of the transferred file when used in a route.

> **Note:**
>
> All transfer attributes submitted through the REST API are available with their actual name in lower case.

> **Note:**
>
> fulltarget and route\_source\_full\_target are only available for SIT Push.

To use the transfer attributes container, declare a variable with `@Inject` annotation to the interface of the transfer attributes data service provided in the API:


    @Inject
    public TransferAttributesData mTransferAttributesData;

The `TransferAttributesData` object has the following capabilities:

`Map<String, Object> getTransferAttributes();` - gets the transfer attributes populated by the server.

Returns the key-value pairs of transfer attributes for the currently transferred file.

<span id="Account"></span>

### Account Attributes Data service

#### AccountAttributesData

This service is available from SecureTransport Pluggable Transfer Site SPI version 1.6 and serves as a container for account-related attributes. This container can be used for reading account-related attributes for the currently transferred file.

The account attributes contain the following properties:

-   `account_name` – the name of account transferring the file
-   `account_id` – ID of the account transferring the file
-   `account_email` – email address of the account transferring the file
-   `account_notes` – notes of the account transferring the file
-   `account_phone` – phone number of the account transferring the file
-   `account_type` – type of account transferring the file, e.g. user, template, service
-   `homedir` – home folder of the account transferring the file
-   `useruid` – UID of the account transferring the file
-   `usergid` – GID of the account transferring the file
-   `loginname` – the name of logged in user transferring the file
-   `site_name` – the name of site executing the transfer
-   `business_unit_name `– the name of business unit the account that performs the file transfer belongs to
-   `userVars.<variable>` - additional attributes of the account transferring the file

To use the account attributes container, declare a variable with `@Inject` annotation to the interface of the account attributes data service provided in the API:



    @Inject
    public AccountAttributesData mAccountAttributesData;

The `AccountAttributesData` object has the following capabilities:

-   `Map<String, Object> getAccountAttributes();` - gets the account attributes populated by the server.
-   Return the key-value pairs of account attributes for the currently transferred file.

<span id="Storage"></span>

### Storage Service

#### StorageService

Available with Pluggable Transfer Site SPI version 1.8, this service allows data to be stored and retrieved during the execution of Transfer Site methods. The data is stored on Transfer Site level, which means that it will be shared across all file transfers for single Transfer Site instance. If there are multiple subscriptions for the same Transfer Site, they will be operating with the same data.

To use the storage service implementation, declare a variable with `@Inject` annotation to the interface of the transfer attributes data service provided in the API:



    @Inject
        
    private StorageService storageService ;

The storage service allows you to create `StorageEntry` objects to be stored and retrieved using the service. It offers the following properties:

-   `key` - string - the key without the prefix from the DB.
-   `value` - string - the value of the entry in plain text.
-   `modificationDate` - LocalDateTime - the date and time in UTC of latest data modification. This field can be used to implement expiration logic in the service consumers.

The storage service implements the following capabilities:

-   `List<StorageEntry> getAll()` - retrieves all data entries for the Transfer Site.
-   `StorageEntry get(String key)` - retrieves single data entry from the Transfer Site based on the provided key.
-   `void save(StorageEntry entry)` - stores single storage entry. If the key is already present, then the existing entry is overridden.
-   `void save(List<StorageEntry> entries)` - stores a list of storage entries. Any entries that are already existing will be overridden.
-   `void delete(String key)` - deletes the entry for the specified key.

 

 
