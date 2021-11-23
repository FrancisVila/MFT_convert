{
    "title": "Custom Advanced Routing step",
    "linkTitle": "Custom Advanced Routing Step",
    "weight": "120"
}This topic explains how to develop a custom Advanced Routing step and plug it into {{< SecureTransport/componentshortname  >}}.

{{< SecureTransport/securetransportname  >}} provides a Custom Advanced Routing SPI, a set of Java interfaces and services that you can use to create, configure, and register a routing step. It is part of the SecureTransport Software Development Kit (SDK) which can be downloaded from {{< SecureTransport/supportwebsite  >}} at [support.axway.com](http://support.axway.com/).

To access the Advanced Routing SPI, unzip the SDK and open the `CustomRoutingStep\lib` folder. The `lib `folder contains the following library:

-   `securetransport-plugins-improvedrouting-spi-<version>.jar`

This JAR library holds the classes you need for implementation of Advanced Routing plug-ins. Install it in the local Maven repository following the instructions in the README file.

A custom Advanced Routing step plug-in is deployed by dropping its JAR file into `${FILEDRIVEHOME}/plugins/routingSteps` directory. The latter is automatically created when you install or upgrade {{< SecureTransport/componentshortname  >}} {{< SecureTransport/releasenumber  >}}.

The JAR file must contain all the information required for the custom step including its metadata.

## Java artifacts required for compiling the project

The artifacts required for compilation are:

-   org.hibernate:hibernate-validator:4.3.2.Final
-   javax.validation:validation-api:1.0.0.GA
-   javax:juel:2.1.0

## Structure of the JAR file containing the Advanced Routing step


    JAR ROOT
        com/axway/st/server/route/core/component/customstep/
            CustomStepArchiveBean.class
            CustomArchiveStepProducer.class
            
        messages/AdvancedRoutingMessages.xml
        html/customArchiveStep.html
            
        META-INF/
            MANIFEST.MF
            services/
                com/axway/st/server/route/step/metadata/CustomArchiveStep.xml

## Configuration resources

### Main configuration resource file

The file `/META-INF/services/com/axway/st/server/route/step/metadata/CustomArchiveStep.xml` has the following format:


    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
        <routeStepMetadata>
            <stepType>CustomArchiveStep</stepType>
            <stepCategory>Transformation</stepCategory>
            <stepDisplayName>Custom Archive Step</stepDisplayName>
            <endpointSchema>st.customarchivestep</endpointSchema>
            <uiPagePath>customStep.html</uiPagePath>
            <stepPropertyBean>com.axway.st.server.route.core.component.customstep.CustomArchiveStepBean</stepPropertyBean>
            <stepProducer>com.axway.st.server.route.core.component.customstep.CustomArchiveStepProducer</stepProducer>
        </routeStepMetadata>

Where:

-   `stepType` must be unique for the different steps. It is used for distinguishing the different steps in the SecureTransport Rest API.
-   `stepCategory` is the category of the step (`Transformation `or `Routing`).
-   `stepDisplayName` is the way the step is displayed in the SecureTransport UI.
-   `endpointSchema` must be unique for the different steps. It is used as internal ID of the custom steps.
-   `stepPropertyBean` is the bean representation of the step custom properties. It is used for validation of the properties when creating the step.
-   `stepProducer` implements the actual logic of the step for the transformations/routing of the files.

The name of the step configuration XML file must be unique across the different steps.

### Custom logs resource file

The file `/messages/AdvancedRoutingMessages.xml` contains custom messages which are used by the step.

The format is:


    <?xml version="1.0" encoding="UTF-8"?>
        <messages>
            ...
            <message>
                <id>SCCS0000</id>
                <code>ARCS0000</code>
                <text>General error while executing CustomStep step.</text>
                <description>General error while executing CustomStep step.</description>
            </message>
            <message>
                <id>SCCS0001</id>
                <code>ARCS0001</code>
                <text>Custom message with %s placeholders.</text>
                <description>Custom message for Custom Step.</description>
            </message>
            ...
        </messages>

The `ID` must be unique. The format used for the new `ID`s is as follows:


    SCCS0000

Where:

-   first two characters `SC` are an identifier
-   followed by two characters for the step abbreviation (examples are `LE `for Line Ending, `CO `for Compress, `CS `for Custom Step, etc.)
-   followed by four decimal digits for numbering in ascending order, starting from `0000 `for each step.

## Custom logging used by the Advanced Routing

The custom steps can use the defined messages in the `/messages/AdvancedRoutingMessages.xml` file of the custom step JAR.

Example:


    import org.slf4j.Logger;
    import org.slf4j.LoggerFactory;
    import com.axway.st.plugins.improvedrouting.logger.ImmutableMsg;
    import com.axway.st.plugins.improvedrouting.logger.MessagesHolder;
    import com.axway.st.plugins.improvedrouting.logger.MessagesFactory;
    // ...
    Logger sLogger = LoggerFactory.getLogger(SomeClass.class);
    MessagesHolder messagesFactory = MessagesFactory.getInstance();
    // Status code as defined in AdvancedRoutingMessages.xml
    sLogger.error(messagesFactory.getMessage("SCCS0001")
            .getFormatedMsg("parameter to replace placeholder"));
    sLogger.error(messagesFactory.getMessage("SCCS0000").getText());

The log messages will be displayed in the SecureTransport server log with the following format.


    <code> [user performing the action] [route being executed]: log message

## Available services for Custom Advanced step implemention

The following services are available for the Custom Advanced Routing step implementation:

-   `EnvService` – root of all environment service
-   `SsoEnvService` – environment about the SSO login
-   `FlowEnvService` – represents information about Subscription custom attributes; example: `flow.attributes['userVars.ATTRIBUTE_NAME']`
-   `HttpEnvService` – represents information about the HTTP transfer environment
-   `LdapEnvService` – environment about the LDAP login
-   `StfsEnvService` – represents information about the target file `stfs` attributes; example: `stfs.attributes['ATTRIBUTE_NAME']`.
-   `PesitEnvService` – represents information about the current PeSIT environment in case the transfer is via PeSIT protocol
-   `PluginEnvService` – represents specific information about the plug-in environment in case the currently logged account is authenticated using pluggable authentication
-   `AccountEnvService` – represents information about the currently logged account
-   `RoutingEnvService` – represents information about the Advanced Routing environment
-   `SSLContextService` – constructs SSLContext, SSLSocketFactory objects, to be used when connecting over secure connection to a remote partner
-   `SessionEnvService` – represents information about the current session
-   `RepencryptService` – serves repository encryption (in short &lt;i>repencrypt&lt;/i>) operations
-   `TransferEnvService` – represents information about the current transfer, including start and end time, ParentCycleId, eventID, etc.

For the full list of services and detail information, refer to the `index.html` file in **CustomRoutingStep/docs/spi/javadoc** in the unzipped SDK folder.

### Implementation of the step

The following sample implementations are available in the `CustomRoutingStep\samples` folder in the unzipped SDK folder:

-   Bean representation of the Advanced routing step properties (`CustomArchiveStepBean.java`) – a bean that is used for validation of the step properties values when the step is created or modified.
-   File processing (`CustomArchiveStepProducer.java`) – handles the actual execution of the step.

### Configuration option registration

Plug-ins can auto-register global configuration options. This can be achieved by editing the `MANIFEST.MF` file and providing the path to a specific bean, which describes the desired configuration options.

#### Example MANIFEST.MF file content:


    Plugin-Configuration-Class: com.axway.st.server.route.core.component.customstep.CustomStepConfigurationBean
    Plugin-Label: custom-step

> **Note:**
>
> The MANIFEST.MF file must end with a new line. The last line will not be parsed properly if it does not end with a new line or carriage return.

#### Example CustomStepConfigurationBean:


    package com.axway.st.server.route.core.component.customstep;
    import com.axway.st.plugins.improvedrouting.spi.Description;
    import com.axway.st.plugins.improvedrouting.spi.PluginConfigurationBase;
    /**
    Sample configuration.
    */
    public class CustomArchiveStepConfigurationBean implements PluginConfigurationBase 
    {
        private String successMessage;
        private String failureMessage;
        public CustomArchiveStepConfigurationBean() {
    }
        @Override
        public void initDefault() {
            successMessage = "STEP SUCCEEDED.";
            failureMessage = "STEP FAILED.";
        }
        @Description(value = "Message, that will be logged in Server Log in case of successful step execution.")
        public String getSuccessMessage() {
            return successMessage;
        }
        public void setSuccessMessage(String successMessage) {
            this.successMessage = successMessage;
        }
        @Description(value = "Message, that will be logged in Server Log in case of unsuccessful step execution.")
        public String getFailureMessage() {
            return failureMessage;
        }
        public void setFailureMessage(String failureMessage) {
            this.failureMessage = failureMessage;
        }
    }

The code and `MANIFEST.MF` file described above will create two configuration options - `successMessage `and `failureMessage`. Both will have default values but will be editable from the **Server Configuration** menu. The configuration option will be named following the model: "`Plugins.AdvancedRouting`" + JAR name + option name.

### CustomStepExitStatusException and previous step exit status

All advanced routing steps are capable of evaluating the exit status of the previous step. It can be either "success" or "failure" for regular steps, plus any custom string for the custom steps. Setting a custom status to your custom step is achieved by throwing `CustomStepExitStatusException` with arguments the error message to be logged and the custom status. The exit status of the previous step can be evaluated using the following expression: `${routing.precedingStepExitStatus}`.

Example:


    if (condition) {
        throw new CustomStepExitStatusException("Custom step failure message", "CustomFailureStatusExample");
     }

### Using the {{< SecureTransport/componentshortname  >}} SSLContext service

SecureTransport provides a service for creating `javax.net.ssl.SSLContext` and `javax.net.ssl.SSLSocketFactory` objects using its internal keystore. These objects can be used for setting up secure SSL connections to other applications. This service is identical to the *SSLContext service* exposed for *Custom connectors*, see [SecureTransport exposed services](../custom_connector/custom_protocol#exposed).

The service interface is called `com.axway.st.plugins.improvedrouting.environment.SSLContextService` and can be used in the process method of the custom advanced routing step using the following code:


    SSLContextService sslContextService = producerSettings.getSSLContextService();

The service methods are:

-   `SSLContext createSSLContext(String certId, boolean verifyPeer) throws SecurityException;`
-   `SSLContext createSSLContext(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(SSLContext sslContext, String[] protocols, String[] cipherSuites) throws SecurityException;`
-   `SSLSocketFactory configSSLContextFactory(String certId, boolean verifyPeer, String sslProtocol, String keyAlgorithm, String trustAlgorithm, String[] protocols, String[] cipherSuites) throws SecurityException;`

These methods have the same behavior as those from the Custom connectors’ `SSLContextService`.

### Using the SecureTransport Certificate service

{{< SecureTransport/componentshortname  >}} provides a service for certificate parsing and validation against its keystore. The service is called `com.axway.st.plugins.improvedrouting.environment.CertificateService` and can be used in the process method of the custom advanced routing step using the following code:


    CertificateService certificateService = producerSettings.getCertificateService();

This service is identical to the Certificate service exposed for Custom connectors, see [Implement a custom protocol connector](../custom_connector/custom_protocol).

It declares the following methods:

-   `CertificateStatus getCertificateStatus(X509Certificate certificate)` – validates the certificate against the {{< SecureTransport/securetransportname >}} keystore; returns one of these enumeration values: `VALID, EXPIRED, NOT_YET_VALID, UNTRUSTED`.
-   `KeyPair getKeyPair(String certificateAlias)` – Retrieves public/private key pair from the {{< SecureTransport/securetransportname >}} keystore using certificate alias.
-   `X509Certificate getCertificateByAlias(String certificateAlias)` – retrieves certificate from the {{< SecureTransport/securetransportname >}} keystore using certificate alias.
-   `X509Certificate getCertificateById(String certificateId)` – retrieves certificate from the SecureTransport keystore using certificate’s unique identifier.
-   `X509Certificate getIssuer(X509Certificate certificate)` – retrieves certificate issuer from the {{< SecureTransport/securetransportname >}} keystore for given certificate.
-   `List<X509Certificate> getCertificateChain(X509Certificate certificate)` – retrieves certificate chain list from the {{< SecureTransport/securetransportname >}} keystore for given certificate. Can be empty, if certificate does not have a chain. The first element is the certificate itself, next element is its issuer and so on to the root certificate.
-   `Collection<X509Certificate> getCertificates(String subjectDN)` – retrieves certificate list from the {{< SecureTransport/securetransportname >}} keystore for given subject DN.
-   `Subject getCertificateSubject(X509Certificate certificate)` – extracts the domain name of the `certificate`’s subject into a bean of type `Subject`, that contains the following properties: `Common name, Country, Organization, Organization Unit, Locality, State`

### Using the SecureTransport Logging service

{{< SecureTransport/securetransportname  >}} provides a service for logging messages and exceptions with a different log level. The service interface is called `com.axway.st.plugins.improvedrouting.services.LoggingService` and can be used in the process method of the custom advanced routing step using the following code:


    LoggingService loggingService = producerSettings.getLoggingService();

The *LoggingService* interface declares functionality for logging messages and exceptions with a different log level – ERROR, WARN, INFO, DEBUG, etc.

This service is identical to the Logging service exposed for Custom connectors, see [SecureTransport exposed services](../custom_connector/custom_protocol#exposed).

Examples:


    loggingService.debug("Start custom AR step processing...");
    loggingService.info("Environments: " + producerSettings.toString());
    loggingService.error("Error during Custom AR processing", e);

The logging level can be controlled by logger in `tm-log4j.xml` and `admin-log4j.xml`.

### Using the SecureTransport Expression Evaluator service

{{< SecureTransport/securetransportname  >}} provides a service for evaluating and validating expressions used in the custom step implementation.

The service interface is called `com.axway.st.plugins.improvedrouting.services.ExpressionEvaluatorService` and can be used in the process method of the custom advanced routing step using the following code:


    ExpressionEvaluatorService loggingService = producerSettings.getExpressionEvaluatorService();

This service is identical to the Expression Evaluator service exposed for Custom connectors, see [Implement a custom protocol connector](../custom_connector/custom_protocol).

Examples:



    Map<String, Object> expressionContext = new HashMap<>();

     
    expressionContext.put(AccountEnvService.ENVIRONMENT_KEY, producerSettings.getAccountEnvService());
    expressionContext.put(LdapEnvService.ENVIRONMENT_KEY, producerSettings.getLdapEnvService());

    expressionContext.put(FlowEnvService.ENVIRONMENT_KEY, producerSettings.getFlowEnvService());

    expressionContext.put(HttpEnvService.ENVIRONMENT_KEY, producerSettings.getHttpEnvService()); 
     expressionContext.put(SessionEnvService.ENVIRONMENT_KEY, producerSettings.getSessionEnvService());

    expressionContext.put(TransferEnvService.ENVIRONMENT_KEY, producerSettings.getTransferEnvService());

    expressionContext.put(StfsEnvService.ENVIRONMENT_KEY, producerSettings.getStfsEnvService());

    expressionContext.put(SsoEnvService.ENVIRONMENT_KEY, producerSettings.getSsoEnvService());

    expressionContext.put(PluginEnvService.ENVIRONMENT_KEY, producerSettings.getPluginEnvService());

    expressionContext.put(RoutingEnvService.ENVIRONMENT_KEY, producerSettings.getRoutingEnvService());
     

    mExpressionEvaluatorService.loadExpressionService(expressionContext);

> **Note:**
>
> The internal StProducer object is not instantiated for every execution. It reuses the already existing instances which are shared between executions, leading to shared instance members as well. Therefore, to have correct data in producerSettings, the services should not be assigned to variables once and then reused multiple times. Instead, any service within the producerSetting should be evaluated using the getter method each time before using it.

## Step deployment

The step should be placed in the `SecureTransport/plugins/routingSteps` directory. In cluster environment the step should be present on all {{< SecureTransport/componentshortname  >}} cluster nodes. Restart of the {{< SecureTransport/componentshortname  >}} Admin UI and the {{< SecureTransport/componentshortname  >}} TransactionManager is required.

## Step undeployment

Before removing the step make sure it is not used in any existing SecureTransport routes. After that the step JAR can be deleted. Restart of the {{< SecureTransport/componentshortname  >}} Admin UI and the {{< SecureTransport/componentshortname  >}} TransactionManager is required.

## Accessing third party libraries

The classes of the custom steps are loaded with custom classloader which inherits the TransactionManager classloader. If you want to use third-party libraries, then you must create a JAR together with its dependency JARs into a single executable JAR file.

## REST API

Creating the step using the SecureTransport Routes and Steps REST API:


    curl -i -X POST -A "SecureTransport\HttpClient" -H "Content-Type: application/json" -H "Accept: application/json" -H "Referer: https://<SecureTransport Host>:<SecureTransport AdminUi Port>" -u<admin name>:<admin password>; -k -d "{
        {   "type" : "CustomStep",
            "status" : "ENABLED",
            "fileFilterExpressionType" : "TEXT_FILES",
            "fileFilterExpression": "*",
            "firstCustomProperty" : "value1",
            "secondCustomProperty" : "value2"
        }
    }" https://<SecureTransport Host>:<SecureTransport AdminUi Port>/api/v1.2/routes/<simple route id>/steps
        HTTP/1.1 201 Created
        {
          "id" : "8a6883dc41ff98b60142041b4467006e",
          "link" : "https://10.232.3.92:444/api/v1.2/routes/8a6883dc41ff98b601420413b61f0068/steps/8a6883dc41ff98b60142041b4467006e",
          "status" : "success",
          "message" : "A new route step with id = 8a6883dc41ff98b60142041b4467006e is created."
        }

## UI page for custom route step

This section of the document explains how to plug the custom developed AdvancedRouting step page into {{< SecureTransport/componentshortname  >}}Admin UI.

After the deployment of the JAR, you can verify the step is plugged in {{< SecureTransport/componentshortname  >}} using the REST API:


    https://<host>:<port>/api/v1.4/routeStepsMetadata

Result:


    [ ...
            {
              "stepType" : "CustomArchiveStep",
              "stepCategory" : "Transformation",
              "stepDisplayName" : "Custom Archive Step",
              "endpointSchema" : "st.customarchivestep",
              "uiPagePath" : "customStep.html",
              "stepPropertyBean" : "com.axway.st.server.route.core.component.customstep.CustomArchiveStepBean",
              "stepProducer" : "com.axway.st.server.route.core.component.customstep.CustomArchiveStepProducer"
            }
        ... ]

The `uiPagePath` is the page you have developed for the custom Advanced Routing step.

### UI component

The user interface logic of the custom Advanced Routing step is added as JavaScript methods to a HTML file in the `/html` folder from the step JAR.

The step is displayed in the {{< SecureTransport/componentshortname  >}} Administration Tool and you can verify it by navigating to the **Routes** page.

#### Example HTML excerpt



    <style id="antiClickjack">body{display:none !important;}</style>
    <script type="text/javascript">
      if (self === top) {
        var antiClickjack = document.getElementById("antiClickjack");
        antiClickjack.parentNode.removeChild(antiClickjack);
      } else {
        top.location = self.location;
      }
      components.register(new CustomComponent());
      function CustomComponent() {
        components.register(new FileFilterActionsTemplate
          ("#fileFilterActionsContainer"));
        components.register(new StepFailureActionsTemplate
          ("#stepFailureActionsContainer"));
        function fill(currentRouteStep) {
          $('#attr-name').val(currentRouteStep.attrKey);
          $('#attr-value').val(currentRouteStep.attrValue);
        }
        function collect(collectionBean) {
          var attrKey = $.trim($('#attr-name').val());
          collectionBean.attrKey = attrKey;
          var attrValue = $.trim($('#attr-value').val());
          collectionBean.attrValue = attrValue;
        }
        var instance = new ComponentInterface();
        instance.fill = fill;
        instance.collect = collect;
        return Object.seal(instance);
      }
    </script>
    <div id="step-errors" class="errors"></div>
    <form style="width: 800px;" method="post">
      <div class="wrapper-section wide-heading">
         <div id="fileFilterActionsContainer"></div>
         <div style="height: 20px;"></div>
         <div id="stepFailureActionsContainer"></div>
         <div class="clear" style="height: 20px;"></div>
         <fieldset>
             <legend>Add new flow attribute</legend>
             <table>
                      <tr>
                             <td>         </td>
                             <td>
                        <label>Flow attribute Name:</label>
                             </td>
                             <td>
                        <input type="text" id="attr-name" value="userVars.zipFileName" style="width: 285px" />
                             </td>
                             <td>
                        <div class="contextual-help">
                            <a data-content-id="help-box-custom-step-key" title="Open contextual help" class="modern-iconhelp" tabIndex="-1" href="#">?</a>
                            <div class="help-dialog hidden">
                               <div class="dialog-header">
                                   <span class="hidden"></span><a class="btn-close" href="#">x</a>
                               </div>
                               <div class="dialog-content"></div>
                            </div>
                               <div class="hidden" id="help-box-custom-step-key">
                                  <p>The name of the flow attribute to be created. Once the step has set its value, this name can later be used as a key elsewhere in the Advanced Routing steps. </p>
                                  <p>If the value remains and the key is used as an archive name in the Compress step, the name will be the first 10 characters of the transferred file's content. </p>
                               </div>
                        </div>
                             </td>
                      </tr>
                      <tr>
                             <td>         </td>
                             <td>
                        <label>Flow attribute Value:</label>
                             </td>
                             <td>
                        <input type="text" id="attr-value" value="&#36;{getFileContent(routing.routeSourceFile, '0', '10', 'UTF-8')}" class="template-input" style="width: 285px" />
                             </td>
                             <td>
                        <div class="contextual-help">
                            <a data-content-id="help-box-custom-step-value" title="Open contextual help" class="modern-iconhelp" tabIndex="-1" href="#">?</a>
                            <div class="help-dialog hidden">
                               <div class="dialog-header">
                                       <span class="hidden"></span><a class="btn-close" href="#">x</a>
                               </div>
                               <div class="dialog-content"></div>
                            </div>
                               <div class="hidden" id="help-box-custom-step-value">
                                   <p>The value of the specified key. Currently it is the first 10 characters of the content of the file being transferred.</p>
                                   <p>The value can be any hardcoded string or an expression.</p>
                               </div>
                        </div>
                             </td>
                      </tr>
             </table>
         </fieldset>
         
    <div class="clear" style="height: 20px;"></div>
            <!-- Route legend begin. -->
            <div class="page-legend message clear">
                <p>
                    <em class="asterisk">*</em><span>Indicates required field</span>
                </p>
                <p class="template-input">Enter value or expression</p>
            </div>
            <!-- Route legend end. -->
        </div>
    </form>

To use a Component in the UI, you must only call `components.register(new CustomComponent())`. This adds the component to a registry that is used to control the flow of operations for all components and the step itself.

For every registered component the `fill()` function is called to populate previous values (in case of Edit step operation);

When the **Save** button is pressed, the following events occur:

-   Each component `validate()` function is called, if such is implemented, to ensure that all entered values are valid;
-   If validation succeeds, the `collect()` function is called to fill values in `stepBean` used to make the REST call to save new data. The dialog is closed.
