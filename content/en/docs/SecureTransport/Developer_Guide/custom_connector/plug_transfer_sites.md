{
    "title": "What is a Pluggable Transfer Site",
    "linkTitle": "What is a Pluggable Transfer Site",
    "weight": "80"
}Beginning with {{< SecureTransport/componentshortname  >}} 5.3.3, the Pluggable Transfer Site Service Provider Interface (SPI) has been exposed to allow developers to implement custom transfer sites for sending and receiving files using {{< SecureTransport/componentshortname  >}} server-initiated transfers. This capability allows customer specific custom protocols to be implemented and used for {{< SecureTransport/componentshortname  >}} file transfers.

Generally, a Pluggable Transfer Site is a custom connector that can be plugged into {{< SecureTransport/componentshortname  >}} Server and used like a built-in {{< SecureTransport/componentshortname  >}} Transfer Site. The {{< SecureTransport/componentshortname  >}} Pluggable Transfer Site SPI is a set of Java interfaces and services that can be used to create, configure, and register custom protocol connectors to a {{< SecureTransport/componentshortname  >}} Server.

When creating a custom connector that can be used by {{< SecureTransport/componentshortname  >}} for transferring files, you should generally perform the following steps:

1.  [Implement a user interface](../implement_interface)
2.  [Implement a custom protocol connector](../custom_protocol)
3.  [Deploy a custom protocol connector](../deploy_connector)

> **Note:**
>
> Take notice of the following Pluggable Transfer Site limitation: the Send To Partner step in Advanced Routing cannot overwrite the upload folder of a Pluggable Transfer Site.

The following sections will guide you through these steps to create and deploy a Custom Connector in {{< SecureTransport/componentshortname  >}} Server. All you need to implement a Custom Transfer Site is the Pluggable Transfer Site SPI. An example implementation of a custom connector using the FTP protocol will be used to illustrate how to implement a {{< SecureTransport/componentshortname  >}} Pluggable Transfer Site SPI.
