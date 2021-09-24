{
    "title": "Transfer serialization",
    "linkTitle": "Transfer serialization",
    "weight": "220"
}Business users today expect that applications can transfer files sequentially. Additionally, when sending files sequentially (first in/first out), users may want to define a processing phase that the transfer must reach before Transfer CFT begins executing the next transfer. This process in Transfer CFT is known as transfer serialization.

On the sender side, the next file cannot be sent until the previously sent file is written on the disk by the receiving Transfer CFT, and a certain phase reached, for example the post-processing is executed. Once this occurs, the sending Transfer CFT can then send the next file.

Serialization of transfer requests is based on a combination of the request's IDF and PART values. Therefore, if either of these values varies, the IDF or PART, then the request does not belong to the same serialization list.

Additional serialization rules:

-   Un-serialized transfers do not have an impact on serialized transfers.
-   Serialization takes priority over the [MINDATE](../../c_intro_userinterfaces/command_summary/parameter_intro/mindate)/[MINTIME](../../c_intro_userinterfaces/command_summary/parameter_intro/mintime) parameters.
-   A failed transfer blocks following transfers.
-   Deleting a transfer in the catalog triggers the next waiting transfer in the list.

## <span id="Using"></span>Using serialization

Serialization is supported in REQUESTER mode for send and receive operations except for cyclic requests and RECV file=all.

### Procedure

Use the [serial](../../c_intro_userinterfaces/command_summary/parameter_intro/serial) parameter based on the following examples.

**Example 1**

This example demonstrates 3 waiting transfer requests, which execute sequentially regardless of the configuration or available resources. The first transfer recorded in the catalog is the first to execute, in this example transfer A.

The DONE (X) phase is reached when the post-processing has completed, or once the transfer is finished if no post-processing exists.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>SEND PART=PARIS, IDF=BIN, SERIAL=X, IDA=A</p>
            <p>SEND PART=PARIS, IDF=BIN, SERIAL=X, IDA=B</p>
            <p>SEND PART=PARIS, IDF=BIN, SERIAL=X, IDA=C</p>
            <p> </p>
            <p><strong>Results</strong> </p>
            <p>CFTT57I Requester transfer started   &lt;IDTU=&lt;transfer A&gt; PART=PARIS IDF=BIN </p>
            <p>CFTT58I Requester transfer ended     &lt;IDTU=&lt;transfer A&gt; PART=PARIS IDF=BIN </p>
            <p> CFTR12I END Treated for USER &lt;my user&gt; &lt;PART=PARIS IDF=BIN  &gt;</p>
            <p> </p>
            <p>CFTT57I Requester transfer started   &lt;IDTU=&lt;transfer B&gt; PART=PARIS IDF=BIN </p>
            <p>CFTT58I Requester transfer ended     &lt;IDTU=&lt;transfer B&gt; PART=PARIS IDF=B </p>
            <p> CFTR12I END Treated for USER &lt;my user&gt; &lt;PART=PARIS IDF=BIN  &gt;</p>
            <p> </p>
            <p>CFTT57I Requester transfer started   &lt;IDTU=&lt;transfer C&gt; PART=PARIS IDF=BIN </p>
            <p>CFTT58I Requester transfer ended     &lt;IDTU=  &lt;transfer C&gt; PART=PARIS IDF=BIN</p>
            <p> CFTR12I END Treated for USER &lt;my user&gt; &lt;PART=PARIS IDF=BIN  &gt;</p>
         </td>
      </tr>
   </tbody>
</table>

**Example 2**

In this example, a serialized transfer can start as soon as the post-processing of the preceding transfer begins, as opposed to waiting for it to complete as in Example 1.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>SEND PART=PARIS, IDF=BIN, SERIAL=Y, IDA=A</p>
            <p>SEND PART=PARIS, IDF=BIN, SERIAL=Y, IDA=B</p>
            <p>SEND PART=PARIS, IDF=BIN, SERIAL=Y, IDA=C</p>
            <p> </p>
            <p><strong>Results</strong> </p>
            <p>CFTT57I Requester transfer started   &lt;IDTU=&lt;transfer A&gt; PART=PARIS IDF=BIN </p>
            <p>CFTT58I Requester transfer ended     &lt;IDTU=&lt;transfer A&gt; PART=PARIS IDF=BIN </p>
            <p> </p>
            <p>CFTT57I Requester transfer started   &lt;IDTU=&lt;transfer B&gt; PART=PARIS IDF=BIN </p>
            <p> CFTR12I END [for transfer A] Treated for USER &lt;my user&gt; &lt;PART=PARIS IDF=BIN  &gt;</p>
            <p>CFTT58I Requester transfer ended     &lt;IDTU=&lt;transfer B&gt; PART=PARIS IDF=B </p>
            <p> </p>
            <p>CFTT57I Requester transfer started   &lt;IDTU=&lt;transfer C&gt; PART=PARIS IDF=BIN </p>
            <p> CFTR12I END [for transfer B] Treated for USER &lt;my user&gt; &lt;PART=PARIS IDF=BIN  &gt;</p>
            <p>CFTT58I Requester transfer ended     &lt;IDTU=  &lt;transfer C&gt; PART=PARIS IDF=BIN</p>
            <p> </p>
            <p> CFTR12I END [for transfer C] Treated for USER &lt;my user&gt; &lt;PART=PARIS IDF=BIN  &gt;</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">SEND requests are not serialized with RECV request. Send and receive procedures can have two different values for the SERIAL parameter.         </td>
      </tr>
</table>

**<span id="Example_3"></span>Example 3**

In this example, serialized transfers between a Transfer CFT and a remote PeSIT application must be acknowledged in order to reach the DONE (X) phase.

-   The first transfer recorded in the catalog executes first, in this example transfer A.
-   The DONE (X) phase is reached once transfer A is acknowledged.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>SEND PART=RS43, IDF=BIN, SERIAL=X, IDA=A, ACKSTATE=REQUIRE</p>
            <p>SEND PART=RS43, IDF=BIN, SERIAL=X, IDA=B, ACKSTATE=REQUIRE</p>
            <p>SEND PART=RS43, IDF=BIN, SERIAL=X, IDA=C, ACKSTATE=REQUIRE</p>
            <p> </p>
            <p><strong>Results</strong>
</p>
            <p>CFTT57I Requester transfer started &lt;IDTU=&lt;transfer A&gt; PART=RS43 IDF=BIN</p>
            <p>CFTT58I Requester transfer ended &lt;IDTU=&lt;transfer A&gt; PART=RS43 IDF=BIN</p>
            <p>CFTT59I Server    reply    transferred &lt;IDT=&lt;IDT transfer A&gt; PART=RS43 IDM=BIN</p>
            <p> </p>
            <p>CFTT57I Requester transfer started &lt;IDTU=&lt;transfer B&gt; PART=RS43 IDF=BIN</p>
            <p>CFTT58I Requester transfer ended &lt;IDTU=&lt;transfer B&gt; PART=RS43 IDF=B</p>
            <p>CFTT59I Server    reply    transferred &lt;IDT=&lt;IDT transfer B&gt; PART=RS43 IDM=BIN</p>
            <p> </p>
            <p>CFTT57I Requester transfer started &lt;IDTU=&lt;transfer C&gt; PART=RS43 IDF=BIN</p>
            <p>CFTT58I Requester transfer ended &lt;IDTU= &lt;transfer C&gt; PART=RS43 IDF=BIN</p>
            <p>CFTT59I Server    reply    transferred &lt;IDT=&lt;IDT transfer C&gt; PART=RS43 IDM=BIN</p>
         </td>
      </tr>
   </tbody>
</table>

### Using serialization in multi-node architecture

Serialization works in a multi-node environment only if the Communication Media File dispatching policy is partner aligned. To do this, set the uconf parameter `cft.multi_node.cftcom.dispatcher_policy` to` node_affinity`. and set `state=HOLD` when you execute transfer commands.
