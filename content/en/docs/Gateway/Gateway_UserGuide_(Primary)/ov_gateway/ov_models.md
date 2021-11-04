{
    "title": "Models",
    "linkTitle": "Models",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

A <span style="font-style: italic;">Model object</span> is a logical container that holds a set of reusable attributes. Models are useful when you need to repeatedly reuse a specific set of information to accomplish a series of tasks.

Gateway provides Model objects that enable you to group sets of attributes for the creation of:

-   Transfer Requests
-   Axway Messaging connector objects for Axway Messaging incoming and Axway Messaging outgoing events

<span id="Transfer_Model"></span>

## Transfer Models

You can create Models that provide sets of attributes that complete Transfer Requests. You can specify the name of a Model when you create a Transfer Request or a Decision Rule. Then, when Gateway executes the Transfer Request or Decision Rule, it extracts attributes from the named Model.

Use the Model object to define parameters such as:

-   Sender and receiver
-   Application name
-   Transfer validity date and time
-   Scheduling priority
-   User information
-   ...

There are two types of Model for use with Transfer Requests and Decision Rules:

-   <span style="font-weight: bold;">General Model</span>  
    The General Model defines a set of parameters that can be reused in a Transfer Request with any protocol. When you create a Model, you begin by creating a General Model.  
    There are some parameters that you can only define via the General Model, in particular, the <span style="font-weight: bold;">destination alias</span> (<span class="code">dest\_alias</span>), <span style="font-weight: bold;">remote agent</span> (<span class="code">remote\_agent</span>) and <span style="font-weight: bold;">originator alias</span> (<span class="code">org\_alias</span>) parameters.  
    In general, a General Model contains sufficient information for outgoing transfers.
-   <span style="font-weight: bold;">Protocol Model</span>  
    After having defined a General Model, you can optionally define a Protocol Model with the same name. The Protocol Model contains a set of protocol-specific parameters.  
    A Protocol Model may be useful when you are submitting a Transfer Request that has a Diffusion List as its destination. If the members of the Diffusion List are serviced by different protocols, Gateway can use the Protocol Model to apply the appropriate protocol to each destination Site.

When you specify the Model name to use in a Transfer Request or a Decision Rule, Gateway first extracts the parameters specified in the Protocol Model and then completes the definition with parameters taken from the General Model with the same name.

<span style="font-weight: bold;">Note:</span> If you set the same parameters in both the Transfer Request and the Model objects, the Transfer Request parameters override the parameters you set in the Model.

### Using Models in Transfer Requests

To accelerate the process of creating a Transfer Request, you can specify the name of a Model to use as one of the Transfer Request parameters.

### Using Models in Decision Rules

As described in [Event management](../ov_events), when you can create Decision Rule objects to link Gateway processes to triggering events, you can set the execution type to <span style="font-style: italic;">Model</span> and then specify the name of the Model to apply. You can specify the name of an existing Model or a Model that is not yet defined. If the Model is not already defined, complete the object definition before executing the Decision Rule.

When you implement Model-based routing via Decision Rules, you must specify the final destination for the transfer either by entering a value for the <span style="font-weight: bold;">destination alias</span> (<span class="code">dest\_alias</span>) or the <span style="font-weight: bold;">remote agent</span> (<span class="code">remote\_agent</span>). You can <span style="font-weight: bold;">only</span> define these two Transfer parameters in a General Model, and not in a Protocol Model.

When you use Gateway to route files via a Model object:

-   The Model name that you specify must correspond to a General Model definition and can optionally correspond to a Protocol Model with the same name
-   The specified General Model must include a final destination
-   Either the General Model or the Protocol Model must contain values for the parameters: <span style="font-weight: bold;">file component</span> (<span class="code">-file\_component</span>) and <span style="font-weight: bold;">application</span> (<span class="code">-appli</span>)

If you set the execution type to <span style="font-style: italic;">Model</span> in a Decision Rule, it is recommended that you use symbolic variables in the Model definition. For example:


    file_component = &(dir_path)/&(file_component)
    application = &(appli)
    destination_alias = &(dest_alias)

This ensures that when the Decision Rule invokes the Model to process a Transfer Request, the attributes that the Model uses for the transfer correspond to the attributes that are contained in the transfer that is being handled.

<span id="XMS_connector_model"></span>

## XMS Models

The Axway Messaging product serves as Messaging-Oriented Middleware. Axway Messaging components (servers, clients and administrative tools) provide an environment in which applications can exchange messages without directly communicating with each other. The Axway Messaging environment functions using Axway proprietary protocols.

Use the XMS Model object to define the set of connector attributes to support either:

-   Incoming Axway Messaging messages originating from a specified Axway Messaging server and queue
-   Outgoing messages to be sent to a specified Axway Messaging server message queue

[Next topic](../ov_monitoring_gateway)

Related topics

[About Models](../../transfers_start_here/parameters_start_here/models_start_here)

[Working with Transfer Models](../../transfers_start_here/parameters_start_here/models_start_here/working_with_models_(gui))

[Working with XMS Models](../../transfers_start_here/parameters_start_here/models_start_here/managing_xms_models)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
