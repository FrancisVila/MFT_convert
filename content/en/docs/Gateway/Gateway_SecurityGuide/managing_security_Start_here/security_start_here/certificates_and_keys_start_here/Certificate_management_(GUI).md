{
    "title": "Managing certificates",
    "linkTitle": "Managing certificates",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Overview](#Overview)

[Importing a certificate](#Importing_a_certificate)

[Displaying a certificate](#Displaying_a_certificate)

[Modifying certificate status](#Modifying_certificate_status)

[Exporting a certificate](#Exporting_a_certificate)

[Deleting a certificate](#Deleting_a_certificate)

<span id="Overview"></span>

## Overview

The Security Certificate object enables you to import a certificate from a file into the local database. Additionally, you can use the GUI Certificate object to check certificate status, export a certificate, delete or update a certificate.

The name of the certificate must be unique. The DN of the read certificate is checked to ensure that the certificate name is unique in the database.

When you import a user certificate, you must also import its associated private keys.

<span id="Importing_a_certificate"></span>

## Importing a certificate

To import a certificate:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Certificate</span> sub-node, and then select <span style="font-weight: bold;">Import...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Welcome to the Certificate Import Wizard</span> window.
3.  Click <span style="font-weight: bold;">Next</span> to continue.  
    Gateway displays the <span style="font-style: italic;">File to import</span> window with these fields:
4.  Complete the <span style="font-style: italic;">File to import</span> window. Click <span style="font-weight: bold;">Next</span> to continue with the <span style="font-style: italic;">Certificate Import Wizard</span>.  
    Gateway displays the <span style="font-style: italic;">Completing the certificate import</span> window.
5.  Confirm the certificate information, and then click <span style="font-weight: bold;">Finish</span>.

<span id="Displaying_a_certificate"></span>

## Displaying a certificate

To display a certificate:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management > Certificate**  
    Gateway displays nodes for the [certificate types](../certificate_restrictions#Certificate_types):
    -   Root: Root certification authority certificate
    -   CA: Intermediate Certification Authority certificate
    -   User: User certificate
    -   Other: Undetermined type of certificate
2.  Click the node that represents the category of certificate to display.  
    Gateway displays the certificates of the selected category in the display (right) pane.

<span id="Modifying_certificate_status"></span>

## Modifying certificate status

The certificate status is listed in the right pane work area. To modify the certificate status:

1.  Display certificates (as described above).
2.  In the display (right) pane, right-click the icon that precedes the name of the certificate for which you want to change status, and then choose <span style="font-weight: bold;">Select...</span> in the context menu.  
    Gateway displays the <span style="font-weight: bold;">Select Certificates</span> tab.
3.  Select a <span style="font-weight: bold;">State</span>:
    -   Enabled
    -   Disabled
    -   To Check
    -   Other
4.  Click <span style="font-weight: bold;">OK</span> to confirm your selection.  
    Gateway updates the status if the certificate.

<span id="Exporting_a_certificate"></span>

## Exporting a certificate

*Not available in the current version.*

<span id="Deleting_a_certificate"></span>

## Deleting a certificate

To remove a certificate from the database:

1.  Display certificates (as described above).
2.  In the display (right) pane, right-click the icon that precedes the name of the certificate you want to delete.
3.  Select <span style="font-weight: bold;">Delete</span> from the context menu.  
    Gateway removes the certificate from the database and removes the entry from the certificates list in the display pane.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
