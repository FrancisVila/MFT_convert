{
    "title": "Secret file",
    "linkTitle": "Secret file",
    "weight": "80"
}The secret file (also called `taeh` file) contains randomly-generated data used by the SecureTransport system for encryption. It must be the same for all SecureTransport Servers or SecureTransport Edges in a cluster.

The installer creates the secret file (named `taeh`) when you install a stand-alone server or the first SecureTransport Server in a cluster. It is stored in the `<FILEDRIVEHOME>/bin/taeh` directory, where `<FILEDRIVEHOME>` is the directory where SecureTransport is installed.

For the second and subsequent servers of the cluster, you must copy the `taeh` file from the first cluster node before you install SecureTransport. Make sure the name of the secret file does not contain any special characters or spaces. Then you import the secret file during server installation. After you configure the server, you cannot change the `taeh` file. Changing the secret file after the server is configured may corrupt certain encrypted configuration elements (local certificates, passwords, and so forth).

When you install SecureTransport on a second node in a cluster using an appliance, you are prompted for the remote server credentials and location of the secret file. The other server must be an appliance with SecureTransport installed and an OS-level SSH daemon running.

For details, see [General prerequisites](general_prerequisites.htm#installation_3205816781_1041633).
