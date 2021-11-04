{
    "title": "What is a Pluggable Transfer Site",
    "linkTitle": "What is a Pluggable Transfer Site",
    "weight": "80"
}Beginning with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> 5.3.3, the Pluggable Transfer Site Service Provider Interface (SPI) has been exposed to allow developers to implement custom transfer sites for sending and receiving files using <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server-initiated transfers. This capability allows customer specific custom protocols to be implemented and used for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> file transfers.

Generally, a Pluggable Transfer Site is a custom connector that can be plugged into <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and used like a built-in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Transfer Site. The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Pluggable Transfer Site SPI is a set of Java interfaces and services that can be used to create, configure, and register custom protocol connectors to a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server.

When creating a custom connector that can be used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> for transferring files, you should generally perform the following steps:

1.  <a href="../implement_interface" class="MCXref xref">Implement a user interface</a>
2.  <a href="../custom_protocol" class="MCXref xref">Implement a custom protocol connector</a>
3.  <a href="../deploy_connector" class="MCXref xref">Deploy a custom protocol connector</a>

> **Note:**
>
> Take notice of the following Pluggable Transfer Site limitation: the Send To Partner step in Advanced Routing cannot overwrite the upload folder of a Pluggable Transfer Site.

The following sections will guide you through these steps to create and deploy a Custom Connector in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. All you need to implement a Custom Transfer Site is the Pluggable Transfer Site SPI. An example implementation of a custom connector using the FTP protocol will be used to illustrate how to implement a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Pluggable Transfer Site SPI.
