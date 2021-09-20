{
    "title": "Setup steps",
    "linkTitle": "Setup steps",
    "weight": "90"
}Before executing the setup steps, log into the Setup Administrator account. The Setup Administrator account is used for the initial, one-time configuration of the system.

There are seven steps involved in configuring SecureTransport for initial use. Complete the steps in the order listed to prevent conflicts.

1.  **Install Licenses** – Install the core and feature licenses. This is the only step you perform on the second and subsequent servers in an Enterprise Cluster.
2.  **Keystore Password** – Replace the default keystore password with one you create.
3.  **Generate CA** – Regenerate the Internal CA used to sign other certificates.  
    Alternately, you can import a CA certificate.
4.  **Generate Certificates** – Generate certificates for each protocol server you are using, FTP, HTTP, etc.  
    You can import server certificates. The certificates can be signed by any trusted authority.
5.  **Database Settings** - Select the internal database port and configure the internal database password or setup an external database.
6.  **Set Up Servers**– Set up the HTTP, FTP, SSH, AS2, and PeSIT protocol servers, the Transaction Manager (TM) server, and the Database server.  
    The SecureTransport Edge server also supports a proxy (SOCKS) setup.
7.  **Exchange Certificates** – Export and import CAs from SecureTransport Servers and SecureTransport Edge servers.
