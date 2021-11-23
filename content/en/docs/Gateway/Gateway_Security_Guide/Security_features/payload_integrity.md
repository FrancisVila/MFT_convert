{
    "title": "Payload integrity",
    "linkTitle": "payload_integrity",
    "weight": "180"
} 

The purpose of *payload integrity* is to detect any tampering with files stored by {{< Gateway/gatewayname  >}}.

You can enable the payload integrity check to assure that payload haven’t changed between the moment is has been received by Gateway and further actions: routing to Integrator or routing to a third party. If activated, Gateway generates the signature for the incoming transfer’s payload using Gateway private key and is validating the signature for the routed transfers. The signature for the routed transfers can be generated either by Gateway or by Integrator. The protocols for which the signature is computed in Gateway, for incoming transfers are: SWIFTNet, PeSIT and JMS.

Data integrity operations rely on digital signatures, so its usage assumes the following:

-   {{< Gateway/gatewayname >}} is configured with pair of keys to build/verify a signature
-   A public key performs signature verification on requests submitted from other sources
-   Local operations, including requests submitted directly in Gateway (via command line or GUI), are performed only using the keys from {{< Gateway/gatewayname >}}.
-   Requests submitted by {{< Gateway/integratorname >}} are performed by {{< Gateway/integratorname >}}'s public key.

## Payload integrity coverage

-   For requests submitted by {{< Gateway/integratorname >}}, when the option is enabled, data integrity is always enforced. Any submission without signature information fails.
-   Currently, Gateway supports only RSA keys with the SHA256 hash algorithm in all payload integrity related operations (sign and verify).
-   Requests submitted locally in Gateway are **not** covered by payload integrity
-   For transfers initiated via command line tools or Navigator, it is possible to set up mechanisms to implement payload integrity.

## Outbound transfers

For outbound transfers, data integrity is achieved by attaching a signature when a transfer request is submitted to Gateway.

-   If the transfer is initiated by a local operator, the attached signature is generated using {{< Gateway/gatewayname >}}'s private key.
-   If the submitted by {{< Gateway/integratorname >}}, the signature is generated with the {{< Gateway/integratorname >}}'s private key.

Once the transfer is actually started, the verification is performed with the pair of that key.

For further information refer to [Payload Security](#).

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
