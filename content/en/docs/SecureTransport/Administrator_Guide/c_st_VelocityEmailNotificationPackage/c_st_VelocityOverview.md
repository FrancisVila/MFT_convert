{
    "title": "Velocity overview",
    "linkTitle": "Velocity overview",
    "weight": "320"
}Velocity is an open source template engine provided by the Jakarta Apache Project. It uses the Velocity Template Language (VTL) which provides an easy and simple way to incorporate dynamic content in an HTML email.

VTL uses *references* to embed dynamic content into an HTML email and a variable is one type of reference. This makes it an ideal technology for integrating with the SecureTransport Server SDK as the variables can be mapped to the set of SecureTransport environment variables.

The following HTML code snippet shows a VTL statement that can be embedded in an HTML email notification generated by SecureTransport:

    <tr id="areabody" bgcolor="white">
       <td colspan="2">
          You have received a new File <b>$DXAGENT_TARGET</b> from the 
          Remote Host $DXAGENT_REMOTEHOST
       </td>
    </tr>

When generated, the email notification displays something like the following example:

![File delivery notification](emailnotificationmessage%20example2.png)

For more information, refer to the Apache Velocity Project website.