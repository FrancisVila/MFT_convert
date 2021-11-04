{
    "title": "X.400",
    "linkTitle": "X.400",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[X.400](#x400)

[Addressing](#addressing)

[X.400 components](#x400_components)

[X.400 protocols](#x400_protocols)

This topic introduces the X.400 protocol.

<span id="x400"></span>

## About X.400

X.400 is a messaging standard, based on a set of ITU-T Recommendations, each in the 400-number range. These Recommendations define standards for Data Communication Networks for Message Handling Systems (MHS).

X.400 is an alternative to the more common SMTP email protocol. It is often used for the transmission of EDI messages, for example in the European food trade.

<span id="addressing"></span>

## Addressing

Originators and recipients of an X.400 message are identified by their X.400 Originator/Recipient addresses (O/R addresses). X.400 specifies a number of possible address characteristics that do not exist in SMTP.

An X.400 address consists of several parts. In the short form (string form) each part has a tag, for example:

"C=SE;A=400NET;P=FRONTEC;O=AMT;OU1=X420UA;CN=EDI;"

### X.400 address elements

The following table lists the most-commonly-used X.400 address elements.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Tag</p>         </td>
         <td><p>Meaning</p>         </td>
         <td><p>Max length</p>         </td>
      </tr>
      <tr>
         <td><p>C</p>         </td>
         <td><p>Country name</p>         </td>
         <td><p>3 characters</p>         </td>
      </tr>
      <tr>
         <td><p>A</p>         </td>
         <td><p>ADMD, Administrative Management Domain name. Usually a public mail service provider.</p>         </td>
         <td><p>16 characters</p>         </td>
      </tr>
      <tr>
         <td><p>P</p>         </td>
         <td><p>PRMD, Private Management Domain name</p>         </td>
         <td><p>16 characters</p>         </td>
      </tr>
      <tr>
         <td><p>O</p>         </td>
         <td><p>Organization name</p>         </td>
         <td><p>64 characters</p>         </td>
      </tr>
      <tr>
         <td><p>OU1-4</p>         </td>
         <td><p>Organizational Unit names</p>         </td>
         <td><p>34 characters</p>         </td>
      </tr>
      <tr>
         <td><p>S</p>         </td>
         <td><p>Surname</p>         </td>
         <td><p>40 characters</p>         </td>
      </tr>
      <tr>
         <td><p>G</p>         </td>
         <td><p>Given name</p>         </td>
         <td><p>16 characters</p>         </td>
      </tr>
      <tr>
         <td><p>I</p>         </td>
         <td><p>Initials</p>         </td>
         <td><p>5 characters</p>         </td>
      </tr>
      <tr>
         <td><p>CN</p>         </td>
         <td><p>Common name</p>         </td>
         <td><p>64 characters</p>         </td>
      </tr>
      <tr>
         <td><p>DDAT</p>         </td>
         <td><p>Domain-defined Attribute Type, specific to a messaging domain and used to pass non-standard information.</p>         </td>
         <td><p>8 characters</p>         </td>
      </tr>
      <tr>
         <td><p>DDAV</p>         </td>
         <td><p>Domain-defined Attribute Value. Always set together with, and following, the DDAT.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Q</p>         </td>
         <td><p>General Qualifier</p>         </td>
         <td><p>3 characters</p>         </td>
      </tr>
   </tbody>
</table>

### Example

The SMTP email address:

joe.smith@dev.axway.fr

might look like this in an X.400 email message:

G=joe; S=smith; O=axway; OU=dev; PRMD=sopranet; ADMD=sopranet; C=fr

<span id="x400_components"></span>

## X.400 components

Message handling is a distributed information processing task that integrates two related sub-tasks: <span style="font-style: italic;">message transfer</span> and <span style="font-style: italic;">message storage</span>.

The main components used in X.400 communication are:

-   Message Transfer Agents (MTA)
-   Message Stores (MS)
-   User Agents (UA)

<span id="x400_protocols"></span>

## X.400 protocols

The protocols defined by the standard are:

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Usage</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>P1</p>         </td>
         <td><p>MTA - MTA</p>         </td>
         <td><p>End-to-end message transfer service.</p>         </td>
      </tr>
      <tr>
         <td><p>P3</p>         </td>
         <td><p>MTA - UA</p>         </td>
         <td><p>Communication between UAs and MTAs.</p>         </td>
      </tr>
      <tr>
         <td><p>P7</p>         </td>
         <td><p>UA - MS</p>         </td>
         <td><p>An increasingly widely used protocol for communication between the UA and the MS.</p>
<p>Typical P7 operations:</p>
<ul>
<li>Bind to Message Store</li>
<li>UnBind from Message Store</li>
<li>List Messages held in Message Store</li>
<li>Fetch Messages/Notifications/Reports</li>
<li>Submit Messages/Notifications/Reports</li>
<li>Delete message from Message Store</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>P2/P22</p>         </td>
         <td><p>Interpersonal messaging (IPM)</p>         </td>
         <td><p>Defines the format of a structured memo-like document having two main components: the heading and the body part(s).</p>
<p>The heading specifies things like the originator and recipient of the message, copy and blind copy recipients of the message, whether the originator es to receive a notification for the message and in what circumstances etc.</p>
<p>The body part may be one of many forms of data - those specified by the standard include Ia5 text, G3Fax, Images, Audio data etc.</p>
<p>Messages may also be encapsulated within messages, providing a clean and structured forwarding mechanism.</p>         </td>
      </tr>
   </tbody>
</table>

 

Related topics

[X.400 connector](x400_connector)

[Configuring Gateway for X.400](x400_configuring)

[Managing X.400 partners](x400_managing_partners)

[Working with X.400](x400_working_with)

[X.400 O/R address](../../configuration_start_here/config_protocols_about/x400_or_address)

[X.400 log messages](../../log_messages_about/x400_messages)

 

More information

For details of ITU-T Recommendations, go to:

<http://www.itu.int/ITU-T/dbase/index.html>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
