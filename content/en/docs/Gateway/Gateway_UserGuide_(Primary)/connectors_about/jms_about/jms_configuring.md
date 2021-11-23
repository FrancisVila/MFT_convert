{
    "title": "Configuring the Axway Gateway/JMS environment",
    "linkTitle": "Configuring for JMS",
    "weight": "270"
}{{< Gateway/componentlongname  >}}: Connectors

[Prerequisites](#Prerequisites)

[Configuring the JMS connector](#Configuration)

[JMS static configuration](#JMSstatic)

[JMS connector logging](#JMSlog)

[Required objects](#Required_objects)

[Creating objects for JMS transfers](#Creating_objects_for_JMS_transfers)

<span id="Prerequisites"></span>

## Prerequisites

Before you can use Gateway to send and receive JMS messages:

-   Check that Java Runtime Environment 1.4.2 or higher is installed on your machine.
-   You need to have a JMS provider.
-   You need access to the JMS provider from the machine running Gateway.
-   The `jar` files for the JMS provider must be installed on the machine running Gateway.
-   At least one queue must be defined on the JMS provider machine.
-   Ensure that the MOM user has the necessary access rights (user name + password).

<span id="Configuration"></span>

## Configuring the JMS connector

To configure Gateway for use with JMS, set up the JMS connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

-   In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select **Configure**.
-   Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > JMS</span>.
-   Click <span style="font-weight: bold;">Activate</span> to enable the connector.
-   Click <span style="font-weight: bold;">OK</span>.

<span id="JMSstatic"></span>

## JMS static configuration

The JMS java connector process is started by Gateway processes using a java command line. The configuration of the start JMS command line is done through the `[monitor]jms_command` parameter (default value is provided with Gateway installation):

\[monitor\]jms\_command='java -Xms64M -Xmx128M -DcallbackAddress=$h\_jms\_listen -Dtrace\_dir\_path=$p\_tmp\_dir -DjmsInLogProp=$p\_runtime\_dir/jms/logJMSIN.properties -DjmsOutLogProp=$p\_runtime\_dir/jms/logJMSOUT.properties -classpath $p\_runtime\_dir/jms/jmsctor.jar:$p\_runtime\_dir/jms/javax.jms.jar:$p\_runtime\_dir/jms/xerces-1.4.4.jar:$p\_runtime\_dir/jms/log4j-core-2.10.0.jar:$p\_runtime\_dir/jms/log4j-api-2.10.0.jar com.axway.gateway.jms.Gtw2Jms'

<span id="JMSlog"></span>

## JMS connector logging

The JMS connector process logs information using the log4j2 apache library. The logging information produced is configured (levels, rolling, policies etc) using two properties files:

-   one for the inbound connector (`logJMSIN.properties`)
-   one for the outbound connector (`logJMSOUT.properties`).

Two sample properties files are provided with the Gateway installation, but you can change them at will using the syntax described at <https://logging.apache.org/log4j/2.x/manual/configuration.html>.

You can also change the name and location of the properties files; to do so, update the `[monitor]jms_command` parameter.

<span id="Required_objects"></span>

## Required objects

To carry out a JMS transfer to or from a remote business partner, you require as a minimum the following Gateway objects:

-   Remote Site object

You may also need to create other objects for routing. For more information, refer to [Working with the JMS connector](../jms_working_with).

<span id="Creating_objects_for_JMS_transfers"></span>

## Creating objects for JMS transfers

This section describes how to create the following objects for JMS transfers:

-   Remote Site objects

<span id="Creating_remote_site_object_for_JMS_transfers"></span>

### Creating a Remote Site object for JMS transfers

In the Remote Site object you specify the JMS queue initialization properties and the connection parameters to your provider. You can also specify the transfer direction (Initiator/Sender or Responder/Receiver).

To create a Remote Site object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:<span style="font-weight: bold;">  
    Partner Management > Sites</span>
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node, then select <span style="font-weight: bold;">New</span> to display the <span style="font-style: italic;">New Remote Site</span> window.
3.  Complete the fields on the <span style="font-weight: bold;">[General](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab. In the <span style="font-weight: bold;">Protocol</span> field, make sure you select <span style="font-weight: bold;">JMS</span>.
4.  Complete the fields on the <span style="font-weight: bold;">[JMS](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_jms_tab)</span> tab.
5.  Click <span style="font-weight: bold;">OK</span>.  
    Gateway creates a new Remote Site object with your specified characteristics.

Once the Remote Site has been configured, the connection between Gateway and the JMS provider is made automatically.

Now that you have configured the JMS environment in Gateway, you are ready to [work with JMS](../jms_working_with).

#### Using command line

Alternatively, you can create a Remote Site object using the <span style="font-weight: bold;">[peladm create\_site](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_create_site)</span> online command.

Related topics

[About JMS](../)

[JMS connector](../jms_connector)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/JMS](../jms_working_with)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
