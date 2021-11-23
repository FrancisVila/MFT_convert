{
    "title": "Synchronous and asynchronous receipts",
    "linkTitle": "Synchronous and asynchronous receipts",
    "weight": "210"
}A synchronous receipt is returned to the sender during the same HTTP session as the sender’s original message. An asynchronous receipt is returned to the sender on a different communication session than the sender’s original message session.

The synchronous receipt is sent as an HTTP response to an HTTP POST or as an HTTPS response to an HTTPS POST. This form of AS2-MDN is called synchronous because the AS2-MDN is returned to the originator of the POST on the same TCP/IP connection.

The asynchronous AS2-MDN is sent on a separate HTTP or HTTPS TCP/IP connection. Logically, the asynchronous AS2- MDN is a response to an AS2 message. However, at the transfer-protocol layer, assuming that no HTTP pipe lining is used, the asynchronous AS2-MDN is delivered on a unique TCP/IP connection, distinct from that used to deliver the original AS2 message. When handling an asynchronous request, the HTTP response MUST be sent back before the MDN is processed and sent on the separate connection.

When an asynchronous AS2-MDN is requested by the sender of an AS2 message, the synchronous HTTP or HTTPS response returned to the sender prior to terminating the connection *must* be a transfer-layer response indicating the success or failure of the data transfer. The format of such a synchronous response *may* be the same as that response returned when no AS2-MDN is requested.

<img src="/Images/SecureTransport/AS2_SyncAndAsyncReceipts.png" class="maxWidth" alt="AS2 receipt" />

AS2 receipt

**Related topics:**

-   [AS2 and application framework: Architecture and workflow](../c_st_as2_application_framework_architecture_workflow)
-   [SecureTransport AS2 server: Setup overview](../c_st_as2_server_setup_overview)
