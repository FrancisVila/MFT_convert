{
    "title": "What is a Pluggable Transfer Site",
    "linkTitle": "What is a Pluggable Transfer Site",
    "weight": "80"
}Beginning with SecureTransport 5.3.3, the Pluggable Transfer Site Service Provider Interface (SPI) has been exposed to allow developers to implement custom transfer sites for sending and receiving files using SecureTransport server-initiated transfers. This capability allows customer specific custom protocols to be implemented and used for SecureTransport file transfers.

Generally, a Pluggable Transfer Site is a custom connector that can be plugged into SecureTransport Server and used like a built-in SecureTransport Transfer Site. The SecureTransport Pluggable Transfer Site SPI is a set of Java interfaces and services that can be used to create, configure, and register custom protocol connectors to a SecureTransport Server.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The version of the Pluggable Transfer Site SPI described in this <span>SecureTransport</span> Developer's Guide is 1.7.0.         </td>
      </tr>
</table>

When creating a custom connector that can be used by SecureTransport for transferring files, you should generally perform the following steps:

1.  [Implement a user interface](../implement_interface)
2.  [Implement a custom protocol connector](../custom_protocol)
3.  [Deploy a custom protocol connector](../deploy_connector)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Take notice of the following Pluggable Transfer Site <i>limitation</i>: the Send To Partner step in <span>Advanced Routing</span> cannot overwrite the upload folder of a Pluggable Transfer Site.         </td>
      </tr>
</table>

The following sections will guide you through these steps to create and deploy a Custom Connector in SecureTransport Server. All you need to implement a Custom Transfer Site is the Pluggable Transfer Site SPI. An example implementation of a custom connector using the FTP protocol will be used to illustrate how to implement a SecureTransport Pluggable Transfer Site SPI.
