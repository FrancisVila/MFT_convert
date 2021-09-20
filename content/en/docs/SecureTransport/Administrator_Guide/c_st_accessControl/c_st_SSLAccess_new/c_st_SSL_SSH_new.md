{
    "title": "SSL and SSH",
    "linkTitle": "SSL and SSH",
    "weight": "210"
}SSH provides mutual authentication. The client authenticates the server and the server authenticates the client. The data transferred between the client and server is encrypted.

For SSH server authentication, a key is assigned to the SSH server. As part of the connection handshake, the SSH client verifies the server key by checking whether the user has successfully connected to the server in the past. If a user is connecting to the server for the first time, the SSH client asks the user to confirm that the SSH server key and accept it before connecting to the server.

Generally, the SSH protocol provides three methods of authenticating clients: keyboard-interactive authentication, password authentication, and public key authentication. All types of client authentication are supported by SecureTransport.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">SSH authentication is based on the public key, while SSL authentication is based on certificates. A certificate includes a public key, but it also includes information about the entity to which the key belongs.         </td>
      </tr>
</table>

In SecureTransport, keys are always managed in the form of certificates. Server keys are associated with Local Certificates. For details, see [Manage local certificates and certificate signing requests](../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs).

You can assign a local server certificate to the SSH server. The key contained in the certificate is used to establish the SSH connection. Similarly SSH client keys are associated with login certificates. For details, see [Certificate types](../../../c_st_setup/c_st_certificates/r_st_certificate_types).

The Secure Socket Layer configuration includes an option to control the use of client certificates in SSL. This option also applies to the use of SSH client keys as described in [Manage SSL access](../t_st_sslaccess_new).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If <span>SecureTransport</span> is deployed with <span>SecureTransport</span> Edge Server installed in a peripheral network (DMZ), you must configure the SSL access control settings on both the <span>SecureTransport</span> Edge and the <span>SecureTransport</span> Server. The settings can be the same to require the same secure connection for both types of installation or they might differ. For example, HTTP and FTP servers on the <span>SecureTransport</span> Server might be intended for internal use only and be protected by the firewall. In this case, the <span>SecureTransport</span> Server can be set up to not require SSL, depending on the organization’s policy.         </td>
      </tr>
</table>

**Related topic:**

-   [Manage SSL access](../t_st_sslaccess_new)
