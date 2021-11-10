{
    "title": "Enable  TLSv1.3 protocol support in SecureTransport",
    "linkTitle": "Enable TLSv1.3 in SecureTransport",
    "weight": "140"
}TLSv1.3 is enabled by default on fresh installations of SecureTransport 5.5-20210930 or later. For upgraded instances, it is disabled by default as TLSv1.3 is not directly compatible with previous versions of the protocol and uses new cipher suites that are not supported by earlier versions of TLS. Therefore, when you enable TLSv1.3 on your instance, you must also add TLSv1.3 cipher suites to the configured list of supported cipher suites for the transfer site and the server listener. If TLSv1.3 and earlier versions are enabled, the configured list of supported cipher suites must include values supported for TLSv1.3 and values supported by earlier TLS versions.

## Enable TLSv1.3

To enable TLSv1.3 in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, add "TLSv1.3" to the following configuration options:

-   `Admin.Ssl.protocol`
-   `As2.SIT.EnabledProtocols`
-   `Cluster.DynamicSync.SSLProtocol, Cluster.Listeners.Ssl.protocol`
-   `Ftp.Listeners.Ssl.enabledProtocols, Ftps.SIT.EnabledProtocols`
-   `Http.Ssl.Protocols, Https.SIT.EnabledProtocols`
-   `Pesit.Listeners.Ssl.enabledProtocols, Pesit.SIT.enabledProtocols`
-   `Streaming.EnabledProtocols`

Add TLSv1.3 cipher suites to the following configuration options. See the list of supported cipher suits [here]().

-   `Admin.EnabledCipherSuites`
-   `As2.FIPS.SIT.Ciphers, As2.Listeners.Ssl.enabledCipherSuites, As2.SIT.Ciphers`
-   ` AxwaySentinel.SecureConnection.EnabledCipherSuites`
-   `Cluster.Listeners.Ssl.enabledCipherSuites`
-   `Ftp.FIPS.Listeners.Ssl.EnabledCipherSuites, Ftp.Listeners.Ssl.enabledCipherSuites, Ftps.FIPS.SIT.Ciphers, Ftps.SIT.Ciphers`
-   `Http.FIPS.Ssl.EnabledCipherSuites, Http.Ssl.EnabledCipherSuites, Https.SIT.Ciphers`
-   `Pesit.FIPS.Listeners.Ssl.EnabledCipherSuites, Pesit.FIPS.SIT.Ciphers, Pesit.Listeners.Ssl.enabledCipherSuites, Pesit.SIT.Ciphers`
-   `Streaming.EnabledCipherSuites`
-   `Tm.CipherSuites`.

## Enable TLSv1.3 for ICAP servers

To enable TLSv1.3 for an ICAP server, navigate to **ICAP server settings** &gt; **Advanced connection settings**. Edit the **Enabled Protocols** field to add `TLSv1.3`. Then, add TLSv1.3 supported values to the configured list of enabled cipher suites.

## Enable TLSv1.3 and FIPS support

To enable TLSv1.3 under FIPS mode, remove it from the `FIPS.DisabledProtocols` configuration option. Add TLSv1.3 cipher suites to the configured list of supported FIPS cipher suites for each FIPS-enabled transfer site.
