{
    "title": "Edit an XML file",
    "linkTitle": "Edit an XML file",
    "weight": "180"
}Read the following information before editing an XML file:

-   To change the password for the account, delete the `encryptedPassphrase` element and replace it with a `passphrase` element. Type the new account password using plain text.  
    `<passphrase>user3</passphrase>`  
    The password is encrypted during the import process.

-   You can add or modify the information for a transfer site in its `site` element. Each setting that applies to all transfer sites has an element named for the setting. The information specific to the transfer protocol is represented by the `customProperties` element using the format `<entry key="fieldname">value</entry>` where `fieldname` is the name of the field in the transfer site, such as `port`, and `value` is the information entered for that field, such as `801`.

-   You can add or modify the information for a transfer profile in its `Idf` element:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadE-Column1-Header1">Element         </th>
    <th class="HeadD-Column1-Header1">Valid values         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>Transfer Profile Name         </td>
             <td>name         </td>
             <td>Any valid string         </td>
          </tr>
          <tr>
             <td>Files To Send         </td>
             <td>sendMapping         </td>
             <td>Any valid string         </td>
          </tr>
          <tr>
             <td>Receive File As         </td>
             <td>receiveMapping         </td>
             <td>Any valid string         </td>
          </tr>
          <tr>
             <td>Acknowledge transfer         </td>
             <td>sendingAcknowledgmentEnabled         </td>
             <td><code>false</code><br />
    <code>true</code>         </td>
          </tr>
          <tr>
             <td>File Label         </td>
             <td>fileLabelOption         </td>
             <td><code>DONT_SEND</code><br />
    <code>SEND_FILENAME</code><br />
    <code>SEND_FILENAME_AND_PATH</code>         </td>
          </tr>
          <tr>
             <td>All files         </td>
             <td>multiSelect         </td>
             <td><code>false</code><br />
    <code>true</code>         </td>
          </tr>
          <tr>
             <td>Transfer Mode         </td>
             <td>transferMode         </td>
             <td><code>ASCII</code><br />
    <code>BINARY</code><br />
    <code>EBCDIC</code>         </td>
          </tr>
          <tr>
             <td>Record Format         </td>
             <td>recordFormat         </td>
             <td><code>0</code> for Fixed<br />
    <code>128</code> for Variable         </td>
          </tr>
          <tr>
             <td>Record Length         </td>
             <td>recordLength         </td>
             <td>Any valid positive integer         </td>
          </tr>
       </tbody>
    </table>

-   To indicate that a transfer profile is the default, include the `<default>true</default>` element in the `Idf` element. Only one transfer profile can include this element.

-   If you add or modify a subscription, make sure that the application is set up on the server where you are importing the XML file or that you are importing the appropriate application information in the same XML file.

-   To modify an application name in a subscription, edit the following element:  
    `<applicationReference>MySub</applicationReference>`

-   You can change the account information of an existing account, or you can add new accounts to the file.

-   When editing an account, you can modify the account information and use the existing `id` attribute in the `Account` element.

-   When adding an account, include the following elements in a new `completeAccount` element. Do not include the `id` attribute.  



                <account authByEmail="false" unlicensed="false" 
            isUnlicensedAllowedToReply="true" disabled="false" >
            <name>partner1</name>
            <type>user</type>
            <usrid>1001</usrid>
            <grpid>1003</grpid>
            <homeFolder>/home/users/partner1</homeFolder>
            <homeFolderAccessLevel>PUBLIC</homeFolderAccessLevel>
            <email>partner1@example.com</email>
            <phone>800-555-0199</phone>
            <htmlTemplateFolderPath>/html/skin/ric</htmlTemplate
        FolderPath>
            <notes>Include ad hoc file transfer functions.</notes>
            <deliveryMethod>CUSTOM</deliveryMethod>
            <enrollmentTypes>CHALLENGED_LINK</enrollmentTypes>
            <implicitEnrollmentType>EXISTING_ACCOUNT</implicitEnrollmentType>
            <customAttributes>
                <customProperties>
                    <entry key="encryptMode">unspecified</entry>
                    <entry key="routingMode">reject</entry>
                    <entry key="transferType">E</entry>
                    <entry key="transfersWebServiceAllowed">false</entry>
                </customProperties>
                <localCertificates>
                </localCertificates>
                <partnerCertificates>
                </partnerCertificates>
                <userCertificates>
                </userCertificates>
            </customAttributes>
        </account> 

      
    The elements correspond to the fields in the account *Settings* pane:  

    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadE-Column1-Header1">Element         </th>
    <th class="HeadD-Column1-Header1">Valid values         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>Attributes         </td>
          </tr>
          <tr>
             <td>Allow this account to login by email         </td>
             <td>authByEmail         </td>
             <td><code>false</code><br />
    <code>true</code>         </td>
          </tr>
          <tr>
             <td>(none)         </td>
             <td>unlicensed         </td>
             <td>Is this an unlicensed user account?<br />
    <code>false</code><br />
    <code>true</code><br />
             </td>
          </tr>
          <tr>
             <td>Allow reply to packages         </td>
             <td>isUnlicensedAllowedToReply         </td>
             <td><code>false</code><br />
    <code>true</code><br />
    Always <code>true</code> of licensed accounts.<br />
             </td>
          </tr>
          <tr>
             <td>(none)         </td>
             <td>disabled         </td>
             <td>Is this user account disabled?<br />
    <code>false</code><br />
    <code>true</code><br />
             </td>
          </tr>
          <tr>
             <td>Elements         </td>
          </tr>
          <tr>
             <td>Delivery Method         </td>
             <td>deliveryMethod         </td>
             <td><code>DISABLED</code><br />
    <code>DEFAULT</code><br />
    <code>ANONYMOUS</code><br />
    <code>ACCOUNT_WITHOUT_ENROLLEMENT</code><br />
    <code>ACCOUNT_WITH_ENROLLMENT</code><br />
    <code>CUSTOM</code>         </td>
          </tr>
          <tr>
             <td>Enrollment Types         </td>
             <td>enrollmentTypes         </td>
             <td><p>If deliveryMethod is CUSTOM:</p>
    <p><code>ANONYMOUS_LINK</code><br />
    <code>CHALLENGE_LINK</code><br />
    <code>EXISTING_ACCOUNT</code><br />
    <code>ENROLL_UNLICENSED</code><br />
    <code>ENROLL_LICENSED</code></p>         </td>
          </tr>
          <tr>
             <td>Implicit Enrollment Type         </td>
             <td>implicitEnrollmentType         </td>
             <td>One of the valid enrollment types. Do not include when the deliveryMethod is <code>DEFAULT</code> or the field value is None.         </td>
          </tr>
          <tr>
             <td>Home Folder Access         </td>
             <td>homeFolderAccessLevel         </td>
             <td><p><code>PRIVATE</code></p>
    <p><code>PUBLIC</code></p>
    <p><code>BUSINESSUNIT</code></p>         </td>
          </tr>
          <tr>
             <td>Custom properties         </td>
          </tr>
          <tr>
             <td>Encrypt Mode         </td>
             <td>encryptMode         </td>
             <td><p><code>unspecified</code></p>
    <p><code>enabled</code></p>         </td>
          </tr>
          <tr>
             <td>Routing Mode         </td>
             <td>routingMode         </td>
             <td><code>accept</code><br />
    <code>reject</code>
    <p><code>ignore</code></p>         </td>
          </tr>
          <tr>
             <td>Account Type         </td>
             <td>transferType         </td>
             <td><code>E</code><br />
    <code>I</code>
    <p><code>N</code></p>         </td>
          </tr>
          <tr>
             <td>Transfer Mode         </td>
             <td>transfersWebServiceAllowed         </td>
             <td><code>false</code><br />
    <code>true</code>         </td>
          </tr>
       </tbody>
    </table>

**Related topics:**

-   [Account XML schema](../c_st_account_xml_schema)
-   [Export and import accounts](../t_st_importandexportaccounts)
