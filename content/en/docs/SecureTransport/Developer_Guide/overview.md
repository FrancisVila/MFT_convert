{
    "title": "Introduction",
    "linkTitle": "Introduction",
    "weight": "40"
}The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>'s SPI allows customers to extend the out-of-the-box capabilities in a safe and supported way. Following the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable">5.5</span> Developer Guide, they can create, update, and maintain their own plugins using a concrete version (for example 1.7) of the Service Provider Interface. Those plugins will not be deleted and can be successfully used after product update and/or upgrade. There are four different SPIs that cover the following functional areas:

-   Transfer Sites
-   Authentication
-   Authorization
-   Advanced Routing Step

Plugins for SecureTransport, that were developed and are officially supported by Axway, can be found on [Axway Support](http://support.axway.com/) website under type "Product Extensions" or in the AMPLIFY Repository.

## Glossary

This glossary provides definitions of words and abbreviations that appear throughout the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Developer's Guide.  

**SPI** - Service Provider Interface

**Plugin** - A module (Java code) that can be plugged in the product in concrete functional areas.

**Pluggable Transfer Sites or Connectors** - plugins that can be used as a Transfer Site and is responsible for pushing/pulling files.

**Custom Advanced Routing Step** - A plugin that can be used as a step within an Advanced Routing subscription.
