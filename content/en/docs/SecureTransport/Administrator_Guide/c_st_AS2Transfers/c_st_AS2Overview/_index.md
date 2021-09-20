{
    "title": "AS2 implementation",
    "linkTitle": "AS2 implementation",
    "weight": "200"
}Companies that conduct Business-to-Business (**B2B**) Electronic Commerce can use SecureTransport Server to send business documents to their business partners using the AS2 protocol.

The SecureTransport AS2 server provides security by utilizing encryption and signing. The server sends a document that is signed and encrypted to the partner using digital certificates that are agreed upon between the server and the target partner.

The partner checks the signature of the document and sends a signed MDN receipt to acknowledge that the transfer succeeded. MDN is an Internet messaging format used to transmit a receipt. MDN is used interchangeably with receipt. MDN is a receipt. This MDN signature is used to prove that the original document was sent from the SecureTransport AS2 server to the partner in a process called non-repudiation.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The use of signing, encryption, and MDN receipts are optional AS2 features that are decided when businesses enter into a partnership.         </td>
      </tr>
</table>

The following topics describe the SecureTransport AS2 implementation:

-   [Synchronous and asynchronous receipts](c_st_synchronous_asynchronous_receipts) - Describes synchronous and asynchronous receipts.
-   [AS2 and application framework: Architecture and workflow](c_st_as2_application_framework_architecture_workflow) - Describes the architecture and workflow of AS2 and the application framework.
-   [SecureTransport AS2 server: Setup overview](c_st_as2_server_setup_overview) - Provides an overview of the SecureTransport AS2 server setup.