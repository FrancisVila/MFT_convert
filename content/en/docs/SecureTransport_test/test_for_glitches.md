{
    "title": "Test for glitches",
    "linkTitle": "Test for glitches",
    "weight": "30"
}

AAAAAAAAAAAA
\<pre>  \<strong>POST\</strong>\<code>/api/v1.4/mailbox/messages\</code>
POST DATA:
\<code>to=petya\@sofia-pso.tumbleweed.com&amp;cc=&lt;group_entry_id&gt;&amp;bcc=&lt;user_entry_id&gt;&amp;subject=from+api&amp;messag
e=sample+message&amp;security=ANONYMOUS_LINK&amp;question=+What+is+the+name+of+your+best+friend+from+childhood%3F+&amp;answer=&amp;ex
piration=86400\</code>
RESPONSE: http://10.232.3.211:8080/api/v1.4/mailbox/messages 200 OK
Headers Response body {  \"info\": \"Draft was successfully created\",
 \"messageId\": \"6a5467d4a084445687b1cdc0cd11f3a3\" } \</pre>

1111111111

\<pre> &lt;account authByEmail=\"false\" unlicensed=\"false\"
    isUnlicensedAllowedToReply=\"true\" disabled=\"false\" &gt;    
&lt;name&gt;partner1&lt;/name&gt;     &lt;type&gt;user&lt;/type&gt;
    &lt;usrid&gt;1001&lt;/usrid&gt;     &lt;grpid&gt;1003&lt;/grpid&gt;
    &lt;homeFolder&gt;/home/users/partner1&lt;/homeFolder&gt;
    &lt;homeFolderAccessLevel&gt;PUBLIC&lt;/homeFolderAccessLevel&gt;
    &lt;email&gt;partner1\@example.com&lt;/email&gt;
    &lt;phone&gt;800-555-0199&lt;/phone&gt;
    &lt;htmlTemplateFolderPath&gt;/html/skin/ric&lt;/htmlTemplate
FolderPath&gt;     &lt;notes&gt;Include ad hoc file transfer
functions.&lt;/notes&gt;
    &lt;deliveryMethod&gt;CUSTOM&lt;/deliveryMethod&gt;
    &lt;enrollmentTypes&gt;CHALLENGED_LINK&lt;/enrollmentTypes&gt;
    &lt;implicitEnrollmentType&gt;EXISTING_ACCOUNT&lt;/implicitEnrollmentType&gt;
    &lt;customAttributes&gt;         &lt;customProperties&gt;
            &lt;entry key=\"encryptMode\"&gt;unspecified&lt;/entry&gt;
            &lt;entry key=\"routingMode\"&gt;reject&lt;/entry&gt;
            &lt;entry key=\"transferType\"&gt;E&lt;/entry&gt;
            &lt;entry
key=\"transfersWebServiceAllowed\"&gt;false&lt;/entry&gt;
        &lt;/customProperties&gt;         &lt;localCertificates&gt;
        &lt;/localCertificates&gt;         &lt;partnerCertificates&gt;
        &lt;/partnerCertificates&gt;         &lt;userCertificates&gt;
        &lt;/userCertificates&gt;     &lt;/customAttributes&gt;
&lt;/account&gt; \</pre>

22222222

::: indentTable
\<pre> AddressBookEntry {     id:
addressBookSourceId:addressBookEntryId,     displayName,     mail,
    parentGroup,     type,     customAttr1,     customAttr2,
    customAttr3 } \</pre>
:::

**Note:**





```
 &lt;strong&gt;POST&lt;/strong&gt;&lt;code&gt;/api/v1.4/mailbox/messages&lt;/code&gt;
POST DATA:
&lt;code&gt;to=petya@sofia-pso.tumbleweed.com&amp;amp;cc=&amp;lt;group_entry_id&amp;gt;&amp;amp;bcc=&amp;lt;user_entry_id&amp;gt;&amp
;amp;subject=from+api&amp;amp;message=sample+message&amp;amp;security=ANONYMOUS_LINK&amp;amp;question=+What+is+the+name+of+your+best+
friend+from+childhood%3F+&amp;amp;answer=&amp;amp;expiration=86400&lt;/code&gt;
RESPONSE:
http://10.232.3.211:8080/api/v1.4/mailbox/messages
200 OK
Headers
Response body
{
 "info": "Draft was successfully created",
 "messageId": "6a5467d4a084445687b1cdc0cd11f3a3"
}```

<p>1111111111</p>

```

        &amp;lt;account authByEmail="false" unlicensed="false"
    isUnlicensedAllowedToReply="true" disabled="false" &amp;gt;
    &amp;lt;name&amp;gt;partner1&amp;lt;/name&amp;gt;
    &amp;lt;type&amp;gt;user&amp;lt;/type&amp;gt;
    &amp;lt;usrid&amp;gt;1001&amp;lt;/usrid&amp;gt;
    &amp;lt;grpid&amp;gt;1003&amp;lt;/grpid&amp;gt;
    &amp;lt;homeFolder&amp;gt;/home/users/partner1&amp;lt;/homeFolder&amp;gt;
    &amp;lt;homeFolderAccessLevel&amp;gt;PUBLIC&amp;lt;/homeFolderAccessLevel&amp;gt;
    &amp;lt;email&amp;gt;partner1@example.com&amp;lt;/email&amp;gt;
    &amp;lt;phone&amp;gt;800-555-0199&amp;lt;/phone&amp;gt;
    &amp;lt;htmlTemplateFolderPath&amp;gt;/html/skin/ric&amp;lt;/htmlTemplate
FolderPath&amp;gt;
    &amp;lt;notes&amp;gt;Include ad hoc file transfer functions.&amp;lt;/notes&amp;gt;
    &amp;lt;deliveryMethod&amp;gt;CUSTOM&amp;lt;/deliveryMethod&amp;gt;
    &amp;lt;enrollmentTypes&amp;gt;CHALLENGED_LINK&amp;lt;/enrollmentTypes&amp;gt;
    &amp;lt;implicitEnrollmentType&amp;gt;EXISTING_ACCOUNT&amp;lt;/implicitEnrollmentType&amp;gt;
    &amp;lt;customAttributes&amp;gt;
        &amp;lt;customProperties&amp;gt;
            &amp;lt;entry key="encryptMode"&amp;gt;unspecified&amp;lt;/entry&amp;gt;
            &amp;lt;entry key="routingMode"&amp;gt;reject&amp;lt;/entry&amp;gt;
            &amp;lt;entry key="transferType"&amp;gt;E&amp;lt;/entry&amp;gt;
            &amp;lt;entry key="transfersWebServiceAllowed"&amp;gt;false&amp;lt;/entry&amp;gt;
        &amp;lt;/customProperties&amp;gt;
        &amp;lt;localCertificates&amp;gt;
        &amp;lt;/localCertificates&amp;gt;
        &amp;lt;partnerCertificates&amp;gt;
        &amp;lt;/partnerCertificates&amp;gt;
        &amp;lt;userCertificates&amp;gt;
        &amp;lt;/userCertificates&amp;gt;
    &amp;lt;/customAttributes&amp;gt;
&amp;lt;/account&amp;gt;
```

<p>22222222</p>
<div class="indentTable">

```

AddressBookEntry {
    id: addressBookSourceId:addressBookEntryId,
    displayName,
    mail,
    parentGroup,
    type,
    customAttr1,
    customAttr2,
    customAttr3
}
```




-   Enter the following commands to run the Axway Installer:

        ./setup.sh -m console

-   Press Enter.  
    The installer will display the license agreement page by page.
    After each one there is a **Press ENTER to continue** prompt.
    After all license agreement pages are displayed, the installer displays the license agreement and the following prompt (for accepting or rejecting the license agreement):

        [1] I accept the terms of the license agreement.
        [2] I do not accept the terms of the license agreement.
        Enter a number [1-2] to select an option or (Previous, Quit).
        :>2

-   AAA Note: All certificates need to be regenerated and DB configuration updated prior to certificates' expiration.

-     
      

-   The installer displays the default SecureTransport ports, nightly log rotation, and import secret file configuration:

        ----------------------------------------
        Configuration
        ----------------------------------------
          Select the options that you want to enable:
          SecureTransport Ports
        1: SSL Admin UI Port:           444
        2: Tomcat Shutdown Port:        8005
        3: Enable Nightly Log Rotation: true
          Import Secret File
        To synchronize the configuration of this ST Server with another ST Server you
                                        must import the same secret file (located on the remote ST Server at:
                                        <installation path>/bin/taeh). Otherwise, leave the field empty
                                        to generate a new secret file.
        4: Secret File Path:

                  

                                    Enter a number [1-4] to select an option or (Next, Previous, Quit).
        :>Next

-   Accept or modify the default configuration.  
    The information required is:
    -   **SSL Admin UI Port** – The port used to connect to the Administration Tool. When you install SecureTransport as a non-root user, the default value for Admin port number is 8444.
    -   **Tomcat Shutdown Port** – The port used to shut down the Tomcat server
    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, SecureTransport Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation. For more information, see the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>, Server Log Rotation Scheduling.
    -   **Secret File Path** – The path to the secret file you copied from another SecureTransport Server installation to this system, if blank, the installer creates a secret file (See [Secret file](secret_file.htm#beforeinstallst_3365039947_1107715).)
