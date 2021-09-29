{
    "title": "Example catalog search request",
    "linkTitle": "Example catalog search request",
    "weight": "350"
}# Example catalog search request



Use this request to search for information in the catalog, for example details about the status of a transfer request.



## XFER\_CAT\_SELECT request with IDTU



In this example the XFER\_CAT\_SELECT request uses the IDTU.



&lt;SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"&gt;



&gt; &lt;SOAP-ENV:Header&gt;



&gt; &gt; &lt;m:ClientAuth xmlns:m="http://www.axway.com"&gt;

&gt; &gt;

&gt; &gt; &lt;m:user &gt;user1&lt;/m:user&gt;encoding="base64"/&gt;

&gt; &gt;

&gt; &gt; &lt;m:password&gt;user1&lt;/m:password&gt; encoding="base64"/&gt;

&gt; &gt;

&gt; &gt; &lt;/m:ClientAuth&gt;

&gt;

&gt; &lt;/SOAP-ENV:Header&gt;



&gt; &lt;SOAP-ENV:Body&gt;

&gt;

&gt; &gt; &lt;m:XFER\_CAT\_SELECT xmlns:m="http://www.axway.com"&gt;

&gt; &gt;

&gt; &gt; &lt;m:CAT\_FILENAME&gt;$CFTCATA&lt;/m:CAT\_FILENAME&gt;

&gt;

&gt; &lt;m:PERSISTENCE\_LOCALIZATION&gt;PERSISTENCE\_ON\_WORKSTATION&lt;/m:PERSISTENCE\_LOCALIZATION&gt;

&gt;

&gt; &lt;m:PERSISTENCE\_ACCESSIBILITY&gt;PERSISTENCE\_USER\_ALL&lt;/m:PERSISTENCE\_ACCESSIBILITY&gt;

&gt;

&gt; &gt; &lt;m:DIRECT&gt;BOTH&lt;/m:DIRECT&gt;

&gt; &gt;

&gt; &gt; &lt;m:IDTU\_ARRAY&gt;

&gt; &gt;

&gt; &gt; &gt; &lt;m:IDTU&gt;A0000030&lt;/m:IDTU&gt;

&gt; &gt;

&gt; &gt; &lt;/m:IDTU\_ARRAY&gt;

&gt; &gt;

&gt; &gt; &lt;m:CONTENT\_SUBSET&gt;

&gt; &gt;

&gt; &gt; &gt; &lt;m:CAT\_CONTENT&gt;CAT\_BRIEF&lt;/m:CAT\_CONTENT&gt;

&gt; &gt; &gt;

&gt; &gt; &gt; &lt;m:SELECT\_FIELDS\_ARRAY&gt;

&gt; &gt; &gt;

&gt; &gt; &gt; &lt;m:SELECT\_FIELD&gt;String&lt;/m:SELECT\_FIELD&gt;

&gt; &gt;

&gt; &gt; &gt; &lt;/m:SELECT\_FIELDS\_ARRAY&gt;

&gt; &gt;

&gt; &gt; &lt;/m:CONTENT\_SUBSET&gt;

&gt; &gt;

&gt; &gt; &lt;/m:XFER\_CAT\_SELECT&gt;

&gt;

&gt; &lt;/SOAP-ENV:Body&gt;



&lt;/SOAP-ENV:Envelope&gt;



## Successful response



### <span>Transfer CFT</span> is down



Executing the this request when Copilot is running but <span>Transfer CFT</span> is not running returns the same response.



&lt;?xml version="1.0" encoding="UTF-8" standalone="yes"?&gt;



&lt;soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"&gt;



&lt;soap:Body&gt;



&gt; &lt;XFER\_CAT\_SELECTResponse xmlns="http://www.axway.com"&gt;

&gt;

&gt; &lt;CAT\_MAXRECORDS&gt;10000&lt;/CAT\_MAXRECORDS&gt;

&gt;

&gt; &lt;CAT\_CURRENTRECORDS&gt;12&lt;/CAT\_CURRENTRECORDS&gt;

&gt;

&gt; &lt;LISTCAT\_ARRAY&gt;

&gt;

&gt; &lt;LISTCAT\_SUBSET&gt;

&gt;

&gt; &lt;CAT\_FREC&gt;14&lt;/CAT\_FREC&gt;

&gt;

&gt; &lt;CAT\_DIAGI&gt;0&lt;/CAT\_DIAGI&gt;

&gt;

&gt; &lt;CAT\_NREC&gt;14&lt;/CAT\_NREC&gt;

&gt;

&gt; &lt;CAT\_TYPE&gt;FILE&lt;/CAT\_TYPE&gt;

&gt;

&gt; &lt;CAT\_IDA&gt;30080&lt;/CAT\_IDA&gt;

&gt;

&gt; &lt;CAT\_DIAGC/&gt;

&gt;

&gt; &lt;CAT\_IDT&gt;E0314250&lt;/CAT\_IDT&gt;

&gt;

&gt; &lt;CAT\_IDF&gt;TEST&lt;/CAT\_IDF&gt;

&gt;

&gt; &lt;CAT\_DIAGP&gt;CP NONE&lt;/CAT\_DIAGP&gt;

&gt;

&gt; &lt;CAT\_PART&gt;LOOP&lt;/CAT\_PART&gt;

&gt;

&gt; &lt;CAT\_STATE&gt;CAT\_STATE\_CONSUMED&lt;/CAT\_STATE&gt;

&gt;

&gt; &lt;CAT\_ACK&gt;false&lt;/CAT\_ACK&gt;

&gt;

&gt; &lt;CAT\_NACK&gt;false&lt;/CAT\_NACK&gt;

&gt;

&gt; &lt;CAT\_CFTSTATE&gt;X&lt;/CAT\_CFTSTATE&gt;

&gt;

&gt; &lt;CAT\_DIRECT&gt;SEND&lt;/CAT\_DIRECT&gt;

&gt;

&gt; &lt;/LISTCAT\_SUBSET&gt;

&gt;

&gt; &lt;/LISTCAT\_ARRAY&gt;

&gt;

&gt; &lt;RETURN\_CODE&gt;3&lt;/RETURN\_CODE&gt;

&gt;

&gt; &lt;RETURN\_MESSAGE/&gt;

&gt;

&gt; &lt;/XFER\_CAT\_SELECTResponse&gt;



&gt; &lt;/soap:Body&gt;



&lt;/soap:Envelope&gt;



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To retrieve the Phase, Phasestep and  Appstate statuses you can set the CAT_CONTENT value to FULL. However, setting the catalog to FULL returns a large number of lines in the catalog.</td>
</tr>
</tbody>
</table>



&gt; &lt;CAT\_PHASE&gt;X&lt;/CAT\_PHASE&gt;

&gt;

&gt; &lt;CAT\_PHASESTEP&gt;X&lt;/CAT\_PHASESTEP&gt;

&gt;

&gt; &lt;CAT\_APPSTATE/&gt;



## Response when there is no IDTU



In the following response the return code is 3, successful, but the LISCAT\_ARRAY is empty.



&lt;soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"&gt;



&gt; &lt;soap:Body&gt;

&gt;

&gt; &gt; &lt;XFER\_CAT\_SELECTResponse xmlns="http://www.axway.com"&gt;

&gt; &gt;

&gt; &gt; &gt; &lt;CAT\_MAXRECORDS&gt;10000&lt;/CAT\_MAXRECORDS&gt;

&gt; &gt; &gt;

&gt; &gt; &gt; &lt;CAT\_CURRENTRECORDS&gt;12&lt;/CAT\_CURRENTRECORDS&gt;

&gt; &gt; &gt;

&gt; &gt; &gt; &lt;LISTCAT\_ARRAY/&gt;

&gt; &gt; &gt;

&gt; &gt; &gt; &lt;RETURN\_CODE&gt;3&lt;/RETURN\_CODE&gt;

&gt; &gt; &gt;

&gt; &gt; &gt; &lt;RETURN\_MESSAGE/&gt;

&gt; &gt;

&gt; &gt; &lt;/XFER\_CAT\_SELECTResponse&gt;

&gt;

&gt; &lt;/soap:Body&gt;



&lt;/soap:Envelope&gt;



## Unsuccessful response



### Copilot is down



The exact message text may vary depending on the selected COM media type (File or TCP).



Related topics



[Get started with Web services](get_started_web_services.htm)

