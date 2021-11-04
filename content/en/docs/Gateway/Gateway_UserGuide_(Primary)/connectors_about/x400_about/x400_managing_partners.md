{
    "title": "Managing X.400 partners",
    "linkTitle": "Managing X.400 partners",
    "weight": "280"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About X.400 partner management](#about)

[Prerequisites](#prerequisites)

[Managing X.420 partners in PassPort PM](#managing_x420_partners)

<span id="about"></span>

## About X.400 partner management

For the X.400 protocol, Gateway makes use of the partner management function provided by Axway PassPort. You use PassPort PM to view, create, modify or delete X.400 users, or partners. In this version of Gateway, X.420 partners are supported.

This topic describes the X.400-specific parameters in PassPort PM.

<span id="prerequisites"></span>

## Prerequisites

In addition to installing Gateway (and any available patches) you must install PassPort PM V3.4.4 (or later) and the latest patch(es).

<span id="managing_x420_partners"></span>

## Managing X.420 partners in PassPort PM

1.  Log in to PassPort PM.
2.  Click the <span style="font-weight: bold;">PassPort Administration</span> tab.
3.  In the left menu, select <span style="font-weight: bold;">Profile Management > Communication Protocol > Open Communication Protocol</span>.
4.  On the <span style="font-weight: bold;">General</span> tab, in <span style="font-weight: bold;">Protocol Type</span>, select <span style="font-weight: bold;">X420-Users</span>.
5.  Click <span style="font-weight: bold;">Search</span>.  
    PassPort PM displays a list of all available X.420 partners.
6.  To view or edit partner details, click the eye icon at the right of the line for that partner.  
    PassPort PM displays general information about the partner.
7.  Click the <span style="font-weight: bold;">Protocol</span> tab to display X.400-specific parameters related to this partner.
8.  Edit the parameters as required.
9.  Click <span style="font-weight: bold;">OK</span> to save your changes or <span style="font-weight: bold;">Cancel</span> to quit without making changes.

#### X.420 partner parameters

The following table lists X.400-specific parameters.

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Name (prefixed by X400_)</p>         </td>
         <td><p>Format and value</p>         </td>
         <td><p>Category (1)</p>         </td>
         <td><p>Remarks</p>         </td>
      </tr>
      <tr>
         <td><p>X420:</p>         </td>
      </tr>
      <tr>
         <td><p>USER_ALIAS</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p> </p>         </td>
         <td><p>The alias name of the X.420 partner.</p>         </td>
      </tr>
      <tr>
         <td><p>UA_NAME</p>         </td>
         <td><p>PrintableString 1..16</p>         </td>
         <td><p>Local</p>         </td>
         <td><p>The name of the UA attached to this user. The name is only used locally in the system: it is not in any of the X.400 protocols. This name is used by the UA servers when they register themselves in the local MTA. The defined UA name value must be the same value as the value defined for the UA processes (x420s) u start option.</p>
<p>You can add multiple entries with the same UA_NAME. This makes it possible to correlate multiple O/R addresses to a specific UA, which is the case when multiple local partners have been defined. The UA name value used must contain the substring 420.</p>         </td>
      </tr>
      <tr>
         <td><p>MTA_NAME</p>         </td>
         <td><p>IA5-string 1..32</p>         </td>
         <td><p>Remote</p>         </td>
         <td><p>This optional parameter is used to explicitly correlate a remote X.420 partner with an external MTA. When the local MTA gets a message that is addressed to this partner, the message is routed to this MTA.</p>
<p>The MTA name must match a remote MTA defined in the MTA Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>MS_NAME</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p>Local</p>         </td>
         <td><p>The Message Store attached to this user (if MS used).</p>         </td>
      </tr>
      <tr>
         <td><p>MESSAGE_STORE_USED</p>         </td>
         <td><p>Boolean { True | False }</p>         </td>
         <td><p>Local</p>         </td>
         <td><p>This parameter indicates if this UA entry is connected to a Message Store (True) or to the local MTA (False).</p>
<p>If this parameter is set to True, there is an MSP7 Remote Site definition that is correlated to this UA entry. The Remote Site entry contains information about the remote mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>SUBSET_ADDR_USED</p>         </td>
         <td><p>Boolean { True | False }</p>         </td>
         <td><p>Local</p>         </td>
         <td><p>Match OR_ADDRESS exactly for incoming message or not.</p>
<p>If this parameter is set to True, match UA_OR_ADDR address attributes exactly. In other words, messages are put in the UA in-queue only if the recipient address contains address attributes that exactly match this address.</p>
<p>If set to False, match at least these UA_OR_ADDR: address attributes. In other words messages are put in the UA in-queue if the recipient address contains at least these attributes.</p>         </td>
      </tr>
      <tr>
         <td><p>DELIVERY_TIMEOUT</p>         </td>
         <td><p>Decimal digits</p>         </td>
         <td><p>Local</p>         </td>
         <td><p>Timeout in minutes. Default = 1440 (24 hours).</p>
<p>The parameter defines the number of minutes that a delivered message can stay in the UA in-queue. If the UA does not read the message and accepts the responsibility for it, the MTA will remove the message from the in-queue and send a non-delivery notification to the message originator. If the value is set to 0, it means that the UA has a retrieval queue. This implies that the responsibility for the message is imposed on the UA as soon as the message is placed in its in-queue, and the MTA does then not supervise this queue.</p>         </td>
      </tr>
      <tr>
         <td><p>OR_ADDRESS:</p>         </td>
         <td><p>The OR_ADDRESS is mandatory. It contains the X.400 O/R address information of the X.420 partner.</p>         </td>
      </tr>
      <tr>
         <td><p>CN</p>         </td>
         <td><p>PrintableString 2..2</p>         </td>
         <td><p> </p>         </td>
         <td><p>Country Name identifies the country.</p>         </td>
      </tr>
      <tr>
         <td><p>ADMD</p>         </td>
         <td><p>PrintableString 1..16</p>         </td>
         <td><p> </p>         </td>
         <td><p>Administration Domain Name. Identifies an ADMD relative to the country specified by the Country Name. An ADMD provides a public messaging service within a single country. Several ADMDs may exist within a country.</p>         </td>
      </tr>
      <tr>
         <td><p>PRMD</p>         </td>
         <td><p>PrintableString 1..16</p>         </td>
         <td><p> </p>         </td>
         <td><p>Private Domain Name. Identifies a PRMD relative to the ADMD or the Country. A PRMD is a messaging service within an organization. The ADMD operator must uniquely assign the Name of the Private Domain if the PRMD is connected to an ADMD service.</p>         </td>
      </tr>
      <tr>
         <td><p>ORG_NAME</p>         </td>
         <td><p>PrintableString 1..64</p>         </td>
         <td><p> </p>         </td>
         <td><p>Organization name address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>ORG_UNIT_NAME_1</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p> </p>         </td>
         <td><p>Organization unit name address attributes</p>         </td>
      </tr>
      <tr>
         <td><p>ORG_UNIT_NAME_2</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ORG_UNIT_NAME_3</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ORG_UNIT_NAME_4</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>COMMON_NAME</p>         </td>
         <td><p>PrintableString 1..64</p>         </td>
         <td><p> </p>         </td>
         <td><p>An RFC1685 encoding format of the O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>FREE_FORM_NAME</p>         </td>
         <td><p>PrintableString 1..64</p>         </td>
         <td><p> </p>         </td>
         <td><p>Free-form name address attribute of the O/R descriptor.</p>         </td>
      </tr>
      <tr>
         <td><p>TELEPHONE_NUMBER</p>         </td>
         <td><p>PrintableString 1..32</p>         </td>
         <td><p> </p>         </td>
         <td><p>Telephone number address attribute of the O/R descriptor.</p>         </td>
      </tr>
      <tr>
         <td><p>DOMAIN_DEF_ATTR_1:</p>         </td>
         <td><p>Optional domain-defined attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_TYPE_1</p>         </td>
         <td><p>PrintableString 1..8</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute type address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_VALUE_1</p>         </td>
         <td><p>PrintableString 1..128</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute value address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DOMAIN_DEF_ATTR_2:</p>         </td>
         <td><p>Optional domain-defined attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_TYPE_2</p>         </td>
         <td><p>PrintableString 1..8</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute type address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_VALUE_2</p>         </td>
         <td><p>PrintableString 1..128</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute value address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DOMAIN_DEF_ATTR_3:</p>         </td>
         <td><p>Optional domain-defined attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_TYPE_3</p>         </td>
         <td><p>PrintableString 1..8</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute type address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_VALUE_3</p>         </td>
         <td><p>PrintableString 1..128</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute value address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DOMAIN_DEF_ATTR_4:</p>         </td>
         <td><p>Optional domain-defined attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_TYPE_4</p>         </td>
         <td><p>PrintableString 1..8</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute type address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>DDA_VALUE_4</p>         </td>
         <td><p>PrintableString 1..128</p>         </td>
         <td><p> </p>         </td>
         <td><p>Domain-defined attribute value address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>PERSONAL_NAME:</p>         </td>
         <td><p>Optional subgroup within OR_ADDRESS containing the personal address attributes: SURNAME, GIVENNAME, INITIALS and GQ.</p>         </td>
      </tr>
      <tr>
         <td><p>SURNAME</p>         </td>
         <td><p>PrintableString 1..40</p>         </td>
         <td><p> </p>         </td>
         <td><p>Mandatory if PERSONAL_NAME is used.</p>
<p>Surname address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>GIVENNAME</p>         </td>
         <td><p>PrintableString 1..16</p>         </td>
         <td><p> </p>         </td>
         <td><p>Given name address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>INITIALS</p>         </td>
         <td><p>PrintableString 1..5</p>         </td>
         <td><p> </p>         </td>
         <td><p>Initials address attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>GQ</p>         </td>
         <td><p>PrintableString 1..3</p>         </td>
         <td><p> </p>         </td>
         <td><p>Generation Qualifier address attribute.</p>         </td>
      </tr>
   </tbody>
</table>

#### Notes:

\(1\) All parameters apply to both categories (Local and Remote) unless otherwise stated.

\(2\) Mandatory parameters are indicated by an asterisk (\*) in the PassPort PM GUI.

### String definitions

#### PrintableString:

a-z

A-Z

0-9

Space

( ) + , . / - : = ?

#### IA5-String:

a-z

A-Z

0-9

Space

\] ! " $ % & ' ( ) \* + , . / : &lt; = &gt; ? @ \[ \_ \` { | } ~ ^ # ; \\ -

Related topics

[About X.400](../)

[X.400 connector](../x400_connector)

[Configuring Gateway for X.400](../x400_configuring)

[Working with X.400](../x400_working_with)

[X.400 O/R Address](../../../configuration_start_here/config_protocols_about/x400_or_address)

 

More information

For full details about partner management with PassPort PM, refer to the PassPort PM documentation.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
