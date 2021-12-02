{
    "title": "Default ports",
    "linkTitle": "Ports",
    "weight": "180"
}The following list contains the default {{< TransferCFT/componentshortname  >}} port numbers used for installation. You can check in advance that these ports do not conflict with ports used by other applications on the same machine.

You may need to modify the default port numbers, depending on your configuration.

The Internet Assigned Numbers Authority (IANA) reserves the TCP ports 1761-1768 for {{< TransferCFT/componentshortname  >}}. For more information, refer to: [www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers](http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml?&page=31).


| Component  |  Port  |
| --- | --- |
| PeSIT  | 1761  |
| SSL  | 1762  |
| SFTP  | 1763  |
| COMS  | 1765  |
| Copilot  | 1766  |
| Transfer CFT UI (Copilot) server for {{< TransferCFT/centralgovernancename  >}}  | 1767  |
| REST API  | 1768  |
|   | 12553  |
| {{< TransferCFT/centralgovernancename  >}} SSL  | 12554  |
|  {{< TransferCFT/securerelayname  >}} MA<br/>ma.comm_port  |  <br/>6801  |
|  {{< TransferCFT/securerelayname  >}} RA<br/> • ra.comm_port<br/> • ra.admin_port</li>  |  <br/> • 6811<br/> • 6810</li>  |


Legend:

-   PeSIT (PESITANY protocol): PeSIT in plain text
-   SSL: PeSIT protocol over SSL/TLS
-   COMS: Synchronous transfers
-   Copilot: Provides access to {{< TransferCFT/componentshortname >}} UI server from an Internet browser
-   Copilot for {{< TransferCFT/centralgovernancename >}}: Provides secure access for (mutual authentication)
-   : Used to connect to Central Governance
