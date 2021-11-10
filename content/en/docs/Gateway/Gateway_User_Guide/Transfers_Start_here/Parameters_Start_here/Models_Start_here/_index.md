{
    "title": "Managing models",
    "linkTitle": "Managing model objects",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Models](#intro)

[General Models and Protocol Models](#gen_and_protocol)

[Models for Transfer Requests](#models_for_trans_req)

[Models for Decision Rules](#Using_Models_in_Decision_Rules)

[Models for Axway Messaging connector objects](#messaging_connector)

[JMS Properties and the Model object](#JMS_Properties)

Related topics

[Working with Transfer Models](working_with_models_(gui))

[Working with XMS Models](managing_xms_models) (for Axway Messaging)

[Working with Purge Models](working_with_purge_models) (to purge the Mailbox)

<span id="intro"></span>

## Models Introduction

Gateway Model objects enable you to group sets of attributes for the creation of:

-   Transfer Requests
-   Decision Rules
-   Axway Messaging connector objects

<span id="gen_and_protocol"></span>

### General Models and Protocol Models

For Transfer Requests and Decision Rules, a Model can either be a <span style="font-style: italic;">General</span> Model or a <span style="font-style: italic;">Protocol</span> Model.

When you create a Model, you begin by creating a General Model. The General Model defines a set of parameters that can be reused by any protocol. Then you can optionally create a Protocol Model, with a set of protocol-specific parameters, that bears the same name.

When you specify the Model name to use in a Transfer Request or a Decision Rule, Gateway first extracts the parameters specified in the Protocol Model and then completes the definition with parameters taken from the General Model with the same name.

Note that parameters specific to a protocol will only be used if the resulting transfer uses that protocol.

<span id="models_for_trans_req"></span>

### Models for Transfer Requests

Model objects are not mandatory for Transfer Requests. However, when you define a Transfer Request, you can provide certain parameters via the Model object.

Models accelerate the process of defining Transfer Requests by grouping a set of reusable Transfer attributes. Rather than redefining frequently-used parameters each time you submit a Transfer Request, you can specify a previously defined Model object as a Transfer Request parameter. If the same parameters are defined in both the Model and the Transfer, the Transfer definition takes precedence.

For example, you can use a Model to define the following:

-   Transfer sender and receiver
-   Application name
-   Transfer validity date and time
-   Scheduling priority
-   User information

<span id="Using_Models_in_Decision_Rules"></span>

### Models for Decision Rules

Model objects are not mandatory for Decision Rules. However, they are useful when defining processing sequences in Decision Rules.

When you define routing behavior via Decision Rule objects, you can set the execution type to <span style="font-style: italic;">Model</span> and then specify the name of the Model to apply. You can specify the name of an existing Model or a Model that is not yet defined. You must however complete the Model object definition before executing the Decision Rule.

When you implement Model-based routing via Decision Rules, you must specify the final destination for the transfer either by entering a value for the <span style="font-weight: bold;">destination alias</span> (<span class="code">dest\_alias</span>) or the <span style="font-weight: bold;">remote agent</span> (<span class="code">remote\_agent</span>). You can <span style="font-weight: bold;">only</span> define these two Transfer parameters in a General Model, and not in a Protocol Model.

When you use Gateway to route files via a Model object:

-   The Model name that you specify must correspond to a General Model definition and can optionally correspond to a Protocol Model with the same name
-   The specified General Model must include a final destination
-   Either the General Model or the Protocol Model must contain values for the parameters: <span style="font-weight: bold;">file component</span> (<span class="code">file\_component</span>) and <span style="font-weight: bold;">application</span> (<span class="code">appli</span>)

<span id="messaging_connector"></span>

### Models for Axway Messaging connector objects

Use Axway Messaging connector objects to handle Axway Messaging incoming and outgoing events in Gateway. When creating an Axway [Messaging connector](../../../connectors_about/messaging_connector) you require at least one XMS Model object.

<span id="JMS_Properties"></span>

### JMS Properties and the Model object

You can enter JMS message properties in the Model object. Gateway adds these properties to the JMS message.

To help you complete the properties in the Model, first create a Property List.

Related topics

[Overview: Models](../../../ov_gateway/ov_models)

[Working with Transfer Models](working_with_models_(gui))

[Working with XMS Models](managing_xms_models) (for Axway Messaging)

[Working with Property Lists](managing_property_lists) (for Axway Messaging or JMS)

[Working with Purge Models](working_with_purge_models) (to purge the Mailbox)

[Working with Models (command line)](working_with_models_cli)

[Working with Purge Models (command line)](working_with_purge_models_cli)

[Model objects: Parameters List](model_object_parameter_list)

[Managing Events on Gateway](../../../managing_events_start_here) (Decision Rules and Rule Tables)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
