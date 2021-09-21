{
    "title": "Single Sign-On with REST API (Enhanced Client or Proxy)",
    "linkTitle": "Single Sign-On with REST API (Enhanced Client or Proxy)",
    "weight": "80"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This example assumes both the Identity Provider and Service Provider are properly configured for Enhanced Client or Proxy (ECP) using basic authentication. For details, refer to the <a href="https://wiki.shibboleth.net/confluence/display/IDP30/Home">Shibboleth documentation</a>.         </td>
      </tr>
</table>

## Operating system and tools used

The following operating system and tools were used in this example:

-   Red Hat 7
-   curl - A tool for client-side URL transfers.
-   tempfile or mktemp - Utility for creating a temporary file to store cookies.

## Single Sign-On (SSO) authentication

1.  REST client – Will request authentication to the Service Provider > SecureTransport (The Service Provider).  
    Headers needed for ECP:

    -   `Accept:text/html; application/vnd.paos+xml`
    -   `PAOS:ver=\"urn:liberty:paos:2003-08\";\"urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp\"`

      
    Create a temp file where you can store the cookie.

    1.  mktemp
    2.  /cookieTemp- The created temp file where the cookies will be stored.

      
    **CURL GET** request to Service Provider:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -v -k -L -c /cookieTemp -b /cookieTemp -H "Accept:text/html; 
application/vnd.paos+xml" -H "PAOS:ver=\"urn:liberty:paos:2003-
08\";\"urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp\"" 
https://&lt;ServiceProvider IP&gt;:&lt;Service Provider PORT&gt;</pre>
         </td>
      </tr>
   </tbody>
</table>

      
    The Service Provider will return a SAML Request:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve"><span>&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;soap11:Envelope xmlns:soap11="http://schemas.xmlsoap.org/soap/envelope/"&gt;
  &lt;soap11:Header&gt;
    &lt;paos:Request xmlns:paos="urn:liberty:paos:2003-08" 
responseConsumerURL="&lt;The Response Consumer URL&gt;" 
service="urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp" 
soap11:actor="http://schemas.xmlsoap.org/soap/actor/next" 
soap11:mustUnderstand="1"/&gt;
    &lt;ecp:Request xmlns:ecp="urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp" 
soap11:actor="http://schemas.xmlsoap.org/soap/actor/next" 
soap11:mustUnderstand="1"&gt;
      &lt;saml2:Issuer xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"&gt;&lt;The 
SAML Issuer&gt;&lt;/saml2:Issuer&gt;
    &lt;/ecp:Request&gt;
  &lt;/soap11:Header&gt;
  &lt;soap11:Body&gt;
    &lt;saml2p:AuthnRequest xmlns:saml2p="urn:oasis:names:tc:SAML:2.0:protocol" 
Destination="&lt;IDP ENDPOINT&gt;" ForceAuthn="false" 
ID="id-30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f21df-
1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" IsPassive="false" 
IssueInstant="2017-04-06T16:47:20.431Z" 
ProtocolBinding="urn:oasis:names:tc:SAML:2.0:bindings:PAOS" Version="2.0"&gt;
      &lt;saml2:Issuer xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"&gt;&lt;The 
SAML Issuer&gt;&lt;/saml2:Issuer&gt;
      &lt;ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#"&gt;
        &lt;ds:SignedInfo&gt;
          &lt;ds:CanonicalizationMethod 
Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/&gt;
          &lt;ds:SignatureMethod 
Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"/&gt;
          &lt;ds:Reference URI="#id-30735cecb29da6728ca33a52b3428846550069245d37
a43d3cf562ef5e7f21df-1491497240411-b5e88519-3536-4294-b06f-df7deeec376a"&gt;
            &lt;ds:Transforms&gt;
              &lt;ds:Transform 
Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/&gt;
              &lt;ds:Transform 
Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/&gt;
            &lt;/ds:Transforms&gt;
            &lt;ds:DigestMethod 
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/&gt;
            &lt;ds:DigestValue/&gt;
          &lt;/ds:Reference&gt;
        &lt;/ds:SignedInfo&gt;
        &lt;ds:SignatureValue/&gt;
        &lt;ds:KeyInfo&gt;
          &lt;ds:X509Data&gt;</span></pre><pre xml:space="preserve"><span>            &lt;ds:X509Certificate&gt;
MIIDtzCCAp+gAwIBAgIBAjANBgkqhkiG9w0BAQsFADCBmTELMAkGA1UEAwwCY2ExCzAJBgNVBAYT 
AmNhMQswCQYDVQQKDAJjYTELMAkGA1UECwwCY2ExCzAJBgNVBAcMAmNhMQswCQYDVQQIDAJjYTFJ 
MEcGA1UEBRNANTU1MDQxZTZlZTcyMjY5OTRiZTQyMTI4YTE2ZjM5NjIwYWQ2OWEwZTFlNWFlYjY4 
NDQ1M2ZmNThjZTEyZDhlZTAeFw0xNzA0MDYxMjM5MzJaFw0xODA0MDYxMjM5MzJaMFIxDzANBgNV 
BAMMBnNzb2tleTELMAkGA1UEBhMCY2ExCzAJBgNVBAoMAmNhMQswCQYDVQQLDAJjYTELMAkGA1UE 
BwwCY2ExCzAJBgNVBAgMAmNhMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA2PIui/zG 
t6l2xm2uqhjdvFkJK1yELUKXYXbLI+uAQglgNfCfGg2qEmk6lulCytKu8UYB+4M4mkMlshwkxTQQ 
EUB+o5TATQKNrc6cT7PahdISnDF9AeGqpCr9OgndeMTFgA7LNAGBJZT/v5LgvvGiPbN/N31t9uEw 
jyFNFB6Ywpu0+9pBPfWb4++dske9b+leXS6N/nm3cyLRvYhggScnKcr+OU1AxQLJetKTWy7lDZcr 
jEGZiEsZc2pm8M5fFc0bUbaPvHjbqB2qNg9+nAVI2i0gHkUwFyd2cHER7p0HR9WdPOou+970SNCb 
SEDtF/yQ9Pk4HuzdVIAvxHX1IV4fWQIDAQABo1AwTjAMBgNVHRMBAf8EAjAAMB0GA1UdDgQWBBSo 
Srl4IyBmi053EURE3cN6YBgjozAfBgNVHSMEGDAWgBQnL3mdt9LybLMJRC8nrMcYi8NPgjANBgkq 
hkiG9w0BAQsFAAOCAQEAfL+GLxrULu3Qv6zzg7TeRZyikClgGVeEFn3rpckDov2aFKexvQq9ArsR 
CCygSvkfFS2EwvXrp9Q1i6prxDQB/cZJtQFdHYfxFT4nWFlmo28oMFWETzJnpMtANA/kt5WVg6Cb 
fR0+QZbC5gQhR4F2Pr/61CSzstm25YRHOhkEylqnLnxiil7dpJfntAYOrWqxdrlrmiGS/287H02v 
CAJWZ2em3jtSA1963Mi/ByvZZ1ZYUNNnzMwFnfEYFKdmJ4uEeTNc8+K6mjXZRZcoIwiT15v2rVwB 
cRm+iSo6mJw+Ah+zUASX+30tNj/+v75Y8NADzW6iS7ilfdmD7IKz27eLag==
           &lt;/ds:X509Certificate&gt;</span></pre><pre xml:space="preserve"><span>          &lt;/ds:X509Data&gt;
        &lt;/ds:KeyInfo&gt;
      &lt;/ds:Signature&gt;
      &lt;saml2:Conditions 
xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion" 
NotBefore="2017-04-06T16:47:20.431Z" 
NotOnOrAfter="2017-04-06T16:48:20.431Z"/&gt;
    &lt;/saml2p:AuthnRequest&gt;
  &lt;/soap11:Body&gt;
&lt;/soap11:Envelope&gt;</span></pre>
         </td>
      </tr>
   </tbody>
</table>

      
    We can save the Request in a temp file (`tmp.samlrequest`) and pass it as a parameter for the **POST** Request to the `IDP_ENDPOINT`:

2.  The SAML Request then needs to be sent to the Identity Provider so it can challenge the user for authentication.  
    The Identity Provider endpoint to which we need to send the SAML can be found in the SAML Request:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">&lt;saml2p:AuthnRequest 
xmlns:saml2p="urn:oasis:names:tc:SAML:2.0:protocol" 
Destination="&lt;IDP_ENDPOINT&gt;" ForceAuthn="false" ID="id-
30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f21df-
1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" 
IsPassive="false" IssueInstant="2017-04-06T16:47:20.431Z" 
ProtocolBinding="urn:oasis:names:tc:SAML:2.0:bindings:PAOS" 
Version="2.0"&gt;
</pre>
         </td>
      </tr>
   </tbody>
</table>

      
    The **POST** Request to the Identity Provider Endpoint  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -v -k --fail -X POST -H 'Content-Type: text/xml; charset=utf-
8' -c /cookieTemp -b /cookieTemp --user &lt;USERNAME&gt; -d 
"@/tmp.samlrequest" &lt;IDP_ENDPOINT&gt;</pre>
         </td>
      </tr>
   </tbody>
</table>

      
    The Identity Provider will challenge for authentication. After successful authentication, the Identity Provider will return a SOAP envelope, which then needs to be send to the Service Provider:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">&lt;?xml version="1.0"?&gt;
&lt;SOAP-ENV:Envelope xmlns:SOAP-
ENV="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ecp="urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp" 
xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" 
xmlns:samlp="urn:oasis:names:tc:SAML:2.0:protocol"&gt;
  &lt;SOAP-ENV:Header&gt;
    &lt;ecp:Response AssertionConsumerServiceURL="&lt;Assertion ConsumerService 
URL&gt;" SOAP-ENV:actor="http://schemas.xmlsoap.org/soap/actor/next" SOAP-
ENV:mustUnderstand="1"/&gt;
  &lt;/SOAP-ENV:Header&gt;
  &lt;SOAP-ENV:Body&gt;
</pre><pre xml:space="preserve">    &lt;samlp:Response Destination="&lt;Response Destination URL&gt;" 
ID="ID_5f5b3f52-7440-49ad-b9c2-d1513239e054" 
InResponseTo="id-
30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f21df-
1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" 
IssueInstant="2017-04-06T16:47:19.813Z" Version="2.0"&gt;
      &lt;saml:Issuer&gt;&lt;The SAML issuer&gt;&lt;/saml:Issuer&gt;
</pre><pre xml:space="preserve">      &lt;dsig:Signature xmlns:dsig="http://www.w3.org/2000/09/xmldsig#"&gt;
        &lt;dsig:SignedInfo&gt;
          &lt;dsig:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/&gt;
          &lt;dsig:SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"/&gt;
          &lt;dsig:Reference URI="#ID_5f5b3f52-7440-49ad-b9c2-d1513239e054"&gt;
            &lt;dsig:Transforms&gt;
              &lt;dsig:Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/&gt;
              &lt;dsig:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/&gt;
            &lt;/dsig:Transforms&gt;
            &lt;dsig:DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256"/&gt;
            &lt;dsig:DigestValue&gt;TMW8z+lkNsLH17DpOVDpVswbGwCdoa4DXSWEm5ERrNg=
&lt;/dsig:DigestValue&gt;
          &lt;/dsig:Reference&gt;
</pre><pre xml:space="preserve">        &lt;/dsig:SignedInfo&gt;
         &lt;dsig:SignatureValue&gt;
RWmMleH2nLausNmC4L9UN+lUiT7vYTMNgzBXXnDBukZTubISwCqrY/DSsrjlLS7tZvaodaGlSLM
+eJVimn0EgGHwj/3Vr6S8ohsOk+IzB5fHYpG8N7uoDadp6ILGwc7vU4bOK4L7zgorgaVN0Ofjmr
5sn5F1Rvh/sSmYUpbfX+3lhQzldXI0B7VpsISZAV9eum/c8HJGE/fvWz3kMneKxMB1b2p4wRNvy
ncuekoiKQ4YN/No3S7PKKFDcdaJV10m6CQUn8TsfJhmpDwot8PRkyqZmFUJXhoyT62oIBviC1Vo
oFxVBiJ7tWBeXKeJ1E15MuFtR8T2rLSll1Hvgwq1Nw==
         &lt;/dsig:SignatureValue&gt;
        &lt;dsig:KeyInfo&gt;
          &lt;dsig:KeyName&gt;tmx7e0gwvdLC4G9HTPegtqq9-elg2rhwg-sM7r7_RfM&lt;/dsig:KeyName&gt;
</pre><pre xml:space="preserve">          &lt;dsig:X509Data&gt;
            &lt;dsig:X509Certificate&gt;
MIICtTCCAZ0CBgFZx7DxnzANBgkqhkiG9w0BAQsFADAeMRwwGgYDVQQDDBNTZWN1cmVUcmFuc3Bv
cnQtc3NvMB4XDTE3MDEyMjE5Mzc1OVoXDTI3MDEyMjE5MzkzOVowHjEcMBoGA1UEAwwTU2VjdXJl
VHJhbnNwb3J0LXNzbzCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAJ9gyQLXAYXz9vBL
rxpX+Ti3yTbJ8CTy4H5B3dwWk9X1voaL9a3uEV0UR4AdsDq+6ExYroYEUgCjVJVywK7eNitZgxrG
bnEKjYsEt/ZXTOaW0V3VV+CVzGZqOBdRbqC4+BFXoH3Jba1fy3frZomPE1xHGiotceUlz7m7Etnf
fnCzblJhYQY4QPu94wTaVykULWA5CkgiRjDC+5OWsKcQ6C/kmkMgI9S4RCS7N6Apj7ILL3jCm/df
+hVlND3ZpYPdRZSavjTiX0L2hglXyn91Zju8ZIm6w8tQDE0vFwjF+9A+w0mnjp+0gtV5ISiCW/0s
K35xcgIsqF84XWQZyACG8VcCAwEAATANBgkqhkiG9w0BAQsFAAOCAQEAbbttR21ubHush5EsuVQj
LAIrsJyJTdodgFMUaOfUolFb7AHIlUWhUALjgWd/6S6KXwSdfPinE3NC9dmUY+S+bxkyDHrHzzib
cpsVaP8TK031PhjbTvH22RgGl77nqq3cRKfte+3Eqi45CqBKfEFMt8YsrAsIzW/T9oeMkLP0M8mw
RO9x280UID+rqSsKseAIFUE2Pxc/YBGID2qbIDKM5NI97ALbxhts3b2GW1PiCyDo8EIq2DlJXWEs
vzCkavfmN/lmx5YvjviXGdzKw7r5KWyKPVoCePtlZc/fcBRk4dZPUFWW6NlA7liRqzAEi7KJvPGL
yfD5rbAwatPnbOW40Q==
           &lt;/dsig:X509Certificate&gt;
          &lt;/dsig:X509Data&gt;
          &lt;dsig:KeyValue&gt;
</pre><pre xml:space="preserve">            &lt;dsig:RSAKeyValue&gt;
              &lt;dsig:Modulus&gt;
n2DJAtcBhfP28EuvGlf5OLfJNsnwJPLgfkHd3BaT1fW+hov1re4RXRRHgB2wOr7oTFiuhgRSAKNU
lXLArt42K1mDGsZucQqNiwS39ldM5pbRXdVX4JXMZmo4F1FuoLj4EVegfcltrV/Ld+tmiY8TXEca
Ki1x5SXPubsS2d9+cLNuUmFhBjhA+73jBNpXKRQtYDkKSCJGMML7k5awpxDoL+SaQyAj1LhEJLs3
oCmPsgsveMKb91/6FWU0Pdmlg91FlJq+NOJfQvaGCVfKf3VmO7xkibrDy1AMTS8XCMX70D7DSaeO
n7SC1XkhKIJb/SwrfnFyAiyoXzhdZBnIAIbxVw==
               &lt;/dsig:Modulus&gt;
</pre><pre xml:space="preserve">              &lt;dsig:Exponent&gt;AQAB&lt;/dsig:Exponent&gt;
            &lt;/dsig:RSAKeyValue&gt;
          &lt;/dsig:KeyValue&gt;
        &lt;/dsig:KeyInfo&gt;
      &lt;/dsig:Signature&gt;
</pre><pre xml:space="preserve">      &lt;samlp:Status&gt;
        &lt;samlp:StatusCode 
Value="urn:oasis:names:tc:SAML:2.0:status:Success"/&gt;
      &lt;/samlp:Status&gt;
      &lt;saml:Assertion xmlns="urn:oasis:names:tc:SAML:2.0:assertion" 
ID="ID_f36812f5-66ce-4b30-88fc-f8e0071b1587" 
IssueInstant="2017-04-06T16:47:19.812Z" Version="2.0"&gt;
        &lt;saml:Issuer&gt;&lt;The SAML issuer&gt;&lt;/saml:Issuer&gt;
        &lt;saml:Subject&gt;
          &lt;saml:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:
unspecified"&gt;kmanchev&lt;/saml:NameID&gt;
          &lt;saml:SubjectConfirmation 
Method="urn:oasis:names:tc:SAML:2.0:cm:bearer"&gt;
            &lt;saml:SubjectConfirmationData 
InResponseTo="id-30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f
21df-1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" NotOnOrAfter="2017-
04-06T16:52:17.812Z" 
Recipient="&lt;Response Destination URL&gt;"/&gt;
          &lt;/saml:SubjectConfirmation&gt;
        &lt;/saml:Subject&gt;
        &lt;saml:Conditions NotBefore="2017-04-06T16:47:17.812Z" 
NotOnOrAfter="2017-04-06T16:48:17.812Z"&gt;
          &lt;saml:AudienceRestriction&gt;
            &lt;saml:Audience&gt;koce-admin-10.134.64.151&lt;/saml:Audience&gt;
          &lt;/saml:AudienceRestriction&gt;
        &lt;/saml:Conditions&gt;
        &lt;saml:AuthnStatement AuthnInstant="2017-04-06T16:47:19.813Z" 
SessionIndex="f414258a-df9b-43c7-a8cf-11edfe78a423"&gt;
          &lt;saml:AuthnContext&gt;
            &lt;saml:AuthnContextClassRef&gt;urn:oasis:names:tc:SAML:2.0:ac:
classes:unspecified
&lt;/saml:AuthnContextClassRef&gt;
          &lt;/saml:AuthnContext&gt;
        &lt;/saml:AuthnStatement&gt;
        &lt;saml:AttributeStatement&gt;
          &lt;saml:Attribute Name="email" 
NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic"&gt;
            &lt;saml:AttributeValue 
xmlns:xs="http://www.w3.org/2001/XMLSchema" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
xsi:type="xs:string"&gt;kmanchev@st1.lab.sofi.axway.int&lt;/saml:AttributeValue&gt;
          &lt;/saml:Attribute&gt;
          &lt;saml:Attribute Name="Role" 
NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic"&gt;
            &lt;saml:AttributeValue 
xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
xsi:type="xs:string"&gt;manage-account&lt;/saml:AttributeValue&gt;
          &lt;/saml:Attribute&gt;
          &lt;saml:Attribute Name="Role" 
NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic"&gt;
            &lt;saml:AttributeValue xmlns:xs="http://www.w3.org/2001/XMLSchema" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
xsi:type="xs:string"&gt;uma_authorization&lt;/saml:AttributeValue&gt;
          &lt;/saml:Attribute&gt;
          &lt;saml:Attribute Name="Role" 
NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic"&gt;
            &lt;saml:AttributeValue 
xmlns:xs="http://www.w3.org/2001/XMLSchema" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:type="xs:string"&gt;view-profile&lt;/saml:AttributeValue&gt;
          &lt;/saml:Attribute&gt;
        &lt;/saml:AttributeStatement&gt;
      &lt;/saml:Assertion&gt;
    &lt;/samlp:Response&gt;
  &lt;/SOAP-ENV:Body&gt;
&lt;/SOAP-ENV:Envelope&gt;
</pre>
         </td>
      </tr>
   </tbody>
</table>

      
    We can save the Response in a temp file `(tmp.idpreponse`) and pass it as a parameter for the **POST** Request to the Service Provider.   
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">We need to compare the <code>responseConsumerURL</code> from the Service Provider to the <code>assertionConsumerServiceURL</code> from the Identity Provider. If they are not identical, we need to send a SOAP fault to the Service Provider.         </td>
      </tr>
</table>

      
    Payload:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">&lt;S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/"&gt;
&lt;S:Body&gt;
&lt;S:Fault&gt;
&lt;faultcode&gt;
S:Server&lt;/faultcode&gt;
&lt;faultstring&gt;responseConsumerURL from SP and 
assertionConsumerServiceURL from IdP do not match&lt;/faultstring&gt;
&lt;/S:Fault&gt;
&lt;/S:Body&gt;
&lt;/S:Envelope&gt;</pre>
         </td>
      </tr>
   </tbody>
</table>

      
    The payload can be saved to a file (`fault_payload`) and used in the **POST** request:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -v -k -X POST -c /cookieTemp -b /cookieTemp -d "@/fault_
payload" -H "Content-Type: application/vnd.paos+xml" &lt;The Response 
Consumer URL&gt;
</pre>
         </td>
      </tr>
   </tbody>
</table>

3.  After successful authentication and check if `responseConsumerURL` from the Service Provideer and the `assertionConsumerServiceURL` from the Identity Provide are identical, we are ready to send the Identity Provider Payload to the Service Provider:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -v -k -s -c /cookieTemp -b /cookieTemp -X POST -d 
"@/tmp.idpreponse" -H "Content-Type: application/vnd.paos+xml" 
&lt;Assertion ConsumerService URL&gt;
</pre>
         </td>
      </tr>
   </tbody>
</table>

      
    The session should now be established.

4.  You can try to access the original resource to check if the authentication was successful:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -k -v -L -e "https://&lt;ServiceProvider IP&gt;:&lt;Service Provider 
PORT&gt;" -c /cookieTemp -b /cookieTemp -H "Accept: application/json" 
https://&lt;ServiceProvider IP&gt;:&lt;Service Provider PORT&gt;
</pre>
         </td>
      </tr>
   </tbody>
</table>

## Single Sign-Off (SSO) logout

Administrator logout:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -v -k -L -c /cookieTemp -b /cookieTemp -D - -X GET 
https://&lt;ServiceProvider IP&gt;:&lt;Service Provider PORT&gt;/coreadmin/logout
</pre>
         </td>
      </tr>
   </tbody>
</table>

End-user logout:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">curl -v -k -L -c /cookieTemp -b /cookieTemp -D - -H "Referer:*" -X 
DELETE https://&lt;ServiceProvider IP&gt;:&lt;Service Provider 
PORT&gt;/api/v1.4/myself
</pre>
         </td>
      </tr>
   </tbody>
</table>

After the logout is performed, the session and session cookies are expired.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For logout , <span>SecureTransport</span> uses Redirect Bindings, so in order for the logout to work:         </td>
      </tr>
</table>

-   Single Logout (SLO) needs to be configured with **Redirect** binding. In the SecureTransport SSO configuration, the **Redirect** binding must be before the **POST** binding.
-   The *Force POST Binding* option must be disabled for Keycloak.

### Login recap

**CLIENT** - **Requests** the `/` of the SecureTransport (Service Provider) → **SecureTransport (Service Provider)**

**CLIENT** ← **Responds** with SAML Request envelope - **SecureTransport (Service Provider)**

**CLIENT** - **Sends** the SAML Request from the Service provider to the Identity Provider → **Identity Provider (Keycloak/Shibboleth)**

**CLIENT** ← **Challenges** the Client for authentication - **Identity Provider (Keycloak/Shibboleth)**

**CLIENT** - **Authenticates** correctly → **Identity Provider (Keycloak/Shibboleth)**

**CLIENT** ← **Responds** with Identity Provider Response - **Identity Provider (Keycloak/Shibboleth)**

**CLIENT** - **Sends** the IDP Response to the Service Provider → **SecureTransport (Service Provider)**

The Service provider sets the Session cookies and the session is established.

### Logout recap

**CLIENT** - **Requests** logout (if EndUser - will perform **DELETE**) → **SecureTransport (Service Provider)**

**CLIENT** ← **Responds** with Logout SAML Request- **SecureTransport (Service Provider)**

**CLIENT** - **Sends** Logout SAML Request → **Identity Provider (Keycloak/Shibboleth)**

**CLIENT** ← **Responds** with Logout SAML Response - **Identity Provider (Keycloak/Shibboleth)**

**CLIENT** - **Sends** the Logout SAML Response from the IDP to confirm that the logout was successul → **SecureTransport (Service Provider)**
