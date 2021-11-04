{
    "title": "Clocks out of sync",
    "linkTitle": "Clocks out of sync",
    "weight": "240"
}If the clock on both the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge are out of sync, the two servers might not be able to communicate correctly. Verify that both systems are set for the same time and date.

If you are using the Windows platform, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge might not be in the same domain, but in a workgroup instead. If this is the case, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge does not use the Windows Time Service and you must manually verify that the clocks are in sync.

When using a UNIX-based platform, make sure that the time formats and time zones are the same. If they are not the same, the imported CA certificate might have a different "valid from" date and time, and are considered invalid until the server reach the listed date and time.

For an Enterprise Cluster (EC), the clocks of all servers must be synchronized.

**Related topics:**

-   <a href="../c_st_trust_establishment_issues" class="MCXref xref">Trust establishment issues</a>
-   <a href="../c_st_connectivity" class="MCXref xref">Connectivity</a>
