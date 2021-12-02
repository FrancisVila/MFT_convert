{
    "title": "SecureRelay with a standalone architecture",
    "linkTitle": "Secure Relay with a standalone architecture",
    "weight": "240"
}This page describes how to configure Transfer CFT in a standalone architecture for use with Secure Relay.

Step overview:

-   Install 1 or more Secure Relay Router Agents
-   Configure Secure Relay
-   Enable Secure Relay and configure Java
-   Configure additional Transfer CFT objects
    -   Network object CFTNET
    -   Protocol object CFTPROT
    -   Partner object CFTPART and CFTTCP

## Secure Relay Router Agent installation

Follow the installation instructions provided in the [Secure Relay RA Installation Guide](https://docs.axway.com/bundle/SecureRelay_271_InstallationGuide_allOS_en_PDF/resource/SecureRelayRA_InstallationGuide_allOS_en_PDF.pdf). During installation, it is essential that you configure the Router Agent CA and user certificate as follows to enable secure communication between the Master Agent and Router Agent:

-   &lt;CACertificate>CA\_for\_RA.der&lt;/CACertificate>
-   &lt;UserCertificate>USER\_for\_RA.p12&lt;/UserCertificate>

You need these values when you configure the Master Agent in the {{< TransferCFT/componentlongname  >}} configuration, where the user certificate that you use must be signed by `CA_for_RA`. You should use the same CA and USER certificate as for the Master Agent.

## Configure the Router Agents in {{< TransferCFT/componentlongname  >}}

After completing installation, configure the Router Agents in the {{< TransferCFT/componentlongname  >}} configuration.

1.  Set the value for the number of Router Agents using the `secure_relay.ra` parameter. {{< TransferCFT/componentlongname >}} generates a set of `secure_relay.ra.n.*` parameters, where the number, *n*, corresponds to the number of Router Agents you defined in this parameter.
2.  You can use the default values for most fields, but you must customize the` secure_relay.ra.0.dmz` parameter. This value must be unique; for example, you can increment the DMZ0 value by one for each Router Agent so that the  second Router Agent has the value` secure_relay.ra.0.dmz = DMZ1`.
3.  Configure the host address for each Secure Relay host using `secure_relay.ra.0.host`.

Example of two Router Agent definitions

```
secure\_relay.ra = 2
 
secure\_relay.ra.0.enable = yes
secure\_relay.ra.0.dmz =
secure\_relay.ra.0.host =
secure\_relay.ra.0.admin\_port = 6810
secure\_relay.ra.0.comm\_port = 6811
secure\_relay.ra.0.nb\_data\_connections = 5
secure\_relay.ra.0.data\_channel\_ciphering = No
secure\_relay.ra.0.outcall\_network\_interface =
 
secure\_relay.ra.1.enable = Yes
secure\_relay.ra.1.dmz =
secure\_relay.ra.1.host =
secure\_relay.ra.1.admin\_port = 6810
secure\_relay.ra.1.comm\_port = 6811
secure\_relay.ra.1.nb\_data\_connections = 5
secure\_relay.ra.1.data\_channel\_ciphering = No
secure\_relay.ra.1.outcall\_network\_interface =
```

## Configure the Master Agent in {{< TransferCFT/componentlongname  >}}

Configure the following UCONF parameters to enable the Master Agent communication with the Router Agent:

-   secure\_relay.ma.ca\_cert\_fname = &lt;must be the same as the CA\_for\_RA.der value>
-   secure\_relay.ma.cert\_fname = &lt;must be a P12 user certificate that is signed by the CA\_for\_RA.der>
-   secure\_relay.ma.cert\_password = &lt;user certificate password>

## Enable Secure Relay and configure the Java

In {{< TransferCFT/componentlongname  >}} from the CFTUTIL prompt, perform the following commands:

1.  Enable Secure Relay:  
    ```
    UCONFSET id=secure\_relay.enable ,value=yes
    ```
2.  Set the full path to Java executable, for example:  
3.  ```
    UCONFSET id=cft.jre.java\_binary\_path ,value=/bin/java
    ```

## Configure {{< TransferCFT/componentlongname  >}} objects

### Createa CFTNET object

1.  Create a CFTNET object where:
    -   TYPE= TCP
    -   protocol value = SR
2.  Define the mandatory parameters RECALLHOST and SSLTERM.
    -   RECALLHOST: The host address on which the Master Agent calls Transfer CFT when Secure Relay receives an incoming call. If Transfer CFT and the Master Agent run of the same host, use the loopback network interface (for example, 127.0.0.1) instead of the public network interface. When using Secure Relay, the HOST parameter designates the network interface that is used on the Router Agent side.
    -   SSLTERM: Set this Boolean to YES to enable SSL termination.
3.  If there is existing CFTNET object(s), the class parameter must be different.

Example

```
CFTNET ID = NETSR,
PROTOCOL = SR,
TYPE = TCP,
CALL = INOUT,
CLASS = 1,
HOST = <e.g. INADDR\_ANY, network\_interface\_used\_by\_Router\_Agent>,
RECALLHOST = 127.0.0.1, /\*network\_interface\_used\_by\_Transfer\_CFT\*/
```

## Create a CFTPROT object

This section describes the CFTPROT object, and how various parameters are related to enabling secure data transmission using Secure Relay.

-   CFTPROT is related to the CFTNET object through the NET parameter.
-   The SAP parameter is the listening port that is used on the RA side (using the CFTNET HOST parameter as the network interface).

**Example**

This example uses a CFTNET object called NETSR.

```
CFTPROT id = PESITANY,
net = NETSR,
sap = 1761,
Prot=PESIT,
prof = ANY
```

## Create CFTPART and CFTTCP objects

When a partner object refers to a CFTPROT object and a CFTNET object that use Secure Relay, it uses Secure Relay for both incoming and outgoing connections.

So to complete the configuration, create a CFTPART and a CFTTCP. In this way, the CFTPART refers to the CFTPROT object, and that in turn refers to a CFTNET, which points to Secure Relay.

Example

This is an example of the CFTPART and CFTTCP object configuration, using PESITANY.

```
CFTPART id = PARIS,
 prot = PESITANY,
 sap = <remote\_partner\_sap>,
 nspart = NPHOENIX,
  nrpart = NPARIS,
  mode = replace
 
CFTTCP id = PARIS,
 class = 1, /\* same class as the one used in the CFTNET \*/
 host = <remote\_partner\_host\_address>,
 mode = replace
```

### Indicate a specific SecureRelay to use

If you would like to use a specific SecureRelay with a given partner, set the following parameter in the CFTPART:

```
SRDMZ = <UCONF secure\_relay.ra.*n*.dmz value, where n is the number that corresponds to the SecureRelay to use>
```
