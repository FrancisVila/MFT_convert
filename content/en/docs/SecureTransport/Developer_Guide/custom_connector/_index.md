{
    "title": "Transfer sites",
    "linkTitle": "Transfer sites",
    "weight": "50"
}This section describes the capability of {{< SecureTransport/componentshortname  >}} Server to use Pluggable Transfer Sites for executing server-initiated transfers and provides instructions on how to implement and configure a Connector.

During the installation or upgrade of SecureTransport 5.3.3 or later, a dedicated folder is created:

-   `${FILEDRIVE_HOME}/plugins/transferSites`

This folder contains a jar file for each Pluggable Transfer Site that is implemented and configured in SecureTransport. The jar file contains all the information required for the site, including the specific configuration metadata. For additional information, refer to [What is a Pluggable Transfer Site](plug_transfer_sites).
