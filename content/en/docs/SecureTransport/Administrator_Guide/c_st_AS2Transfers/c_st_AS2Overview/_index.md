{
    "title": "AS2 implementation ",
    "linkTitle": "AS2 implementation",
    "weight": "190"
}Companies that conduct Business-to-Business (**B2B**) Electronic Commerce can use <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to send business documents to their business partners using the AS2 protocol.

The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> AS2 server provides security by utilizing encryption and signing. The server sends a document that is signed and encrypted to the partner using digital certificates that are agreed upon between the server and the target partner.

The partner checks the signature of the document and sends a signed MDN receipt to acknowledge that the transfer succeeded. MDN is an Internet messaging format used to transmit a receipt. MDN is used interchangeably with receipt. MDN is a receipt. This MDN signature is used to prove that the original document was sent from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> AS2 server to the partner in a process called non-repudiation.

> **Note:**
>
> The use of signing, encryption, and MDN receipts are optional AS2 features that are decided when businesses enter into a partnership.

The following topics describe the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> AS2 implementation:

-   <a href="c_st_synchronous_asynchronous_receipts" class="MCXref xref">Synchronous and asynchronous receipts</a> - Describes synchronous and asynchronous receipts.
-   <a href="c_st_as2_application_framework_architecture_workflow" class="MCXref xref">AS2 and application framework: Architecture and workflow</a> - Describes the architecture and workflow of AS2 and the application framework.
-   <a href="c_st_as2_server_setup_overview" class="MCXref xref">SecureTransport AS2 server: Setup overview</a> - Provides an overview of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> AS2 server setup.
