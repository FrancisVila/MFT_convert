{
    "title": "Test for glitches x",
    "linkTitle": "Test for glitches",
    "weight": "90"
}this should be a note, &gt; in markdown:

> **Note:**
>
> This functionality does not apply to LDAP and SSO users.

false link in http://localhost:1313/docs/transfercft/concepts/cft\_configuration\_concepts\_start\_here/default\_receive\_template\_concepts/#About\_the\_default\_CFTRECV\_object

This is a procedure: (in SecureTransport)

To set up <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> in Azure Virtual Network, you must pass through the following steps:

1.  Create a Virtual Network.
2.  Create Network Security Groups.
3.  Create one public and two private subnets.
4.  Launch the following instances:
    1.  *(optionally)* Launch an instance for an Administration Host.
    2.  Launch instances in the public subnets for <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Edge installations.
    3.  Launch instances in the private subnets for <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Server installations.
    4.  Launch instances in the private subnets for external GlusterFS file system.

      
    Note <span style="font-weight: normal;">Make sure to separate all components of each Enterprise Cluster node in a respective Availability Zone.</span>
5.  Set up two Microsoft SQL Server Always On Availability groups, deployed in a Windows Server Failover Cluster(WSFC).
6.  Establish VPN connection to your Azure VNet.
7.  Set up <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Enterprise Cluster.
8.  Set up Load Balancer.

 

This should look like code:



    keytool –importcert

       -trustcacerts
       -alias AXWMFTCA
       -file <my_root_certificate>.der

       -storepass changeit-keystore <keystore>


    CFTUTIL SEND part=newyork, idf=idf1, fname=/dir_c/work/newyork/idf1/my_file.20131025.txt



    CFTPART id          = USER1,


            prot        = SFTP,

    sap = 1763,    
            
    nspart      = "user1",              

            nspassw     = "TheUser1Password", ...


    CFTTCP id          = USER1,
            

    host        = <server host>,
           ...

Code from SecureTransport:


    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
                                <!-- This is a sample file for SSO configuration for Admin component. -->
                            <SSOConfiguration>
            <!-- Features tag is optional - Here are the default values -->
                            <Features>
                <!-- Configures the session cookie whether to be set with Secure 
                                flag. Recommended value: true. -->
                            <Feature key="secure-cookie" value="true" />
             <!-- Sample Keycloak Identity provider definition. -->
                                <SamlIdentityProvider
                                entityId="https://st.keycloak.axway.int/"
                                metadataUrl="./keycloak-idp-metadata.xml"
                                verifyAssertionExpiration="false"
                            sign="true">
                <!-- Mappings tag is optional -->
                                <Mappings>
                                <!-- NOTE: SecureTransport does not support the attribute 
                                mapping for Admin component. -->
                            </Mappings>
                <!-- Features control specific behavior of SAML message processing. -->
                                <Features>
                                <!-- Allows interaction with the IdP by plain HTTP. Default: 
                                false. -->
                            <Feature key="saml-allow-http-connection" value="false"/>
                                <!-- Allows unsigned assertions in messages received from the 
                                Identity Provider. Default: false. -->
                            <Feature key="saml-allow-unsigned-assertion" value="false"/>

AAAA

<table>
         
         
         
   
   <thead>
      <tr>
<th class="BodyE-Column1-Body1" data-bgcolor="#C0C0C0" style="width: 45.851%; padding-right: 10px; padding-left: 10px; background-color: #c0c0c0; border-left-color: #808080; border-left-style: Inset; border-top-color: #808080; border-top-style: Inset; border-right-color: #808080; border-right-style: Inset; border-bottom-color: #808080; border-bottom-style: Inset; border-left-width: 1px; border-top-width: 1px; border-right-width: 1px; border-bottom-width: 1px" width="45.851%"><p>Topic</p>         </th>
<th class="BodyD-Column1-Body1" data-bgcolor="#C0C0C0" style="width: 54.149%; padding-right: 10px; padding-left: 10px; background-color: #c0c0c0; border-left-color: #808080; border-left-style: Inset; border-top-color: #808080; border-top-style: Inset; border-right-color: #808080; border-right-style: Inset; border-bottom-color: #808080; border-bottom-style: Inset; border-left-width: 1px; border-top-width: 1px; border-right-width: 1px; border-bottom-width: 1px" width="54.149%"><p>Contents</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../concepts/cft_configuration_concepts_start_here/authorization_list_concepts">Creating authorizations
lists CFTAUTH</a></p>         </td>
         <td><p>Describes the CFTAUTH object, which is a list of authorized
file identifiers that defines user access authorization for each partner.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../concepts/cft_configuration_concepts_start_here/network_file_identifier_concepts">Template
to virtual file association CFTIDF</a></p>         </td>
         <td><p>Describes the CFTIDF
object, which defines a network identifier for a given partner, and a
transfer direction, when partners cannot agree on common file identifiers.</p>         </td>
      </tr>
      <tr>
         <td><p>Default
receive template CFTRECV</p>         </td>
         <td><p>Describes general file reception concepts and details the
default CFTRECV template.</p>         </td>
      </tr>
      <tr>
         <td><p>Default send
templates CFTSEND</p>         </td>
         <td><p>Describes general file reception concepts and details the
default CFTSEND template.</p>         </td>
      </tr>
      <tr>
         <td><p>Conversion tables
CFTXLATE</p>         </td>
         <td><p>Describes the CFTXLATE object, which is used to define
translation tables between 2 alphabets.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTT93W"></span>CFTT93W PART=&amp;part IDS=&amp;ids Negative ack not supported</p>
<p>CFTT93W Negative ack not supported PART=&amp;part IDS=&amp;ids</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The  final
partner signals to the initial file sender that application errors
were detected. This occurs via a negative acknowledgments sent in a PeSIT Hors SIT
message, where IDS is the reference for the session context.</p>         </td>
      </tr>
   </tbody>
</table>

 

 

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>id</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Privilege identifier</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>String80</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>resource</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Resource on which this privilege applies</p>         </td>
      </tr>
      <tr>
         <td><p>actions</p>         </td>
         <td><p>List of String32</p>         </td>
         <td><p>Actions authorized on the resource (1 to 16 actions)</p>         </td>
      </tr>
      <tr>
         <td><p>condition</p>         </td>
         <td><p>String256</p>         </td>
         <td><p>Condition to check for authorizing (<a href="#Specifyi">see below</a>)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th class="BodyE-Column1-Body1" data-bgcolor="#C0C0C0" style="width: 45.851%; padding-right: 10px; padding-left: 10px; background-color: #c0c0c0; border-left-color: #808080; border-left-style: Inset; border-top-color: #808080; border-top-style: Inset; border-right-color: #808080; border-right-style: Inset; border-bottom-color: #808080; border-bottom-style: Inset; border-left-width: 1px; border-top-width: 1px; border-right-width: 1px; border-bottom-width: 1px" width="45.851%"><p>Topic</p>         </th>
<th class="BodyD-Column1-Body1" data-bgcolor="#C0C0C0" style="width: 54.149%; padding-right: 10px; padding-left: 10px; background-color: #c0c0c0; border-left-color: #808080; border-left-style: Inset; border-top-color: #808080; border-top-style: Inset; border-right-color: #808080; border-right-style: Inset; border-bottom-color: #808080; border-bottom-style: Inset; border-left-width: 1px; border-top-width: 1px; border-right-width: 1px; border-bottom-width: 1px" width="54.149%"><p>Contents</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../concepts/cft_configuration_concepts_start_here/authorization_list_concepts">Creating authorizations
lists CFTAUTH</a></p>         </td>
         <td><p>Describes the CFTAUTH object, which is a list of authorized
file identifiers that defines user access authorization for each partner.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../concepts/cft_configuration_concepts_start_here/network_file_identifier_concepts">Template
to virtual file association CFTIDF</a></p>         </td>
         <td><p>Describes the CFTIDF
object, which defines a network identifier for a given partner, and a
transfer direction, when partners cannot agree on common file identifiers.</p>         </td>
      </tr>
      <tr>
         <td><p>Default
receive template CFTRECV</p>         </td>
         <td><p>Describes general file reception concepts and details the
default CFTRECV template.</p>         </td>
      </tr>
      <tr>
         <td><p>Default send
templates CFTSEND</p>         </td>
         <td><p>Describes general file reception concepts and details the
default CFTSEND template.</p>         </td>
      </tr>
      <tr>
         <td><p>Conversion tables
CFTXLATE</p>         </td>
         <td><p>Describes the CFTXLATE object, which is used to define
translation tables between 2 alphabets.</p>         </td>
      </tr>
   </tbody>
</table>
