{
    "title": "Example send file request",
    "linkTitle": "Example send file request",
    "weight": "340"
}# Example send file transfer request



This section describes how to execute a SEND transfer request using Web services. After submitting a request you can retrieve transfer processing information in the <span>Transfer CFT</span> catalog using a [Web services catalog search request](example_search_catalog.htm). Responses to SEND requests may differ depending on the type of COM media file that you are using (File or TCP).



## XFER\_CMD\_SEND\_FILE request



This example request uses only the minimal number of options needed to submit the SEND file SOAP request. You can modify as needed.



&lt;soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:axw="http://www.axway.com"&gt;



&lt;soapenv:Header&gt;



&gt; &lt;axw:ClientAuth&gt;



&gt; &gt; &lt;axw:user encoding="base64"&gt;user1&lt;/axw:user&gt;



&gt; &gt; &lt;axw:password encoding="base64"&gt;user1password&lt;/axw:password&gt;



&gt; &lt;/axw:ClientAuth&gt;



&lt;/soapenv:Header&gt;



&lt;soapenv:Body&gt;



&gt; &gt; &lt;axw:XFER\_CMD\_SEND\_FILE &gt;

&gt;

&gt; &gt; &lt;axw:IDF&gt;TEST&lt;/axw:IDF&gt;

&gt; &gt;

&gt; &gt; &lt;axw:FNAME&gt;FiletoTransfer.txt&lt;/axw:FNAME&gt;

&gt;

&gt; &gt; &lt;axw:PARTID&gt;PARIS&lt;/axw:PARTID&gt;

&gt;

&gt; &gt; &lt;/axw:XFER\_CMD\_SEND\_FILE&gt;



&lt;/soapenv:Body&gt;



&lt;/soapenv:Envelope&gt;



## Successful response



In the following successful response, you can see that the IDTU value CAT\_IDTU is returned. While the IDTU value CAT\_IDTU indicates that the request is correctly delivered to <span>Transfer CFT</span>, you do not know the transfer status. To obtain the transfer status, see the section describing how to use the [XFER\_CAT\_SELECT](example_search_catalog.htm) function to view the catalog.



&lt;soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"&gt;



&lt;soap:Body&gt;



&gt; &lt;XFER\_CMD\_SEND\_FILEResponse &gt;

&gt;

&gt; &gt; &lt;CAT\_IDTU&gt;A000002M&lt;/CAT\_IDTU&gt;

&gt; &gt;

&gt; &gt; &lt;RETURN\_CODE&gt;3&lt;/RETURN\_CODE&gt;

&gt; &gt;

&gt; &gt; &lt;RETURN\_MESSAGE/&gt;

&gt;

&gt; &lt;/XFER\_CMD\_SEND\_FILEResponse&gt;



&lt;/soap:Body&gt;



&lt;/soap:Envelope&gt;



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The values displayed are example values and yours results may differ.</td>
</tr>
</tbody>
</table>



## Unsuccessful response



The request response differs depending on if Transfer CFT is running, and if the Transfer CFT Copilot server is started, as described in the following sections.



### <span>Transfer CFT</span> is down



An error message (unsuccessful response) is displayed if Copilot is running, but <span>Transfer CFT</span> is down. The following two examples demonstrate the different responses depending on the COM media type being used.



#### Using the TCP media type



If Transfer CFT is not started and you are using TCP, an error message is displayed.



&lt;soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"&gt;



&gt; &lt;soap:Body&gt;

&gt;

&gt; &lt;XFER\_CMD\_SEND\_FILEResponse xmlns="http://www.axway.com"&gt;

&gt;

&gt; &gt; &lt;RETURN\_CODE&gt;7&lt;/RETURN\_CODE&gt;

&gt; &gt;

&gt; &gt; &lt;RETURN\_MESSAGE&gt;ERROR : Open channel failed  (-6006/0).

&gt; &gt;

&gt; &gt; CSCcom()&lt;/RETURN\_MESSAGE&gt;

&gt;

&gt; &lt;/XFER\_CMD\_SEND\_FILEResponse&gt;

&gt;

&gt; &lt;/soap:Body&gt;



&lt;/soap:Envelope&gt;



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The return code here is 7, while a successful request would return the value 3.</td>
</tr>
</tbody>
</table>



#### Using the File media type



In this scenario no IDTU value is displayed because the request is not immediately processed by Transfer CFT. Instead the request is temporarily stored in the COM file until Transfer CFT is started.



&lt;soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"&gt;



&gt; &lt;soap:Body&gt;

&gt;

&gt; &lt;XFER\_CMD\_SEND\_FILEResponse xmlns="http://www.axway.com"&gt;

&gt;

&gt; &gt; &lt;RETURN\_CODE&gt;3&lt;/RETURN\_CODE&gt;

&gt; &gt;

&gt; &gt; &lt;RETURN\_MESSAGE/&gt;

&gt;

&gt; &lt;/XFER\_CMD\_SEND\_FILEResponse&gt;

&gt;

&gt; &lt;/soap:Body&gt;



&lt;/soap:Envelope&gt;



### Copilot is down



If Copilot is down you get a "connection refused" type of error, regardless of whether Transfer CFT is running or not.



Related topics



[Get started with Web services](get_started_web_services.htm)

