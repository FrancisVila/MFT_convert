{
    "title": "Setting Data Integrity",
    "linkTitle": "Setting Data Integrity",
    "weight": "210"
}## Enabling data integrity

By default, the data integrity check functionality is disabled (no). To enable it.

peluconf set -s monitor payload\_integrity\_option yes

If you enable the data integrity check, you must set the next parameters:

peluconf set -s integrity private\_key %location to Gateway private key (RSA pem file) %

peluconf set -s integrity public\_key %location to Integrator public key (RSA pem file) %

If you enable the data integrity check, you can optionally set the next parameters that stores the password for the Gateway private key:

peluconf set -s integrity private\_key\_dk %location to the derived key file%

peluconf set -s integrity private\_key\_pf %location to the encrypted password file%

The derived key file and the encrypted password file are generated using `pelencpass `tool.

## Transfer parameters for data integrity

`sigfile `and `sigalgo `parameters can be used to manually set the signature of the payload data (necessary mostly for JMS reference mode part). The signature must be generated using Gateway private key. The `sigfile `parameter references a file containing the signature in binary format.

New transfer parameters will be displayed for the incoming transfers, for which the signature of the payload in computed by Gateway on reception:

x\_sigalgo='SHA256withRSA'

x\_signature (256 bytes)= '653362306334343239386663316331343961666266346338393936

66623932343237616534316534363439623933346361343935393931623738353262383535…'

New parameters have been added to the model:

peladm create\_model

\[-sigalgo(-sga) signature and hash algorithm used in payload

signature computation { (SHA256withRSA) }\]

\[-sigfile(-sgf) file containing payload signature in binary format\]

Note: if you create a transfer using a model, you must encrypt the payload with Integrator private key. If you route a transfer using a model, the validation of the signature is made using the Integrator private key.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
