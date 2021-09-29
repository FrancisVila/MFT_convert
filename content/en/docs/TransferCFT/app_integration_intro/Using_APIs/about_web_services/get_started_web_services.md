{
    "title": "Get started with Web services",
    "linkTitle": "Get started with Web services",
    "weight": "330"
}# Get started with Web services



This section describes how to get started using Web services with <span>Transfer CFT</span>. You can use a tool such as SoapUI to create and test SOAP requests. A typical usage for Web services when running Transfer CFT is:



-   To use web services to submit a high number of transfer requests.

-   To trace exchanges using the transfer requests' IDT and IDTU.



When using Web services with <span>Transfer CFT</span>, select the type media communication type, either COM FILE or COM TCP, to use for transfer requests (SEND/RECV), or administration services (such as HALT). If you are using Web services with TCP as the selected COM media type, refer to [About synchronous communication](../../appl_integration/synch_comm_tcpip_intro.htm) for information on configuring the client.



## Prerequisites



You require a tool for developing Web services requests, such as SoapUI.



-   SoapUI information: [www.soapui.org/about-soapui/what-is-soapui-.html](http://www.soapui.org/about-soapui/what-is-soapui-.html)

-   SoapUI download: [www.soapui.org/downloads/latest-release.html](http://www.soapui.org/downloads/latest-release.html)



## View available operations



You can access a full list of available operations at: &lt;Transfer\_CFT\_install\_dir&gt;\\home\\distrib\\copilot\\wsdl\\doc\\index.html



## Select communication media



Regardless of the mode you select, COM FILE or [COM TCP](../../appl_integration/synch_comm_tcpip_intro.htm), the service is the same; the only difference in comportment is the performance and error management (including transfer tracking).



### COM FILE



-   Pros: There is no effect on persistence; if <span>Transfer CFT</span> stops the request is stored in the COM file. Additionally, there is no need to implement error handling on the client side except if the communication file is full (see Note below).

-   Cons: The performance response time per request is at the very least <span>copilot.cft.timerwaitcftcata</span> seconds, where the maximum time could be <span>copilot.cft.timerwaitcftcata</span> multiplied by the `copilot.cft.nbwaitcftcata` value.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If Transfer CFT is not started the transfer requests accumulate in the communication file. However the communication file size is limited. If the com file is full, requests fail leading to an error <span>&lt;RETURN_MESSAGE&gt;ERROR : mediacom is full (-411/0). CSCcom()&lt;/RETURN_MESSAGE&gt;</span>.</td>
</tr>
</tbody>
</table>



### COM TCP



-   Pros: Performance is improved due to a faster request response time (under ideal conditions less than 1 second, however the actual time depends on the Transfer CFT process load, as opposed to <span>copilot.cft.timerwaitcftcata</span> seconds at the very least if you are using COM FILE).

-   Cons: There is an effect on persistence - if <span>Transfer CFT</span> stops the request is not recorded. Additionally, error handling must be implemented on the client.



## Customize the Transfer CFT COM configuration



According to the mode you select, FILE or TCP, you can modify the following parameters in the unified configuration to optimize performance and tracking.



### COM FILE



When using COM FILE the two relevant parameters to consider are `copilot.cft.timerwaitcftcata` and `copilot.cft.nbwaitcftcata`. If you use the default values of 5 and 6 respectively, the minimum wait time is 5 seconds and the maximum wait time for each request is 30 seconds (5 x 6).



Concerning errors when using COM TCP mode, if CFTMAIN stops the connection is lost on the server side and there is no retry. The client then receives an error code 7 with the message " ERROR: Open channel failed (-6006/0)".



### COM TCP or COM FILE



When using either COM FILE or COM TCP, the <span>copilot.misc.maxnbprocess</span> defines the maximum number of parallel sessions accepted by the Transfer CFT Copilot server (default is 20). You can modify this value in function with the peaks in parallel requests your system experiences (maximum is 64), however consider the impact of having a high number of parallel processes. Lastly note that each process treats only one application at a time.



Any requests that exceed the limit cause a network error with either a " connection refused" or "connection closed by remote" type of error.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In multi-node/multi-host on a Transfer CFT Copilot server, the maximum number of parallel requests is <span>copilot.misc.maxnbprocess</span> multiplied by n (where n is the number of hosts).</td>
</tr>
</tbody>
</table>



## Create a request



The following procedure is based on using the SoapUI tool. The exact steps may vary depending on the Web services tool you use.



1.  Start SoapUI.

2.  From the File menu, select New SOAP Project to create a project:

    -   Project Name: Transfer\_CFT

    -   Initial WSDL: &lt;CFTINSTALLDIR&gt;\\home\\distrib\\copilot\\wsdl\\copilotcft.wsdl

3.  Select and expand the service to use, for example:

    -   XFER\_CMD\_SEND\_FILE to send a file, or

    -   XFER\_CAT\_SELECT to monitor a transfer request

4.  Enter the Copilot server URL in the request window: &lt;host&gt;:&lt;copilot server port&gt;

5.  Modify the request as needed. See also:

    -   [Perform a send file request](example_send_request.htm)

    -   [Perform a catalog search request](example_search_catalog.htm)

6.  Submit the request.

7.  Check the result. See [successful or unsuccessful responses.](example_send_request.htm)



## Return codes



When using Web services the return codes are as follows:



<table data-cellspacing="0">
<thead>
<tr>
<th>Name</th>
<th>Description</th>
<th><p>XTS </p>
<p>mapping</p></th>
</tr>
</thead>
<tbody>
<tr>
<td>RCVA_RESPONSE_NOK_VALUE_ERROR</td>
<td>Value error</td>
<td>10</td>
</tr>
<tr>
<td>RCVA_RESPONSE_NOK_NOT_FOUND</td>
<td>Not found</td>
<td>11</td>
</tr>
<tr>
<td>RCVA_PASSPORT_ERROR</td>
<td>Passport AM interrogation error</td>
<td>12</td>
</tr>
<tr>
<td>RCVA_RESPONSE_OK</td>
<td>Ok</td>
<td>3</td>
</tr>
<tr>
<td>RCVA_RESPONSE_OK_POSTED</td>
<td>Inquiry filed</td>
<td>4</td>
</tr>
<tr>
<td>RCVA_RESPONSE_OK_EXECUTED</td>
<td>Inquiry executed</td>
<td>5</td>
</tr>
<tr>
<td>RCVA_RESPONSE_NOK</td>
<td>Error</td>
<td>6</td>
</tr>
<tr>
<td>RCVA_RESPONSE_NOK_IO_ERROR</td>
<td>Error when opening, writing, reading, or closing</td>
<td>7</td>
</tr>
<tr>
<td>RCVA_RESPONSE_NOK_MEMORY_ERROR</td>
<td>Memory error</td>
<td>8</td>
</tr>
<tr>
<td>RCVA_RESPONSE_NOK_PARAMETER_ERROR</td>
<td>Parameter error</td>
<td>9</td>
</tr>
</tbody>
</table>



Related topics



[About Web services](about_web_services.htm)

