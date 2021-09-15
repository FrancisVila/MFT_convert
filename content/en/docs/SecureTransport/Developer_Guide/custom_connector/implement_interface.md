{
    "title": "Implement a user interface",
    "linkTitle": "Implement a user interface",
    "weight": "90"
}SecureTransport Transfer Sites can be created and modified through the SecureTransport Administration Tool and SecureTransport REST API. In order to create a Pluggable Transfer Site that can be saved and modified by SecureTransport administrators, you must first implement the `com.axway.st.plugins.site.UIBean` interface from the Pluggable Transfer Site SPI.

The UIBean implementation must be a simple Java bean that describes the custom connector properties which will be saved into the SecureTransport database. These properties describe the connector and depending on the protocol; they can contain host, port, username, upload folder and so on. They will be visualized in the Administration Tool when an administrator creates an instance of the Pluggable Transfer Site.

Below is a an example implementation, called `FtpBean` which demonstrates the creation of an FTP Pluggable Transfer Site.

    public class FtpBean implements UIBean {
        /** Holds the partner hostname. */
        private String mPartnerHost;
        /** Holds the partner port. */
        private Integer mPartnerPort;
        /** Holds the login name. */
        private String mPartnerUserName;
        /** The user's password. */
        private String mUserPassword;
        /** The remote folder to download files from. */
        private String mPartnerDownloadFolder;
        /** The download pattern. */
        private String mPartnerDownloadPattern;
        /** The remote folder to push files to. */
        private String mPartnerUploadFolder;
        /** Holds the network zone name. */
        private String mNetworkZone;
        /** Whether Active or Passive mode should be used. */
        private boolean mIsPassiveMode;
        /** Whether to use FTP over secure connection. */
        private boolean mUseFtps;
        /** Holds the certificate id, of the private key to authenticate with. */
        private String mClientCertificateIdLocalCertificate;
        /** A flag indicating if sending file with different name is enabled. */
        private boolean mSendFileAsEnabled;
        /** The new file name to be used when sending the file. */
        private String mSendFileAs;
    }

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Special symbols like periods (<code>.</code>) or dashes (<code>-</code>) are not allowed in pluggable transfer site property names.         </td>
      </tr>
</table>

You can use bean validation annotations from the `javax.validation.constraints.*` package (part of Java Bean Validation 1.0 (JSR 303)), if you would like to validate any of the properties defined in the UIBean implementation. For example, you can add the following annotations to validate the `PartnerHost`, `PartnerPort` and `PartnerUsername` properties for incorrect values:

    /** Holds the partner hostname. */
        @NotNull(message="Host could not be null")
        @Size(min=1, message="Host could not be empty")
        @Pattern(regexp="\\S*", message="Host could not contain whitespaces.")
        private String mPartnerHost;

    /** Holds the partner port. */
        @NotNull(message="Port could not be null")

        @Min(value=0, message="Port should not be a negative integer.")
        @Max(value=65535, message="Invalid port number. It should be less or equal to 65535.")
        private Integer mPartnerPort;

        /** Holds the login name. */
        @NotNull(message="Username could not be null")
        @Size(min=1, message="Username could not be empty")
        @Pattern(regexp="\\S*", message="Username could not contain whitespaces.")
        private String mPartnerUserName;

The UIBean implementation must define accessor methods (get and set methods) for every field, so the property can be retrieved and modified. Also, the Pluggable Transfer Site SPI provides `com.axway.st.plugins.site.Encrypted` annotation which indicates that a specific property should be encrypted. This annotation needs to be added to both accessors of the property to indicate that this specific property needs to be encrypted. For example, if you have already defined the bean property `UserPassword` (`private String mUserPassword;`), you must define accessor methods annotated with the encrypted annotation so that the `mUserPassword` is encrypted when stored in the database:

        @Encrypted
        public String getUserPassword() {
          return mUserPassword;
        }
        @Encrypted
        public void setUserPassword(String password) {
          mUserPassword = password;
        }

To associate a custom site with a certificate, the certificate custom property should be named with a `LocalCertificate`, `PartnerCertificate` or `LoginCertificate` suffix depending on the certificate usage.

The following is an example of certificate custom property added to the `FtpBean` implementation, which holds login certificate id.

    /** Holds the certificate id, of the private key to authenticat with.*/
    private String mClientCertificateIdLocalCertificate; 

The next step of creating the user interface of the custom connector is to define the HTML file that will be loaded by SecureTransport Administration Tool on the *Transfer Sites* configuration page. The HTML file allows the administrator to create and save custom connectors to the database.

The HTML file should display UIBean properties and should provide JavaScript functions for loading and saving these properties to the database. The JavaScript functions could be defined as a script inside the HTML file or in a separate JavaScript file. An example HTML file can be found in the example implementation of the Custom connector included in SecureTransport Software Development Kit.

You need to follow specific conventions when writing your JavaScript code to enable SecureTransport administrators to create and save your Custom Transfer Site using the SecureTransport Administration Tool. Your JavaScript code must define the specific functions that SecureTransport will call to save and load your custom site properties.

First of all, you must use the `pluginRegister` object, which is the integration point between the SecureTransport Administration tool and your JavaScript code. The `pluginRegister` object is a special object that is exposed by SecureTransport allowing you to register a custom component that implements predefined load and save functions.

For instance, your JavaScript code should look like:

    pluginRegister.setPluginComponent(new CustomPluginSite());
    function CustomPluginSite() {
        function load(accountName, siteId) {
            // implement load custom site properties
        }
        function save(siteData, callback) {
            // implement save custom site properties
        }
        var instance = new PluginComponentInterface();
        instance.load = load;
        instance.save = save;
        return Object.seal(instance);

When implementing the `load` function, you must use the SecureTransport REST API to retrieve:

-   Custom transfer site data from the database
-   Available network zones
-   Available certificates (can be used to authenticate to the remote partner)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When a custom transfer site is updated with a change in the transfer protocol, the correct default data must be retrieved. Check if the loaded transfer site has the same type of transfer protocol. Default values like the network zones list must be retrieved even when a change in the protocol is made.         </td>
      </tr>
</table>

    if (siteId) {
        $.ajax({
        url : "/api/v2.0/sites/" + siteId,
        type: 'GET',
        dataType : 'json',
        cache: false,
        success : function(data) {
            if (data && data['protocol'] === 'myftp') {
                //check if the loaded transfer site is of custom TS type, otherwise load default data
                // load custom data for this transfer site
            } else {
                // load default data
            }
        }
    });
    } else {

The custom transfer site is returned by SecureTransport REST API as a key-value map containing all custom site properties as described in the UIBean implementation. After retrieving these properties, they should be populated and displayed in the custom HTML file.

When implementing the `save` function, you must collect all properties filled by the administrator in the custom HTML file and use a POST REST request to save the properties into the SecureTransport database. When you save custom properties as key-value pairs using POST REST request, the keys should be named exactly the same as the properties of the class that implemented the UIBean interface. If you want to implement validation for the site properties, you should add the validation in the save function. In order to propagate any validation errors, you should use the callback function with the desired error message as an argument:

-   `callback(“Custom validation error”);`

If the save action is successful and there are no errors, the last action of the save function should be to call the function without arguments:

-   `callback();`

## SecureTransport REST API resources

In order to save the custom transfer site, you should initiate an authorized POST REST request to the following resource:

-   `/api/v2.0/sites`

In order to load the custom site properties, you should initiate an authorized GET REST request to the following resource:

-   `/api/v2.0/sites/<siteId>`

In case of a successful call, the function will receive a data map with the key - value pairs of the name and the value of the properties for the site.

You can retrieve available certificates by sending a GET REST request to the following resource:

-   `/api/v2.0/certificates`

Available network zones can be retrieved by GET REST request to the following resource:

-   `/api/v2.0/zones`

For more details about implementing the User Interface for the Custom Transfer Site, review the examples included in SecureTransport Software Development Kit.

For more information about the resources, refer to Swagger documentation for SecureTransport API 2.0.
