{
    "title": "SIT transfers fail when using DSA certificates",
    "linkTitle": "SIT transfers fail when using DSA certificates",
    "weight": "280"
}Server-initiated transfers might fail if specific DSA certificates are used by the remote server. To prevent this issue, add the following Java option in &lt;`FILEDRIVEHOME>/bin/start_tm_console`:

`-Dorg.bouncycastle.jsse.client.dh.unrestrictedGroups=true`

Save your change and restart the TM Server.
