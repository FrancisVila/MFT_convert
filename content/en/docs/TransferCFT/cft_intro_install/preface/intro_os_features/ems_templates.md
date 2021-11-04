{
    "title": "Event messages",
    "linkTitle": "Event messages",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> can issue Transfer CFT log messages and account records as Event Messages. A management application can then get these event messages by opening an Event Management System (EMS) distributor process and requesting the messages.

In this chapter, event-message tokens and their values are represented in DDL. For a quick explanation of DDL as it applies to SPI, refer to the *SPI Programming Manual* &gt; *[Summary of DDL for SPI](http://h20565.www2.hpe.com/hpsc/doc/public/display?sp4ts.oid=4201303&docId=emr_na-c02131958&docLocale=en_US)* appendix.

For general information on how an application obtains event messages from a subsystem, refer to the EMS Manual.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>For any HP documentation referenced in this guide, you should check for the most recent version on the HP Support Center.         </td>
      </tr>
   </tbody>
</table>

## Event messages format

<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> Guardian events were also available in the previous 2.3 version, with the main difference being that each <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> process was defined as a sub system. In contrast, <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> version <span class="mc-variable axway_variables.Release_Number variable">3.9</span> only has one defined sub-system.

All messages have the following tokens:

<table>
   <th>
      <tr>
<th>Token         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ZSPI-TKN-SSID         </td>
         <td><p>The Transfer CFT subsystem ID, whose value is XCF2_VAL_EXTERNAL_SSID. This token is described in the SPI Programming Manual.</p>         </td>
      </tr>
      <tr>
         <td>ZEMS-TKN-EVENTNUMBER         </td>
         <td><p>The event number, as described in the EMS Manual. Its value is one of the values described in the table below.</p>         </td>
      </tr>
      <tr>
         <td>XCF2_TKN_SUBJ         </td>
         <td><p>The message subject for which the values are described in the Event messages table below.</p>         </td>
      </tr>
      <tr>
         <td>XCF2_TKN_MSG         </td>
         <td><p>The message text.</p>
<p>For details about Transfer CFT LOG messages, see the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> <span class="mc-variable axway_variables.Release_Number variable">3.9</span>  <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Troubleshooting/Messages_and_Codes/Messages_and_error_codes_Start_here_1.htm">Messages and error codes</a> documentation.</p>
<p>The accounting messages are binary coded data, and are described in the exacct.h header.</p>         </td>
      </tr>
      <tr>
         <td>ZEMS_TKN_EMPHASIS         </td>
         <td>If the value is ZSPI-VAL-TRUE, the event being reported is considered critical. This is the case for ERROR and FATAL log events as well as process errors when using the NonStop mode.         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span>Event messages

The following table shows the relationship between the event, the subject, and the message type.

<table>
   <th>
      <tr>
<th>Event number         </th>
<th>EMS subject         </th>
<th>Event type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>4         </td>
         <td>CFT INFO LOG         </td>
         <td>Log information message         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>CFT WARN LOG         </td>
         <td>Log warning message         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>CFT ERR LOG         </td>
         <td>Log error message         </td>
      </tr>
      <tr>
         <td>7         </td>
         <td>CFT FAIL LOG         </td>
         <td>Log failure message         </td>
      </tr>
      <tr>
         <td>8         </td>
         <td>CFT ACCOUNT         </td>
         <td>Account<span style="color: #000000;"> message</span>         </td>
      </tr>
   </tbody>
</table>

## Activate event log messages

The CFTLOG object defines the Transfer CFT log file declarations. The name of the destination is provided in the fname parameter, which can be:

-   A file: The files are created using a CFTUTIL command, as described in Transfer CFT Environment.
-   Collector: Specifies the name of the collector to which log messages are written.

You can use the NOTIFY parameter of the CFTLOG object to combine the two destinations so that they refer to a Collector.

-   NOTIFY: Name of the collector.
-   OPERMSG: Allows you to filter the type of messages to be sent.
    -   This number is the sum of the values that correspond to the types of messages you want to filter
    -   For example, Operating error messages=16, System error messages=32, Operating fatal error messages=64, System fatal error messages=128 giving a total of 240

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Refer to the Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> <em>Users Guide</em>, available on the <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/AxwayStartPage.htm">documentation portal</a>, for a description of the CFTLOG object parameters.         </td>
      </tr>
   </tbody>
</table>

**Example**

In the Transfer CFT configuration:



    cftlog id        = log0,
    …
    fname= ' log/cftlog',
    afname= ' log/cftalog',
    notify= '$COL',
    opermsg= 240,
    ….
     

## Activate event accounting messages

The CFTACCNT object defines the destinations for the statistical data concerning terminated transfers (accounting messages). The possible destinations provided in the fname parameter are:

-   A file: The files are created using a CFTUTIL command as described in Transfer CFT Environment.
-   Collector: Specifies the name of the collector to which account messages are written.

Once defined, you can activate and link the object to the CFTPARM as shown in the following example.

**Example**



    CFTACCNT ID=ACCNT1, TYPE=FILE, FNAME=$COL,...,MODE=REPLACE
    CFTPARM ID=IDPARM0,...,ACCNT=ACCNT1,MODE=REPLACE

## Transfer CFT EMS

The CFTPLATE file contains the Transfer CFT templates to be concatenated with the system template for an EMS collector.

The XCFTDDL and XCFTEMS files describe the Transfer CFT information and CFT EMS messages in DDL format.
