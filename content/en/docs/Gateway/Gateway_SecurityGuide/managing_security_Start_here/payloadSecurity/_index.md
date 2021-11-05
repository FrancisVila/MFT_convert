{
    "title": "Payload integrity",
    "linkTitle": "Payload integrity",
    "weight": "180"
}  

## Introduction

### Inbound transfers

When activated, this feature enables Gateway to attach signatures to all received files, and to use that additional information when the file is routed to a third party. This approach helps to detect any eventual tampering of the files stored by Gateway. When this functionality is enabled, Gateway computes the signature of the payload received from incoming transfers and in case of routing, payload signature validation is performed. When Integrator is used, Gateway forwards it the signature computed for incoming data and validates the signature received from Integrator before routing the payload further.

Enabling this feature makes Axway Integrator perform a signature verification with Gateway's public key before processing the file. This causes failure for any file submitted by Integrator that is not accompanied by the signature information.

The key used by Gateway for signature validation at routing:

• is the Gateway public key if the signature was manually set into <span class="code">peltrans</span>, in the <span class="code">sigfile</span> option

• is the Integrator public key if the signature was manually set into the model used to route the file, in the <span class="code">sigfile </span>option

In more detail: if the following conditions are met:

-   the global configuration is activated (<span class="code"></span>if <span class="code">payload\_integrity\_option</span> is set to <span class="code">yes</span>)
-   the necessary parameters are set: Gateway private key, optionally the password of the key, Integrator public key

then after Gateway has received data on SWIFTNet, PeSIT or JMS, it does the following:

-   computes the signature of the payload using SHA256 hash algorithm,
-   signs in with Gateway private key
-   stores it in the incoming transfer parameters (<span class="code">x\_sigalgo</span>, <span class="code">x\_signature</span>).
-   if the incoming transfer is routed to Integrator, the signature of the transfer is also sent.

### Requests submitted locally

Note that data integrity is not enforced on requests submitted locally in Gateway. However there are mechanisms that can enable payload integrity on transfers initiated via command-line tools, or Navigator.

### Outbound transfers

Payload integrity is also enforced on the outbound transfers, either submitted a Gateway operator or by Integrator. This is achieved by attaching a signature when a transfer request is submitted to Gateway. In this case, the first operation that is performed when the transfer is about to start is integrity verification. There are two distinct use cases:

-   when a local operator submits a transfer on which data integrity should be performed, the signature that is attached must be generated with the private key of Gateway, so that when the transfer is actually started the verification is performed with the pair of this key.
-   for outbound requests submitted by Integrator, the signature must be generated with the private key of Integrator. In the case, when the transfer starts, verification is performed with the pair of that key.

## Requirements

Using the payload security mechanism described in this chapter supposes you have the following:

-   a pair of keys to build/verify signatures, with a public key to perform signature verification on requests submitted by others
-   local operations, including requests submitted directly in Gateway (via command line or GUI), are performed only with the Gateway key or keys.
-   The option is activated only when <span class="code">payload\_integrity\_option </span>is set to <span class="code">yes</span>. See <a href="opensslexample" class="MCXref xref">Working with Payload integrity</a>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)