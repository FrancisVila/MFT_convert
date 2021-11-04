{
    "title": "Working with Secure Relay",
    "linkTitle": "Working with Secure Relay",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Overview](#overview)

[Prerequisites](#prerequisites)

[Installing Secure Relay Master Agent](#Installing_Secure_Relay_MA)

[Installing Secure Relay Router Agent](#Installing_Secure_Relay_RA)

[Configuring and activating Secure Relay](#Configuring_Secure_Relay)

[Confirming that the Secure Relay Router Agent is running](#Checking_Secure_Relay_RA)

[Starting the Secure Relay Master Agent](#Starting_Secure_Relay_MA)

<span id="overview"></span>

## Overview

This topic describes the steps you need to perform to set up Secure Relay for communications over the Internet.

1.  Check the Prerequisites.
2.  Install Gateway (which includes the Secure Relay Master Agent components) on your corporate network.
3.  Install the Secure Relay Router Agent in the DMZ.
4.  Configure and activate Secure Relay.
5.  Confirm that the Secure Relay Router Agent is running.
6.  Start the Secure Relay Master Agent.

<span id="prerequisites"></span>

## Prerequisites

You need Java 1.5.0 or higher to operate Secure Relay. This is installed automatically when you install the Secure Relay Router Agent.

For more information, refer to the:

-   <span style="font-style: italic;">Axway Secure Relay Router Agent Administrator's Guide</span>

<span id="Installing_Secure_Relay_MA"></span>

## Installing Secure Relay Master Agent

The Secure Relay Master Agent is automatically installed when you install Gateway.

<span id="Installing_Secure_Relay_RA"></span>

## Installing Secure Relay Router Agent

The Secure Relay Router Agent is delivered on the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span> installation DVD. Use <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.InstallerName variable">Installer</span> to install the Secure Relay Router Agent on a machine located in the DMZ, independent of Gateway.

<span id="Configuring_Secure_Relay"></span>

## Configuring and activating Secure Relay

Configure and activate Secure Relay in the Gateway configuration menu:

1.  In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span>.
2.  Select <span style="font-weight: bold;">Connectivity > SecureRelay</span>.
3.  Complete the [Secure Relay configuration parameters](../../../../gateway_userguide_(primary)/configuration_start_here/config_connectivity_paras#olh_connectivity_Secure_Relay) according to your network requirements.
4.  Click <span style="font-weight: bold;">Activate</span> to enable Secure Relay.
5.  Click <span style="font-weight: bold;">OK</span>.

<span style="font-weight: bold;">Note:</span> The Secure Relay modifications you make in the configuration menu only take effect after you restart Gateway.

### Using a secure HTTP proxy

In a configuration that has Gateway, Secure Relay and a HTTP proxy, Secure Relay must be bypassed to avoid any issues.

To do so, add a mask of the IP address of the Remote Site in the Secure Relay bypass mask and *not* a mask of the IP address of the proxy.

### Using Secure Relay Router Agent with privileged port numbers

If you want to use the Secure Relay Router Agent on privileged ports, in other words port numbers below 1024, you must do one of the following:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">OS         </th>
<th class="HeadD-Column1-Header1">Solution         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>UNIX         </td>
         <td><p>Change the owner of the Java executable used to run Secure Relay Router Agent and change the mode to <span class="code">-s</span>. By default this file is the JVM installed with <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span>. Use the commands:</p>
<ul>
<li><span class="code">chown root java</span><br />
<span class="code">chmod -s java</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td>UNIX         </td>
         <td>Start Secure Relay Router Agent as root.         </td>
      </tr>
      <tr>
         <td>Windows         </td>
         <td>Use an Administrator account when installing Secure Relay Router Agent.         </td>
      </tr>
   </tbody>
</table>

### Encrypting the Secure Relay Master Agent certificate password

In Gateway, the password used to access the Secure Relay Master Agent certificate must be encrypted using the <span class="code">pelencpass</span> command, while the <span class="code">master\_cert\_password\_dk</span> file, <span class="code">master\_cert\_password\_salt</span> file and <span class="code">master\_cert\_password\_data</span> file configuration parameters must be set accordingly. See the Secure Password Storage section for details.

<span id="Checking_Secure_Relay_RA"></span>

## Confirming that the Secure Relay Router Agent is running

When you start the Secure Relay Master Agent, it connects to the Secure Relay Router Agent(s) and communicates certain configuration parameters. Before you start the Secure Relay Master Agent, confirm that the Secure Relay Router Agent specified in the Gateway configuration menu is running.

Refer to the <span style="font-style: italic;"><span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> Router Agent Administrator Guide</span>.

<span id="Starting_Secure_Relay_MA"></span>

## Starting the Secure Relay Master Agent

The Secure Relay Master Agent starts automatically at the same time as Gateway (as long as the option <span style="font-weight: bold;">Starting/stopping of SecureRelay Master Agent is controlled by Gateway</span> is selected in the [Secure Relay advanced options](../../config_secure_relay_adv_options)).

The *Master Agent process* is monitored by Gatecontroller, on condition that:

-   Gatecontroller is activated and
-   the Master Agent lifecycle is managed by the product.  
    (if you start the Master Agent manually, it will not be monitored by Gatecontroller, and no action will be taken in case it becomes unavailable, crashes or gets stuck in some random processing).

This means that periodically, the <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> Master Agent sends heartbeats to Gatecontroller, just like any other Gateway process. The Master Agent is considered a vital process of the product, meaning that if Gatecontroller detects a problem with it (if it is blocked for some time, or crashed), it restarts the product along with a new instance of Master Agent.

All actions regarding the monitoring of the Master Agent process are logged . Note that for all log entries that refer to <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> Master Agent, the string <span class="code">XSR-MA </span>is used instead of the longer alternative.

Related topics

[About Secure Relay](../secure_relay_about)

[Overview: DMZ deployment](../../../../gateway_userguide_(primary)/ov_gateway/ov_dmz_deployment)

[Configuration: Connectivity parameters](../../../../gateway_userguide_(primary)/configuration_start_here/config_connectivity_paras#olh_connectivity_Secure_Relay)

[Configuration: Secure Relay advanced options](../../config_secure_relay_adv_options)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
