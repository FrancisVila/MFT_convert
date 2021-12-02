{
    "title": "Create a Transfer CFT flow with an unmanaged product ",
    "linkTitle": "Create a flow using an unmanaged product",
    "weight": "170"
}This page describes how to create a {{< TransferCFT/transfercftname  >}} flow in {{< TransferCFT/centralgovernancename  >}} using an unmanaged product and mutual authentication (SSL) for a secure transfer. You may want to become familiar with [PeSIT concepts](../../../protocols_start_here/about_pesit), parameters such as [NSPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/nspart), [NRPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/nrpart), and [SAP](../../../c_intro_userinterfaces/command_summary/parameter_intro/sap), prior to starting the procedure, or refer to the [parameter overview](#Configur) in this page.

## You will need...

-   A {{< TransferCFT/componentlongname >}} associated with an application.
-   An unmanaged product.
-   An installed and running on which you have rights to create a flow.
-   A CG\_CA certificate.

## Parameter overview

The information in this configuration example corresponds to the text used in the fields in the following steps.

<img src="/Images/TransferCFT/unmanged.png" class="maxWidth" />

## Configure an unmanaged product in {{< TransferCFT/centralgovernancename  >}}

1.  Select **Add unmanaged product**.
2.  Enter a **Name** &lt;UP name> and the **Host** &lt;UP host> for this product.
3.  For the **Type**, select **Custom** in the drop-down menu.
4.  Select the environment in the **Operating systems** field.
5.  In the **Protocol** section, enter the **PeSIT login** &lt;UP PeSIT login>and password &lt;UP PeSIT password>. Confirm password.
6.  In the **TCP** subsection, select PeSIT / **Mutual authentication** and add the pesitssl listening **port** &lt;UP PeSIT port in> for the unmanaged product.
7.  Browse to the root certificate to use &lt;UP root certificate>, and upload. The certificate can have the CER, CRT, or PEM format, or be a public certificate chain in the P7B file format.  
    You can use the **Display** button to check the certificate details.
8.  Use all other defaults and click **Save unmanaged product**.

Parameter mapping


| Transfer CFT  | Unmanaged product configuration fields  |
| --- | --- |
| CFTTCP HOST  | Host in the unmanaged product configuration  |
| CFTPART SYST  | Operating system  |
| CFTPART NRPART  | PeSIT Login  |
| CFTPART NRPASSW  | PeSIT password  |
| CFTPART PROT  | Mutual authentication (indicates PeSIT SSL)  |
| CFTPART SAP  | Port  |
|  CFTSSL DIRECT=CLIENT<br/>ROOTCID corresponding to the ROOT certificate in the Transfer CFT PKI database  | Certificate  |


## Create a communication profile on the source {{< TransferCFT/transfercftname  >}}

In this step you create a communication profile on the source {{< TransferCFT/transfercftname  >}} that corresponds to the unmanaged product. To begin, access the **Product List** and select the registered Transfer CFT configuration.

1.  Create a new client communication profile for this partner that corresponds to SSL protocol.
2.  Add PeSIT.
3.  In **Protocol name**, select **PeSITSSL**.
4.  Add Login &lt;CFT PeSIT login> and password &lt;CFT PeSIT password>. Confirm login.
5.  In **Client authentication** select **Upload the private certificate** &lt;CFT user certificate>. As the client, in mutual authentication, the server will require a cert signed by an authority recognized by the unmanaged product.
6.  Enter password.
7.  Specify the **SSL security profile** &lt;UP Communication profile>.
8.  Click **Apply**.

Parameter mapping


| Transfer CFT  | Communication profile for the Unmanaged product  |
| --- | --- |
| CFTPROT  | Protocol name  |
| NSPART  | Login  |
| NSPASSW  | Password  |
| N/A  | Client authentication  |
| N/A  | Upload  |
|  CFTSSL DIRECT=CLIENT<br/>USERCID  | Private certificate  |
| N/A  | Password (for P12)  |
|  CFTSSL DIRECT=CLIENT<br/>ID  | SSL security profile  |


## Create a flow

In the toolbar, select **Flows** &gt; **Add flow**.

<img src="/Images/TransferCFT/flow01.png" class="maxWidth" />

Make the following selections, using the default values for all other fields.

1.  Enter a **Name** for your flow.
2.  Select **Source**, then **Application**.  
    From the list, select {{< TransferCFT/componentlongname >}} as the product type and select your {{< TransferCFT/transfercftname >}}. Confirm by clicking **Add source**.  
    <img src="/Images/TransferCFT/flow03.png" class="maxWidth" />
3.  Select **Protocol**. In the Protocol page, select:
    -   PeSIT as the **Exchange protocol**.
    -   Enter a value for the Flow identifier. Record this identifier as a reference if you want to check the flow configuration on your {{< TransferCFT/componentlongname >}}.
    -   Mutual authentication.
    -   Select Show Transfer CFT communication profiles and select the communication profile that you created.
4.  Select **Target**, then **Unmanaged products**.  
    Click **Edit** product and then from the list, click to select your product.
5.  Click **Select as target** to confirm.
6.  Click **Save**, then click **Deploy**.

 


| Transfer CFT  | Flow field  |
| --- | --- |
| CFTSEND ID  | Flow identifier  |


## Check the flow on {{< TransferCFT/componentlongname  >}}

On the registered Transfer CFT, check to confirm that the flow and partner were created.

Then create a new transfer using the unmanaged product and the flow identifier you defined in .

1.  Add a file to exchange. For example put a file called **report001**, in the {{< TransferCFT/componentshortname >}}` runtime/pub` folder.
2.  From the source {{< TransferCFT/componentshortname >}}, run the SEND command.
    -   Remember to replace `<instance_target>` with your unmanaged product (target).

    <!-- -->

    -   The **Flow identifier** field is equivalent to the {{< TransferCFT/componentshortname >}} IDF parameter.
