{
    "title": "Customizing Gateway Remote Sites for TARGET2",
    "linkTitle": "Customizing Remote Sites",
    "weight": "330"
}After importing the TARGET2 object set, you must modify the configuration of the Gateway Remote Site objects to correspond to your network environment.

The TARGET2 object set includes the following four Remote Sites objects for use in communication with a CRISTAL instance. You require each of the four Remote Sites to enable communication with a single CRISTAL instance. If you have more than one CRISTAL instance, you define four Remote Site objects for each instance.

You can modify the names attributed to the Remote Sites in the following examples, depending on the internal naming rules of your installation.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Site name</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CRISTAL_IN1</p>         </td>
         <td><p>JMS Remote Site</p>
<p>Sender only</p>
<p>Links to the Queue where CRISTAL deposits the request</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_OUT1</p>         </td>
         <td><p>JMS Remote Site</p>
<p>Receiver only</p>
<p>Links to the Queue where Gateway deposits the OK response received from SSP</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_ERR1</p>         </td>
         <td><p>JMS Remote Site</p>
<p>Receiver only</p>
<p>Links to the Queue where Gateway deposits internal error reports</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_FILE1</p>         </td>
         <td><p>PeSIT Remote Site</p>
<p>Receiver only</p>
<p>The destination of the SSP answers when it is sent as a file.</p>         </td>
      </tr>
   </tbody>
</table>

Open each CRISTAL Remote Site object in the Gateway GUI and check the settings in the **General** and **JMS** tabs as illustrated in the examples below. Adapt the settings to correspond to your network requirements.

<img src="/Images/Gateway/0300001E.png" class="maxWidth" />

<img src="/Images/Gateway/0300001F.png" class="maxWidth" />

The preceding JMS tab illustration is intended only as an example. The values you enter in this tab vary depending on your network configuration.

Open the Remote Site object CRISTAL\_FILE1 in the Gateway GUI. Check the settings of the following tabs:

-   General
-   Options
-   Network address
-   PeSIT
-   Net security

Adapt the tab settings to correspond to you network requirements.

<img src="/Images/Gateway/03000010.png" class="maxWidth" />

<img src="/Images/Gateway/03000011.png" class="maxWidth" />

<img src="/Images/Gateway/03000012.png" class="maxWidth" />

<img src="/Images/Gateway/03000013.png" class="maxWidth" />

<img src="/Images/Gateway/03000014.png" class="maxWidth" />

Activate the PeSIT protocol in the Gateway Configuration menu. Deactivate SSL/TLS options in TCP Advanced options.

Be sure that a CGate matching the CRISTAL\_FILE1 site is available and enabled. Check the IP address, listening port and protocol.

<img src="/Images/Gateway/03000015.png" class="maxWidth" />

<img src="/Images/Gateway/03000016.png" class="maxWidth" />

<img src="/Images/Gateway/03000017_623x478.png" class="maxWidth" />

<img src="/Images/Gateway/03000018.png" class="mediumWidth" />

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
