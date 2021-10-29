{
    "title": "Create a Transfer CFT flow with an unmanaged product ",
    "linkTitle": "Create a flow using an unmanaged product",
    "weight": "170"
}This page describes how to create a Transfer CFT flow in Central Governance using an unmanaged product and mutual authentication (SSL) for a secure transfer. You may want to become familiar with [PeSIT concepts](../../protocols_start_here/about_pesit), parameters such as [NSPART](../../c_intro_userinterfaces/command_summary/parameter_intro/nspart), [NRPART](../../c_intro_userinterfaces/command_summary/parameter_intro/nrpart), and [SAP](../../c_intro_userinterfaces/command_summary/parameter_intro/sap), prior to starting the procedure, or refer to the [parameter overview](#Configur) in this page.

## You will need...

-   A Transfer CFT associated with an application.
-   An unmanaged product.
-   An installed and running Central Governance on which you have rights to create a flow.
-   A CG\_CA certificate.

## Parameter overview

The information in this configuration example corresponds to the text used in the fields in the following steps.

![](/Images/TransferCFT/unmanged.png)

## Configure an unmanaged product in Central Governance

1.  Select **Add unmanaged product**.
2.  Enter a **Name** &lt;UP name> and the **Host** &lt;UP host> for this product.
3.  For the Type, select Custom in the drop-down menu.
4.  Select the environment in the **Operating systems** field.
5.  In the **Protocol** section, enter the **PeSIT login** &lt;UP PeSIT login>and password &lt;UP PeSIT password>. Confirm password.
6.  In the **TCP** subsection, select PeSIT / Mutual authentication and add the pesitssl listening **port** &lt;UP PeSIT port in> for the unmanaged product.
7.  Browse to the root certificate to use &lt;UP root certificate>, and upload. The certificate can have the CER, CRT, or PEM format, or be a public certificate chain in the P7B file format.  
    You can use the Display button to check the certificate details.
8.  Use all other defaults and click Save unmanaged product.

Parameter mapping

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Transfer CFT </th>
         <th>Unmanaged product configuration fields</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>CFTTCP HOST         </td>
         <td>Host in the unmanaged product configuration         </td>
      </tr>
      <tr class="even">
         <td>CFTPART SYST         </td>
         <td>Operating system         </td>
      </tr>
      <tr class="odd">
         <td>CFTPART NRPART         </td>
         <td>PeSIT Login         </td>
      </tr>
      <tr class="even">
         <td>CFTPART NRPASSW         </td>
         <td>PeSIT password         </td>
      </tr>
      <tr class="odd">
         <td>CFTPART PROT         </td>
         <td>Mutual authentication (indicates PeSIT SSL)         </td>
      </tr>
      <tr class="even">
         <td>CFTPART SAP          </td>
         <td>Port         </td>
      </tr>
      <tr class="odd">
         <td>            <p>CFTSSL DIRECT=CLIENT</p>
            <p>ROOTCID corresponding to the ROOT certificate in the Transfer CFT PKI database</p>         </td>
         <td>Certificate         </td>
      </tr>
   </tbody>
</table>

## Create a communication profile on the source Transfer CFT

In this step you create a communication profile on the source Transfer CFT that corresponds to the unmanaged product. To begin, access the **Product List** and select the registered Transfer CFT configuration.

1.  Create a new client communication profile for this partner that corresponds to SSL protocol.
2.  Add PeSIT.
3.  In **Protocol name**, select **PeSITSSL**.
4.  Add Login &lt;CFT PeSIT login> and password &lt;CFT PeSIT password>. Confirm login.
5.  In **Client authentication** select **Upload the private certificate** &lt;CFT user certificate>. As the client, in mutual authentication, the server will require a cert signed by an authority recognized by the unmanaged product.
6.  Enter password.
7.  Specify the **SSL security profile** &lt;UP Communication profile>.
8.  Click **Apply**.

Parameter mapping

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Transfer CFT </th>
         <th>Communication profile for the Unmanaged product</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>CFTPROT         </td>
         <td>Protocol name         </td>
      </tr>
      <tr class="even">
         <td>NSPART         </td>
         <td>Login         </td>
      </tr>
      <tr class="odd">
         <td>NSPASSW         </td>
         <td>Password         </td>
      </tr>
      <tr class="even">
         <td>N/A         </td>
         <td>Client authentication         </td>
      </tr>
      <tr class="odd">
         <td>N/A         </td>
         <td>Upload         </td>
      </tr>
      <tr class="even">
         <td>            <p>CFTSSL DIRECT=CLIENT</p>
            <p>USERCID</p>         </td>
         <td>Private certificate         </td>
      </tr>
      <tr class="odd">
         <td>N/A         </td>
         <td>Password (for P12)         </td>
      </tr>
      <tr class="even">
         <td>            <p>CFTSSL DIRECT=CLIENT</p>
            <p>ID</p>         </td>
         <td>SSL security profile         </td>
      </tr>
   </tbody>
</table>

## Create a flow

In the Central Governance toolbar, select **Flows** &gt; **Add flow**.

![](/Images/TransferCFT/flow01.png)

Make the following selections, using the default values for all other fields.

1.  Enter a **Name** for your flow.
2.  Select **Source**, then **Application**.  
    From the list, select Transfer CFT as the product type and select your Transfer CFT. Confirm by clicking **Add source**.  
    ![](/Images/TransferCFT/flow03.png)
3.  Select Protocol. In the Protocol page, select:
    -   PeSIT as the **Exchange protocol**.
    -   Enter a value for the Flow identifier. Record this identifier as a reference if you want to check the flow configuration on your Transfer CFT.
    -   Mutual authentication.
    -   Select Show Transfer CFT communication profiles and select the communication profile that you created.
4.  Select **Target**, then **Unmanaged products**.  
    Click **Edit** product and then from the list, click to select your product.
5.  Click **Select as target** to confirm.
6.  Click **Save**, then click Deploy.

 

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Transfer CFT </th>
         <th>Flow field</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>CFTSEND ID         </td>
         <td>Flow identifier         </td>
      </tr>
   </tbody>
</table>

## Check the flow on Transfer CFT

On the registered Transfer CFT, check to confirm that the flow and partner were created.

Then create a new transfer using the unmanaged product and the flow identifier you defined in Central Governance.

1.  Add a file to exchange. For example put a file called report001, in the Transfer CFT runtime/pub folder.
2.  From the source Transfer CFT, run the SEND command.
    -   Remember to replace &lt;instance\_target> with your unmanaged product (target).

    <!-- -->

    -   The Flow identifier field is equivalent to the Transfer CFT IDF parameter.
