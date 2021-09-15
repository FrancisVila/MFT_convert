{
    "title": "Failed PeSIT file transfers ",
    "linkTitle": "Failed PeSIT file transfers ",
    "weight": "270"
}A change to CBC ciphers in SecureTransport made in response to CVE-2011-3389 causes older version of Transfer CFT and other PeSIT clients to fail to transfer files from and to a SecureTransport server over TLSv1 Legacy. These clients fail because they do have the update or have other deficiencies in their SSL implementations.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The following workarounds enable the file transfer between these clients and <span>SecureTransport</span> but both are considered insecure and using any is at your own risk.         </td>
      </tr>
</table>

## Failed PeSIT file transfers to SecureTransport

To enable transfer of files to SecureTransport, disable the fix in SecureTransport by adding the following Java option in &lt;`FILEDRIVEHOME>/bin/start_pesitd`:

`JAVA_OPTS="-Djsse.enableCBCProtection=false $JAVA_OPTS"`

## Failed PeSIT file transfers from SecureTransport

To enable SecureTransport to transfer files to such clients, disable the fix by adding the following Java option in &lt;`FILEDRIVEHOME>/bin/start_tm_console` :

`JAVA_OPTS="-Djsse.enableCBCProtection=false $JAVA_OPTS"`
