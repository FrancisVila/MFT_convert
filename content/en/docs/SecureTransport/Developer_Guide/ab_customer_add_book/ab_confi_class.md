{
    "title": "Create a configuration class",
    "linkTitle": "Create a configuration class",
    "weight": "140"
}A new file configuration class is created in the sample code. The `isParentGroupAdded` method specifies if the provider requires the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> server to generate a system Address Book entry which will be used as a parent group for all Address Book entries returned by the provider.


    package com.axway.st.plugins.abcustomsource.sdk.file.configuration;
    import com.axway.st.plugins.absource.AddressBookProviderConfiguration;
    /**
     * File Configuration.
     *
     */
    public class AddressBookFileProviderConfiguration implements AddressBookProviderConfiguration {
        @Override
        public String getDefaultParentGroupName() {
            return "file-based";
        }
        @Override
        public boolean isParentGroupAdded() {
            return true;
        }
    }
