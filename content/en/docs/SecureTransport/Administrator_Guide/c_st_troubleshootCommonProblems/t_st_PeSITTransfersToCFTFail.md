{
    "title": "PeSIT file transfers fail  over TLSv1 Legacy for certain ciphers",
    "linkTitle": "Failed PeSIT file transfers ",
    "weight": "260"
}A change to CBC ciphers in SecureTransport made in response to CVE-2011-3389 causes older version of Transfer CFT and other PeSIT clients to fail to transfer files from and to a {{< SecureTransport/componentshortname  >}} server over TLSv1 Legacy. These clients fail because they do have the update or have other deficiencies in their SSL implementations.

> **Note:**
>
> The following workarounds enable the file transfer between these clients and SecureTransport but both are considered insecure and using any is at your own risk.

## Failed PeSIT file transfers to {{< SecureTransport/componentshortname  >}}

To enable transfer of files to {{< SecureTransport/componentshortname  >}}, disable the fix in {{< SecureTransport/componentshortname  >}} by adding the following Java option in &lt;`FILEDRIVEHOME>/bin/start_pesitd`:

`JAVA_OPTS="-Djsse.enableCBCProtection=false $JAVA_OPTS"`

## Failed PeSIT file transfers from {{< SecureTransport/componentshortname  >}}

To enable {{< SecureTransport/componentshortname  >}} to transfer files to such clients, disable the fix by adding the following Java option in &lt;`FILEDRIVEHOME>/bin/start_tm_console` :

`JAVA_OPTS="-Djsse.enableCBCProtection=false $JAVA_OPTS"`
