{
    "title": "SecureTransport Server",
    "linkTitle": "SecureTransport Server",
    "weight": "60"
}{{< SecureTransport/componentshortname  >}} Server provides a centrally managed system for monitoring and managing secure file transfer activity across multiple file transfer sites or applications. Key capabilities of the {{< SecureTransport/componentshortname  >}} Server include:

-   **Guaranteed delivery** – Guarantees secure, reliable, and scalable file transfer service even over unstable network connections or dial-up lines using integrity checking implemented with a cryptographic hash algorithm and provides powerful automation to integrate with back-end systems
-   **Checkpoint restart** – With {{< SecureTransport/companyname >}} clients, allows restarting stopped or failed HTTP, PeSIT, and some FTP file transfers from the point of failure
-   **Secure connectivity** – Accepts, validates, and secures incoming connections and file transfers
-   **Multi-protocol support** – Executes file transfers using widely adopted open standard FTP, secure FTP, HTTP, HTTP(S), AS2, PeSIT, SSH-based (SFTP and SCP), and Folder Monitor protocols
-   **Proxy support** – Can use the SOCKS5 proxy provided by {{< SecureTransport/componentshortname >}} Edge or an HTTP proxy
-   **Native {{< SecureTransport/companyname >}} File Bus support** – Supports PeSIT for connectivity with the {{< SecureTransport/companyname >}} File Bus and implements the {{< SecureTransport/companyname >}} File Bus using metadata, routing, and automation capabilities aligned with {{< SecureTransport/companyname >}} Transfer CFT
-   **Ad hoc file transfer support** – Manages human-to-human (H2H) and human-to-system (H2S) file transfers sent using ST Web Client or one of the {{< SecureTransport/companyname >}} Email Plug-ins and system-to-human (S2H) file transfers delivered through email notifications
-   **Repository encryption** – Encrypts all files on disk at the server transparently
-   **PGP encryption** – Handles PGP encryption and decryption, the generation and storing of PGP keys, and the management of the stored keys
-   **Application integration** – Includes REST and Java APIs, protocols, a file services interface, and {{< SecureTransport/companyname >}} File Bus support
-   **Transfer scheduling** – Allows administrators to plan and configure scheduled file transfers and AdHoc tasks
-   **Monitoring and reporting** – Monitors and analyzes file transfer activity, providing real-time reports and alerts
-   **Signed messaging disposition notification (MDN) receipts** – Can generate receipts for all transfers, regardless of protocol
-   **Flexible clustering models** - Includes Standard Clustering for simple deployment with no external dependencies and optional Enterprise Clustering to increase the capacity of a {{< SecureTransport/componentshortname >}} deployment to handle large workloads
-   **Database support** – Uses an embedded database or, with optional Enterprise Clustering, an external database to store and retrieve configuration parameters and data pertaining to objects and events
-   **Web administration and configuration** – Provides a web-based user interface (the Administration Tool) for centralized administration, configuration, and monitoring of file transfer activity and applications
-   **Fully Embeddable** – Includes a REST API with resources for administration, configuration, and file transfer request management and for creating custom end user access

{{< SecureTransport/componentshortname  >}} Server is available as software on Windows and UNIX platforms and as a Cloud service. You can deploy it as part of an Enterprise Cluster or as a stand-alone server.
