{
    "title": "SSL and SSH",
    "linkTitle": "SSL and SSH",
    "weight": "200"
}SSH provides mutual authentication. The client authenticates the server and the server authenticates the client. The data transferred between the client and server is encrypted.

For SSH server authentication, a key is assigned to the SSH server. As part of the connection handshake, the SSH client verifies the server key by checking whether the user has successfully connected to the server in the past. If a user is connecting to the server for the first time, the SSH client asks the user to confirm that the SSH server key and accept it before connecting to the server.

Generally, the SSH protocol provides three methods of authenticating clients: keyboard-interactive authentication, password authentication, and public key authentication. All types of client authentication are supported by {{< SecureTransport/componentshortname  >}}.

> **Note:**
>
> SSH authentication is based on the public key, while SSL authentication is based on certificates. A certificate includes a public key, but it also includes information about the entity to which the key belongs.

In {{< SecureTransport/componentshortname  >}}, keys are always managed in the form of certificates. Server keys are associated with Local Certificates. For details, see <a href="../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#top" class="MCXref xref">Manage local certificates and certificate signing requests</a>.

You can assign a local server certificate to the SSH server. The key contained in the certificate is used to establish the SSH connection. Similarly SSH client keys are associated with login certificates. For details, see <a href="../../../c_st_setup/c_st_certificates/r_st_certificate_types#SetupMenu_1217491348_1126501" class="MCXref xref">Certificate types</a>.

The Secure Socket Layer configuration includes an option to control the use of client certificates in SSL. This option also applies to the use of SSH client keys as described in <a href="../t_st_sslaccess_new#Specify" class="MCXref xref">Manage SSL access</a>.

> **Note:**
>
> If SecureTransport is deployed with SecureTransport Edge Server installed in a peripheral network (DMZ), you must configure the SSL access control settings on both the SecureTransport Edge and the SecureTransport Server. The settings can be the same to require the same secure connection for both types of installation or they might differ. For example, HTTP and FTP servers on the SecureTransport Server might be intended for internal use only and be protected by the firewall. In this case, the SecureTransport Server can be set up to not require SSL, depending on the organization’s policy.

**Related topic:**

-   <a href="../t_st_sslaccess_new" class="MCXref xref">Manage SSL access</a>
