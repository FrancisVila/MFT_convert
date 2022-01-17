{
    "title": "Axway AMPLIFY architecture",
    "linkTitle": "Axway AMPLIFY architecture",
    "weight": "120"
}Axway AMPLIFY{{< TransferCFT/platformorsuitelongname  >}} Managed File Transfer provides a product platform aimed at increasing the
efficiency of business processes. This platform enables you to integrate
the applications in your corporate information system and implement exchanges
between these applications and external partners. Transfer CFT{{< TransferCFT/componentshortname  >}} in combination with other Axway{{< TransferCFT/companyname  >}} products can provide a complete business solution for creating secured, guaranteed
exchanges with partners.

## Axway{{< TransferCFT/companyname  >}} products

Transfer CFT{{< TransferCFT/componentshortname  >}} can interact with a variety of Axway{{< TransferCFT/companyname  >}} products
 to enable
you to better supervise, track, and analyze your transfer operations.
Additional products include, but are not limited to, the following:

- [API portal](#APIportal), [API Gateway](#APIgtw), [API Manager](#APImanager)
- [Central Governance](#Central_Governance)
- Communication gateways: [Gateway, Secure Transport](#Gateway)
- [SecureRelay](#SecureRelay)
- [TrustedFile](#TrustedFile)

********Example Axway AMPLIFY{{< TransferCFT/platformorsuitelongname  >}} MFT implementation********

****![](/Images/TransferCFT/tbus_products.png)****

<span id="APIgtw"></span>

#### API Gateway{{< TransferCFT/apiservername  >}}

API Gateway{{< TransferCFT/apiservername  >}} is a comprehensive platform for managing, delivering, and securing enterprise APIs, applications, and consumers. In this reference solution{{< TransferCFT/referenceimplementation  >}}, it can be used to manage web services and APIs exposed by Transfer CFT{{< TransferCFT/transfercftname  >}}, SecureTransport{{< TransferCFT/securetransportname  >}}, or third-party products.

<span id="APImanager"></span>

#### API Manager

API Manager provides web-based API administration and partner management capabilities layered on API Gateway, as well as an API Catalog with life cycle management. The web UI also enables an administrator to manage partners that consume APIs and set the appropriate levels of security and quotas.

<span id="APIportal"></span>

#### API Portal

API Portal is a self-service portal that enables client application developers to browse and consume APIs for use in their applications, whether they be mobile, social media, web, or traditional applications. API Portal enables engagement with both internal and external application developers to promote APIs for consumption. It enables new go to market channels in the digital economy.

#### Central Governance{{< TransferCFT/centralgovernancename  >}}

For all products, Central Governance{{< TransferCFT/centralgovernancename  >}} provides IAM and Visibility services through embedded editions of PassPort{{< TransferCFT/passportname  >}} and Sentinel{{< TransferCFT/sentinelname  >}}, enabling:

- Global management of user identity and rights, providing a central control point for security enforcement
- End-to-end centralized supervision of data flows, consistent with definitions in the repository
- Out-of-the-box web dashboards to get a global view of data flow activity, as well as the ability to create custom dashboards

<span id="Central_Governance"></span>

#### Central Governance for Transfer CFT{{< TransferCFT/componentshortname  >}}

For Transfer CFT{{< TransferCFT/transfercftname  >}}, Central Governance{{< TransferCFT/centralgovernancename  >}} also provides product configuration, and flow definition and deployment services.

- Global data flow repository, providing end-to-end data flow definitions, from business application to infrastructure level
- Automatic discovery of products to be managed
- Centralized management of product configuration and associated deployment, including mass processing capabilities for highly distributed environments, which include groups and configuration policies
- Centralized day-to-day operations management: to start and stop products and to view their logs
- Out-of-the box alert management to track any problem linked to products or data flow processing, including a subscription mechanism for alert notifications

<span id="Gateway"></span>

#### Communication gateways

##### Gateway

Gateway is a secure, open and scalable communication gateway for mission-critical system-to-system data transfers with strong support for FSI protocols such as SWIFT. It handles
file exchanges between applications inside the enterprise, and partners
outside of the enterprise network.

##### SecureTransport

SecureTransport is an enhanced, secure, scalable, and highly available gateway for both system-to system data transfers and ad hoc human transactions. In Managed File Transfer{{< TransferCFT/transferbusname  >}}, SecureTransport{{< TransferCFT/securetransportname  >}} serves as a hub to secure and route file transfers between partners, internal applications, and humans.

##### SecureTransport Edge{{< TransferCFT/securetransportedgename  >}}

Using SecureTransport Edge{{< TransferCFT/securetransportedgename  >}}, you can create a multi-tier file exchange infrastructure with multi-protocol managed file transfer, SSL termination, and back-end authorization that streams data across the DMZ to SecureTransport{{< TransferCFT/securetransportname  >}}.

You can deploy multiple Edge gateways in the DMZ for load balancing and performance optimization.

SecureTransport Edge{{< TransferCFT/securetransportedgename  >}} also safeguards compliance wit HSOX, GLBA, HIPAA, and other corporate, industry, and government mandates governing the security and privacy of sensitive information.

<span id="SecureRelay"></span>

#### SecureRelay

Secure Relay is a secure edge gateway that integrates with Axway Interchange and Gateway. You deploy Secure Relay in the DMZ to protect your data, your customers and your networks while enabling critical file transfer services between approved parties.

<span id="TrustedFile"></span>

#### TrustedFile

TrustedFile provides cryptographic features for encryption and digital signature, and is used to secure data at rest. TrustedFile is a standalone product, but is also embedded in Transfer CFT.
