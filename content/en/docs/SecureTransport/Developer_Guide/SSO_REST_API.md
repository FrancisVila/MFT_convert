{
    "title": "Single Sign-On with REST API (Enhanced Client or Proxy)",
    "linkTitle": "Single Sign-On with REST API (Enhanced Client or Proxy)",
    "weight": "80"
}> **Note:**
>
> This example assumes both the Identity Provider and Service Provider are properly configured for Enhanced Client or Proxy (ECP) using basic authentication. For details, refer to the Shibboleth documentation.

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


        curl -v -k -L -c /cookieTemp -b /cookieTemp -H "Accept:text/html; 
        application/vnd.paos+xml" -H "PAOS:ver=\"urn:liberty:paos:2003-
        08\";\"urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp\"" 
        https://<ServiceProvider IP>:<Service Provider PORT>

      
    The Service Provider will return a SAML Request:  




      
    We can save the Request in a temp file (`tmp.samlrequest`) and pass it as a parameter for the **POST** Request to the `IDP_ENDPOINT`:

2.  The SAML Request then needs to be sent to the Identity Provider so it can challenge the user for authentication.  
    The Identity Provider endpoint to which we need to send the SAML can be found in the SAML Request:  


        <saml2p:AuthnRequest 
        xmlns:saml2p="urn:oasis:names:tc:SAML:2.0:protocol" 
        Destination="<IDP_ENDPOINT>" ForceAuthn="false" ID="id-
        30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f21df-
        1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" 
        IsPassive="false" IssueInstant="2017-04-06T16:47:20.431Z" 
        ProtocolBinding="urn:oasis:names:tc:SAML:2.0:bindings:PAOS" 
        Version="2.0">

      
    The **POST** Request to the Identity Provider Endpoint  


        curl -v -k --fail -X POST -H 'Content-Type: text/xml; charset=utf-
        8' -c /cookieTemp -b /cookieTemp --user <USERNAME> -d 
        "@/tmp.samlrequest" <IDP_ENDPOINT>

      
    The Identity Provider will challenge for authentication. After successful authentication, the Identity Provider will return a SOAP envelope, which then needs to be send to the Service Provider:  


        <?xml version="1.0"?>
        <SOAP-ENV:Envelope xmlns:SOAP-
        ENV="http://schemas.xmlsoap.org/soap/envelope/" 
        xmlns:ecp="urn:oasis:names:tc:SAML:2.0:profiles:SSO:ecp" 
        xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" 
        xmlns:samlp="urn:oasis:names:tc:SAML:2.0:protocol">
          <SOAP-ENV:Header>
            <ecp:Response AssertionConsumerServiceURL="<Assertion ConsumerService 
        URL>" SOAP-ENV:actor="http://schemas.xmlsoap.org/soap/actor/next" SOAP-
        ENV:mustUnderstand="1"/>
          </SOAP-ENV:Header>
          <SOAP-ENV:Body>
            <samlp:Response Destination="<Response Destination URL>" 
        ID="ID_5f5b3f52-7440-49ad-b9c2-d1513239e054" 
        InResponseTo="id-
        30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f21df-
        1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" 
        IssueInstant="2017-04-06T16:47:19.813Z" Version="2.0">
              <saml:Issuer><The SAML issuer></saml:Issuer>
              <dsig:Signature xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
                <dsig:SignedInfo>
                  <dsig:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
                  <dsig:SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"/>
                  <dsig:Reference URI="#ID_5f5b3f52-7440-49ad-b9c2-d1513239e054">
                    <dsig:Transforms>
                      <dsig:Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
                      <dsig:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
                    </dsig:Transforms>
                    <dsig:DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256"/>
                    <dsig:DigestValue>TMW8z+lkNsLH17DpOVDpVswbGwCdoa4DXSWEm5ERrNg=
        </dsig:DigestValue>
                  </dsig:Reference>
                </dsig:SignedInfo>
                 <dsig:SignatureValue>
        RWmMleH2nLausNmC4L9UN+lUiT7vYTMNgzBXXnDBukZTubISwCqrY/DSsrjlLS7tZvaodaGlSLM
        +eJVimn0EgGHwj/3Vr6S8ohsOk+IzB5fHYpG8N7uoDadp6ILGwc7vU4bOK4L7zgorgaVN0Ofjmr
        5sn5F1Rvh/sSmYUpbfX+3lhQzldXI0B7VpsISZAV9eum/c8HJGE/fvWz3kMneKxMB1b2p4wRNvy
        ncuekoiKQ4YN/No3S7PKKFDcdaJV10m6CQUn8TsfJhmpDwot8PRkyqZmFUJXhoyT62oIBviC1Vo
        oFxVBiJ7tWBeXKeJ1E15MuFtR8T2rLSll1Hvgwq1Nw==
                 </dsig:SignatureValue>
                <dsig:KeyInfo>
                  <dsig:KeyName>tmx7e0gwvdLC4G9HTPegtqq9-elg2rhwg-sM7r7_RfM</dsig:KeyName>
                  <dsig:X509Data>
                    <dsig:X509Certificate>
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
                   </dsig:X509Certificate>
                  </dsig:X509Data>
                  <dsig:KeyValue>
                    <dsig:RSAKeyValue>
                      <dsig:Modulus>
        n2DJAtcBhfP28EuvGlf5OLfJNsnwJPLgfkHd3BaT1fW+hov1re4RXRRHgB2wOr7oTFiuhgRSAKNU
        lXLArt42K1mDGsZucQqNiwS39ldM5pbRXdVX4JXMZmo4F1FuoLj4EVegfcltrV/Ld+tmiY8TXEca
        Ki1x5SXPubsS2d9+cLNuUmFhBjhA+73jBNpXKRQtYDkKSCJGMML7k5awpxDoL+SaQyAj1LhEJLs3
        oCmPsgsveMKb91/6FWU0Pdmlg91FlJq+NOJfQvaGCVfKf3VmO7xkibrDy1AMTS8XCMX70D7DSaeO
        n7SC1XkhKIJb/SwrfnFyAiyoXzhdZBnIAIbxVw==
                       </dsig:Modulus>
                      <dsig:Exponent>AQAB</dsig:Exponent>
                    </dsig:RSAKeyValue>
                  </dsig:KeyValue>
                </dsig:KeyInfo>
              </dsig:Signature>
              <samlp:Status>
                <samlp:StatusCode 
        Value="urn:oasis:names:tc:SAML:2.0:status:Success"/>
              </samlp:Status>
              <saml:Assertion xmlns="urn:oasis:names:tc:SAML:2.0:assertion" 
        ID="ID_f36812f5-66ce-4b30-88fc-f8e0071b1587" 
        IssueInstant="2017-04-06T16:47:19.812Z" Version="2.0">
                <saml:Issuer><The SAML issuer></saml:Issuer>
                <saml:Subject>
                  <saml:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:
        unspecified">kmanchev</saml:NameID>
                  <saml:SubjectConfirmation 
        Method="urn:oasis:names:tc:SAML:2.0:cm:bearer">
                    <saml:SubjectConfirmationData 
        InResponseTo="id-30735cecb29da6728ca33a52b3428846550069245d37a43d3cf562ef5e7f
        21df-1491497240411-b5e88519-3536-4294-b06f-df7deeec376a" NotOnOrAfter="2017-
        04-06T16:52:17.812Z" 
        Recipient="<Response Destination URL>"/>
                  </saml:SubjectConfirmation>
                </saml:Subject>
                <saml:Conditions NotBefore="2017-04-06T16:47:17.812Z" 
        NotOnOrAfter="2017-04-06T16:48:17.812Z">
                  <saml:AudienceRestriction>
                    <saml:Audience>koce-admin-10.134.64.151</saml:Audience>
                  </saml:AudienceRestriction>
                </saml:Conditions>
                <saml:AuthnStatement AuthnInstant="2017-04-06T16:47:19.813Z" 
        SessionIndex="f414258a-df9b-43c7-a8cf-11edfe78a423">
                  <saml:AuthnContext>
                    <saml:AuthnContextClassRef>urn:oasis:names:tc:SAML:2.0:ac:
        classes:unspecified
        </saml:AuthnContextClassRef>
                  </saml:AuthnContext>
                </saml:AuthnStatement>
                <saml:AttributeStatement>
                  <saml:Attribute Name="email" 
        NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic">
                    <saml:AttributeValue 
        xmlns:xs="http://www.w3.org/2001/XMLSchema" 
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
        xsi:type="xs:string">kmanchev@st1.lab.sofi.axway.int</saml:AttributeValue>
                  </saml:Attribute>
                  <saml:Attribute Name="Role" 
        NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic">
                    <saml:AttributeValue 
        xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
        xsi:type="xs:string">manage-account</saml:AttributeValue>
                  </saml:Attribute>
                  <saml:Attribute Name="Role" 
        NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic">
                    <saml:AttributeValue xmlns:xs="http://www.w3.org/2001/XMLSchema" 
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
        xsi:type="xs:string">uma_authorization</saml:AttributeValue>
                  </saml:Attribute>
                  <saml:Attribute Name="Role" 
        NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:basic">
                    <saml:AttributeValue 
        xmlns:xs="http://www.w3.org/2001/XMLSchema" 
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:type="xs:string">view-profile</saml:AttributeValue>
                  </saml:Attribute>
                </saml:AttributeStatement>
              </saml:Assertion>
            </samlp:Response>
          </SOAP-ENV:Body>
        </SOAP-ENV:Envelope>

      
    We can save the Response in a temp file `(tmp.idpreponse`) and pass it as a parameter for the **POST** Request to the Service Provider.  

    > **Note:**
    >
    > We need to compare the responseConsumerURL from the Service Provider to the assertionConsumerServiceURL from the Identity Provider. If they are not identical, we need to send a SOAP fault to the Service Provider.

      
    Payload:  


        <S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">
        <S:Body>
        <S:Fault>
        <faultcode>
        S:Server</faultcode>
        <faultstring>responseConsumerURL from SP and 
        assertionConsumerServiceURL from IdP do not match</faultstring>
        </S:Fault>
        </S:Body>
        </S:Envelope>

      
    The payload can be saved to a file (`fault_payload`) and used in the **POST** request:  


        curl -v -k -X POST -c /cookieTemp -b /cookieTemp -d "@/fault_
        payload" -H "Content-Type: application/vnd.paos+xml" <The Response 
        Consumer URL>

3.  After successful authentication and check if `responseConsumerURL` from the Service Provideer and the `assertionConsumerServiceURL` from the Identity Provide are identical, we are ready to send the Identity Provider Payload to the Service Provider:  


        curl -v -k -s -c /cookieTemp -b /cookieTemp -X POST -d 
        "@/tmp.idpreponse" -H "Content-Type: application/vnd.paos+xml" 
        <Assertion ConsumerService URL>

      
    The session should now be established.

4.  You can try to access the original resource to check if the authentication was successful:  


        curl -k -v -L -e "https://<ServiceProvider IP>:<Service Provider 
        PORT>" -c /cookieTemp -b /cookieTemp -H "Accept: application/json" 
        https://<ServiceProvider IP>:<Service Provider PORT>

## Single Sign-Off (SSO) logout

Administrator logout:


    curl -v -k -L -c /cookieTemp -b /cookieTemp -D - -X GET 
    https://<ServiceProvider IP>:<Service Provider PORT>/coreadmin/logout

End-user logout:


    curl -v -k -L -c /cookieTemp -b /cookieTemp -D - -H "Referer:*" -X 
    DELETE https://<ServiceProvider IP>:<Service Provider 
    PORT>/api/v1.4/myself

After the logout is performed, the session and session cookies are expired.

> **Note:**
>
> For logout , SecureTransport uses Redirect Bindings, so in order for the logout to work:

-   Single Logout (SLO) needs to be configured with **Redirect** binding. In the {{< SecureTransport/componentshortname >}} SSO configuration, the **Redirect** binding must be before the **POST** binding.
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
