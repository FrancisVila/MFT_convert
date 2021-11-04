{
    "title": "Sentinel: XFBLog Tracked Object",
    "linkTitle": "XFBLog",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

## About XFBLog

When you configure Sentinel to monitor Gateway, you can import the <span style="font-style: italic;">XFBLog</span> Tracked Object. XFBLog describes the contents of a Gateway log file. This log stores traces of the events and errors that occur on a Gateway monitor.

## XFBLog Attributes

The XFBLog includes the following attributes.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Attribute</p>         </td>
         <td><p>Data Type</p>         </td>
         <td><p>Value</p>         </td>
      </tr>
      <tr>
         <td><p>ApplicationName</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Name of the relevant parameter file. This name is defined in the Gateway configuration file.</p>         </td>
      </tr>
      <tr>
         <td><p>Product</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Name of a Gateway product . This name depends on the operating system that you use.</p>         </td>
      </tr>
      <tr>
         <td><p>IdentMsg</p>         </td>
         <td><p>String</p>         </td>
         <td><p>String that identifies a message in the Gateway log file. The format of this identifier depends on the application that sends the relevant message.</p>         </td>
      </tr>
      <tr>
         <td><p>RecDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>Date on which Gateway recorded a message in the Gateway log file</p>         </td>
      </tr>
      <tr>
         <td><p>RecTime</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Time at which Gateway recorded a message in the Gateway log file</p>         </td>
      </tr>
      <tr>
         <td><p>SeverityClass</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Content and severity of an error message in the Gateway log file. The possible values of this attribute are:</p>
<ul>
<li><span style="font-weight: bold;">ES</span>: System Error</li>
<li><span style="font-weight: bold;">EC</span>: Component Error</li>
<li><span style="font-weight: bold;">EM</span>: Message Error</li>
<li><span style="font-weight: bold;">AV</span>: Error and Warning</li>
<li><span style="font-weight: bold;">IG</span>: General Information</li>
<li><span style="font-weight: bold;">IP</span>: Program Information</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

## XFBLog Predefined Request

When you configure Sentinel to monitor Gateway, you can import a predefined Request for XFBTransfer: <span style="font-style: italic;">TransferLog</span>. This Request retrieves Tracked Instances that describe the contents of a Gateway log.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
