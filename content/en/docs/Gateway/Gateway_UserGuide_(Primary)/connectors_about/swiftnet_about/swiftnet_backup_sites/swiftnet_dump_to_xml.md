{
    "title": "SWIFTNet dump to XML",
    "linkTitle": "SWIFTNet dump to XML",
    "weight": "320"
}{{< Gateway/componentlongname  >}}: Connectors

Gateway dumps certain key elements from the communication with SWIFT to the `sw_add_param` XML file. This topic contains examples of files for the following elements:

-   [HeaderInfo](#HeaderInfo)
-   [SignatureList](#SignatureList)
-   [Recipient List](#RecipientList)
-   [File or Message Copy](#FileCopy)
-   [Delivery notification (SnF)](#DeliveryNotif)
-   [Delivery notification (RealTime)](#Example)
-   [Authorization System Message (xsys.002.001.01)](#Example2)
-   [Refusal System Message (xsys.003.001.01)](#Example3)
-   [Delivery Notification System Message (xsys.011.001.01)](#Example4)
-   [Failed Delivery Notification System Message (xsys.012.001.01)](#Example5)

<span id="HeaderInfo"></span>

## Example of XML file containing HeaderInfo

Gateway supports the service profiles supported by SWIFT.


    <AddSwParams>
      <SwHeaderInfo>
      <Out>
      <ApplSpcfc xmlns="urn:swift:xsd:ApplSpcfc.TxsCntr.01">
      <TxsCntr>
      <TtlNbOfTxs>650</TtlNbOfTxs>
      </TxsCntr>
      </ApplSpcfc>
      </Out>
      </SwHeaderInfo>
    </AddSwParams>
     
    <AddSwParams>
      <SwHeaderInfo>
      <Out>
      <ApplSpcfc xmlns="urn:swift:xsd:ApplSpcfc.PmtSummry.01">
      <PmtSummry>
      <TtlIntrBkSttlmAmt Ccy="RON">768900</TtlIntrBkSttlmAmt>
      <TtlNbOfTxs>1467</TtlNbOfTxs>
      <CdtDbtInd>CRDT</CdtDbtInd>
      <IntrBkSttlmDt>2008-05-09</IntrBkSttlmDt>
      <FileId>OurFile</FileId>
      </PmtSummry>
      </ApplSpcfc>
      </Out>
      </SwHeaderInfo>
    </AddSwParams>
     
    <AddSwParams>
      <SwHeaderInfo>
      <Out>
      <ApplSpcfc xmlns = "urn:swift:xsd:ApplSpcfc.BAM.01">
      <FileTrfHdrBAM>
      <File>
      <Tp>terms</Tp>
      <Nm> BankTermsConditions.pdf </Nm>
      </File>
      <File>
      <Tp>passport</Tp>
      <Nm> Passport.jpg </Nm>
      </File>
      </FileTrfHdrBAM>
      </ApplSpcfc>
      </Out>
      </SwHeaderInfo>
    </AddSwParams>
     
    <AddSwParams>
      <SwHeaderInfo>
      <Out>
      <ApplSpcfc xmlns = "urn:swift:xsd:ApplSpcfc.Trade.01">
      <FileHdrTrfTrad>
      <Doc>
      <Nm>SiemensScannedDocs.zip</Nm>
      <Ref>WQ667589A-20100519</Ref>
      </Doc>
      </FileHdrTrfTrad>
      </ApplSpcfc>
      </Out>
      </SwHeaderInfo>
      </AddSwParams>

<span id="SignatureList"></span>

## Examples of XML files containing SignatureList

### SignatureList – FileAct PUT Request – Initiator


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Put.Request and RND</Sw:DigestRef>
      </Sw:Reference>
      <Sw:Reference>
      <Sw:DigestRef>Sw.FARequestHeader</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct PUT Request – Responder


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Put.Response</Sw:DigestRef>
      </Sw:Reference>
      <Sw:Reference>
      <Sw:DigestRef>Sw.FAResponseHeader</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct GET Request – Initiator


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Get.Request</Sw:DigestRef>
      </Sw:Reference>
      <Sw:Reference>
      <Sw:DigestRef>Sw.FARequestHeader</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct GET Request – Responder


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Get.Response</Sw:DigestRef>
      </Sw:Reference>
      <Sw:Reference>
      <Sw:DigestRef>Sw.FAResponseHeader</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct SnF – Sender


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Put.Request</Sw:DigestRef>
      </Sw:Reference>
      <Sw:Reference>
      <Sw:DigestRef>Sw.FARequestHeader</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct SnF – Receiver


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Put.Response</Sw:DigestRef>
      </Sw:Reference>
      <Sw:Reference>
      <Sw:DigestRef>Sw.FAResponseHeader</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct ACK Request


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Ack.Request</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – FileAct ACK Response


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.File.Ack.Response</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – InterAct Request


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.RequestHeader and RequestPayload</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

### SignatureList – InterAct Response


    <AddSwParams>
      <SwSignatureList xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwSec="urn:swift:snl:ns.SwSec">
      <Out>
      <SwSec:SignatureList>
      <SwSec:Signature>
      <SwSec:KeyInfo>
      <SwSec:SignDN>AnyDN</SwSec:SignDN>
      </SwSec:KeyInfo>
      <SwSec:Manifest>
      <Sw:Reference>
      <Sw:DigestRef>Sw.ResponseHeader and ResponsePayload</Sw:DigestRef>
      </Sw:Reference>
      </SwSec:Manifest>
      </SwSec:Signature>
      </SwSec:SignatureList>
      </Out>
      </SwSignatureList>
    </AddSwParams>

<span id="RecipientList"></span>

## Examples of XML files containing Recipient List

### RecipientList – FileAct SnF PUT Request – Initiator

This file also contains two Failed Delivery Notification Messages and one Delivery Notification Message.


    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwSec="urn:swift:snl:ns.SwSec" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
    <SwRecipientList>
    <Out>
    <Sw:RecipientList>
    <Sw:RecipientDN>
    cn=recipient1,ou=fr,o=bankfrpp,o=swift
    </Sw:RecipientDN>
    <Sw:RecipientDN>
    cn=recipient2,ou=fr,o=bankfrpp,o=swift
    </Sw:RecipientDN>
    <Sw:RecipientDN>
    cn=recipient3,ou=fr,o=bankfrpp,o=swift
    </Sw:RecipientDN>
    </Sw:RecipientList>
    </Out>
    </SwRecipientList>
     
    <FailedDeliveryNotificationMessage>
    <In>
    <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.012.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
     <Doc:xsys.012.001.01>
    <Doc:DlvryNtfctn>
    <Sw:SnFRef>snp20005D21313673884370601</Sw:SnFRef>
    <Sw:OrigSnFRef>SNL02026D11313674007922954</Sw:OrigSnFRef>
    <Sw:RecipientDN>cn=recipient1,ou=fr,o=bankfrpp,o=swift</Sw:RecipientDN>
    <Sw:SnFRefType>FileAct</Sw:SnFRefType>
    <Sw:AcceptStatus>Rejected</Sw:AcceptStatus>
    <Sw:DeliveryTime>2011-08-18T13:24:44Z</Sw:DeliveryTime>
    <Sw:AckSwiftTime>2011-08-18T13:24:48Z</Sw:AckSwiftTime>
    <Sw:AckDescription>Destination trading partner does not exist</Sw:AckDescription>
    <Sw:FileRequestHeader>
    <SwInt:Requestor>cn=recipient3,ou=fr,o=bankfrpp,o=swift</SwInt:Requestor>
    <SwInt:Responder>cn=distributor,o=swift,o=swift</SwInt:Responder>
    <SwInt:Service>swift.test.sf.iafa!x</SwInt:Service>
    <SwInt:RequestType>pain.xxx.cfonb170.dct</SwInt:RequestType>
    <SwInt:Priority>Normal</SwInt:Priority>
    </Sw:FileRequestHeader>
    </Doc:DlvryNtfctn>
    </Doc:xsys.012.001.01>
    </Doc:Document>
     
    <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.012.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
    <Doc:xsys.012.001.01>
    <Doc:DlvryNtfctn>
    <Sw:SnFRef>snp20005D21313673884371601</Sw:SnFRef>
    <Sw:OrigSnFRef>SNL02026D11313674007922954</Sw:OrigSnFRef>
    <Sw:RecipientDN>cn=recipient2,ou=fr,o=bankfrpp,o=swift</Sw:RecipientDN>
    <Sw:SnFRefType>FileAct</Sw:SnFRefType>
    <Sw:AcceptStatus>Rejected</Sw:AcceptStatus>
    <Sw:DeliveryTime>2011-08-18T13:24:44Z</Sw:DeliveryTime>
    <Sw:AckSwiftTime>2011-08-18T13:24:55Z</Sw:AckSwiftTime>
    <Sw:AckDescription>Destination trading partner does not exist</Sw:AckDescription>
    <Sw:FileRequestHeader>
    <SwInt:Requestor>cn=recipient3,ou=fr,o=bankfrpp,o=swift</SwInt:Requestor>
    <SwInt:Responder>cn=distributor,o=swift,o=swift</SwInt:Responder>
    <SwInt:Service>swift.test.sf.iafa!x</SwInt:Service>
    <SwInt:RequestType>pain.xxx.cfonb170.dct</SwInt:RequestType>
    <SwInt:Priority>Normal</SwInt:Priority>
    </Sw:FileRequestHeader>
    </Doc:DlvryNtfctn>
    </Doc:xsys.012.001.01>
    </Doc:Document>
    </In>
    </FailedDeliveryNotificationMessage>
     
    <DeliveryNotificationMessage>
    <In>
    <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.011.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
    <Doc:xsys.011.001.01>
    <Doc:DlvryNtfctn>
    <Sw:SnFRef>snp20005D21313673884372601</Sw:SnFRef>
    <Sw:OrigSnFRef>SNL02026D11313674007922954</Sw:OrigSnFRef>
    <Sw:RecipientDN>cn=recipient3,ou=fr,o=bankfrpp,o=swift</Sw:RecipientDN>
    <Sw:SnFRefType>FileAct</Sw:SnFRefType>
    <Sw:AcceptStatus>Accepted</Sw:AcceptStatus>
    <Sw:DeliveryTime>2011-08-18T13:24:44Z</Sw:DeliveryTime>
    <Sw:AckSwiftTime>2011-08-18T13:24:56Z</Sw:AckSwiftTime>
    <Sw:FileRequestHeader>
    <SwInt:Requestor>cn=recipient3,ou=fr,o=bankfrpp,o=swift</SwInt:Requestor>
    <SwInt:Responder>cn=distributor,o=swift,o=swift</SwInt:Responder>
    <SwInt:Service>swift.test.sf.iafa!x</SwInt:Service>
    <SwInt:RequestType>pain.xxx.cfonb170.dct</SwInt:RequestType>
    <SwInt:Priority>Normal</SwInt:Priority>
    </Sw:FileRequestHeader>
    </Doc:DlvryNtfctn>
    </Doc:xsys.011.001.01>
    </Doc:Document>
    </In>
    </DeliveryNotificationMessage>
    </AddSwParams>

### RecipientList – FileAct SnF PUT Request – Responder


    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
    <SwRecipientList>
    <In>
    <Sw:RecipientList xmlns:Sw="urn:swift:snl:ns.Sw">
    <Sw:RecipientDN>
    cn=recipient1,ou=fr,o=bankfrpp,o=swift
    </Sw:RecipientDN>
    <Sw:RecipientDN>
    cn=recipient2,ou=fr,o=bankfrpp,o=swift
    </Sw:RecipientDN>
    <Sw:RecipientDN>
    cn=recipient3,ou=fr,o=bankfrpp,o=swift
    </Sw:RecipientDN>
    </Sw:RecipientList>
    </In>
    </SwRecipientList>
    </AddSwParams>

<span id="FileCopy"></span>

## Example of XML file containing File or Message Copy information


    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
       <Sw:ThirdPartyToReceiverInformation xmlns:Sw="urn:swift:snl:ns.Sw">
          <Sw:TPInfo>generic third party to receiver information</Sw:TPInfo>
       </Sw:ThirdPartyToReceiverInformation>
    </AddSwParams>

<span id="DeliveryNotif"></span>

## Example of XML file containing delivery notification (SnF) information

The Store-and-Forward delivery notification is deposited in the SWIFT parameter file. Both the incoming request and the outgoing reply are saved.


    <?xml version="1.0"  encoding="UTF-8"?>
    <AddSwParams>
      <SwSnFDeliveryNotification>
          <In>
              <Sw:HandleSnFRequest xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwSec="urn:swift:snl:ns.SwSec" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
                  <Sw:SnFRequestHandle>
                      <Sw:SnFRequestDescriptor>
                          <SwInt:MRRResult>
                              <SwInt:SNLId>snl01568</SwInt:SNLId>
                              <SwInt:SNLEP>MC_EP</SwInt:SNLEP>
                          </SwInt:MRRResult>
                          <Sw:SnFOutputInfo>
                              <Sw:SnFSessionId>bic1_dev02fadn!x:p:000868</Sw:SnFSessionId>
                              <Sw:SnFOutputSeq>2374</Sw:SnFOutputSeq>
                              <Sw:DeliveryTime>2010-01-12T15:47:32Z</Sw:DeliveryTime>
                              <Sw:SnFInputTime>0101:2010-01-12T15:47:31</Sw:SnFInputTime>
                          </Sw:SnFOutputInfo>
                      </Sw:SnFRequestDescriptor>
                      <Sw:SnFOpRequestHandle>
                          <Sw:NotifySnFRequestHandle>
                              <Sw:SnFRef>SNL01568D11263311013740630C</Sw:SnFRef>
                              <Sw:SnFRefType>FileAct</Sw:SnFRefType>
                              <Sw:AcceptStatus>Accepted</Sw:AcceptStatus>
                              <Sw:AckSwiftTime>2010-01-12T15:47:31Z</Sw:AckSwiftTime>
                          </Sw:NotifySnFRequestHandle>
                      </Sw:SnFOpRequestHandle>
                  </Sw:SnFRequestHandle>
              </Sw:HandleSnFRequest>
          </In>
          <Out>
              <Sw:HandleSnFResponse xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwSec="urn:swift:snl:ns.SwSec" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
                  <SwSec:AuthorisationContext>
                      <SwSec:UserDN>cn=xfer,o=bic2,o=swift</SwSec:UserDN>
                  </SwSec:AuthorisationContext>
                  <Sw:SnFResponse>
                      <Sw:SnFResponseControl>
                          <SwInt:NRIndicator>FALSE</SwInt:NRIndicator>
                          <Sw:ProductList>
                              <Sw:ProductInfo>
                                  <Sw:VendorName>Axway</Sw:VendorName>
                                  <Sw:ProductName>Gateway</Sw:ProductName>
                                  <Sw:ProductVersion>6130</Sw:ProductVersion>
                              </Sw:ProductInfo>
                          </Sw:ProductList>
                      </Sw:SnFResponseControl>
                      <Sw:SnFOpResponse>
                          <Sw:NotifySnFResponse>                          <Sw:AckMessage>
                                  <Sw:SnFRef>SNL01568D11263311013740630C</Sw:SnFRef>
                                  <Sw:SnFRefType>FileAct</Sw:SnFRefType>
                                  <Sw:AcceptStatus>Accepted</Sw:AcceptStatus>
                              </Sw:AckMessage>
                          </Sw:NotifySnFResponse>
                      </Sw:SnFOpResponse>
                  </Sw:SnFResponse>
              </Sw:HandleSnFResponse>
        </Out>
      </SwSnFDeliveryNotification>
    </AddSwParams>

<span id="Example"></span>

## Example of XML file containing Real Time Delivery Notification

The Real Time delivery notification is deposited in the SWIFT parameter file. Both the incoming request and the outgoing reply are saved.


    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
      <SwRTDeliveryNotification>
        <In>
          <Sw:HandleFileRequest xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwSec="urn:swift:snl:ns.SwSec" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
            <Sw:FileRequestHandle>
              <Sw:FileRequestDescriptor>
                  <SwInt:SwiftRequestRef>SNL02026-2014-03-04T15:56:13.8716.005035Z</SwInt:SwiftRequestRef>
                  <Sw:SwiftTime>2014-03-04T15:40:29Z</Sw:SwiftTime>
                  <SwInt:MRRResult>
                      <SwInt:SNLId>snl02026</SwInt:SNLId>
                      <SwInt:SNLEP>swci_rt1</SwInt:SNLEP>
                  </SwInt:MRRResult>
              </Sw:FileRequestDescriptor>
              <Sw:FileRequestE2EControl>
                  <Sw:MsgId>5315F3EC-3773-5D55-01F2-6F00000003DC</Sw:MsgId>
                  <Sw:CreationTime>2014-03-04T15:40:28Z</Sw:CreationTime>
              </Sw:FileRequestE2EControl>
              <Sw:FileRequestHeader>
                  <SwInt:Requestor>cn=rnda,ou=ro,o=ptsafrkk,o=swift</SwInt:Requestor>
                  <SwInt:Responder>cn=rnd9,ou=ro,o=ptsafrkk,o=swift</SwInt:Responder>
                  <SwInt:Service>swift.test.rt.iafa!x</SwInt:Service>
                  <SwInt:RequestType>xsys.xxx.delnotif</SwInt:RequestType>
                  <SwInt:Priority>Normal</SwInt:Priority>
              </Sw:FileRequestHeader>
              <Sw:FileOpRequestHandle>
                <Sw:AckFileRequestHandle>
                  <Sw:TransferRef>SNL02026D11393948546273789S</Sw:TransferRef>
                  <Sw:Digest>
                      <Sw:DigestAlgorithm>SHA-256</Sw:DigestAlgorithm>
                      <Sw:DigestValue>ypeBEsobvcr6wjGzmiPcTaeG7/gUfE5yuYB3ha/uSLs=</Sw:DigestValue>
                  </Sw:Digest>
                  <Sw:Accepted>TRUE</Sw:Accepted>
                </Sw:AckFileRequestHandle>
              </Sw:FileOpRequestHandle>
            </Sw:FileRequestHandle>
          </Sw:HandleFileRequest>
        </In>
        <Out>
          <Sw:HandleFileResponse xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwSec="urn:swift:snl:ns.SwSec" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
            <SwSec:AuthorisationContext>
                <SwSec:UserDN>cn=xfer2,o=ptsafrkk,o=swift</SwSec:UserDN>
            </SwSec:AuthorisationContext>
            <Sw:FileResponse>
                <Sw:FileResponseControl>
                  <SwInt:ResponseCrypto>FALSE</SwInt:ResponseCrypto>
                  <SwInt:NRIndicator>FALSE</SwInt:NRIndicator>
                  <Sw:ProductList>
                      <Sw:ProductInfo>
                         <Sw:VendorName>Axway</Sw:VendorName>
                         <Sw:ProductName>Gateway</Sw:ProductName>
                         <Sw:ProductVersion>6150IR14</Sw:ProductVersion>
                      </Sw:ProductInfo>
                  </Sw:ProductList>
                </Sw:FileResponseControl>
                <Sw:FileResponseE2EControl>
                    <Sw:MsgId>5315F3EC-3773-5D55-01F2-6F00000003DC</Sw:MsgId>
                    <Sw:CreationTime>2014-03-04T15:40:30Z</Sw:CreationTime>
                </Sw:FileResponseE2EControl>
                <Sw:FileResponseHeader>
                    <SwInt:Responder>cn=rnd9,ou=ro,o=ptsafrkk,o=swift</SwInt:Responder>
                </Sw:FileResponseHeader>
                <Sw:FileOpResponse>
                  <Sw:AckFileResponse/>
                </Sw:FileOpResponse>
            </Sw:FileResponse>
          </Sw:HandleFileResponse>
        </Out>
      </SwRTDeliveryNotification>
    </AddSwParams>

<span id="Example2"></span>

## Example of XML file containing an Authorization Notification system message

The Authorization Notification system message is deposited in the SWIFT parameter file.



    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
      <YCopyAuthorisationNotification>
        <In>
          <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.002.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl" xmlns:SwSec="urn:swift:snl:ns.SwSec">
            <Doc:xsys.002.001.01>
              <Doc:AuthstnNtfctn>
                <Sw:SnFRef>SNL02026D11392743452505115</Sw:SnFRef>
                <Sw:FileRequestHeader>
                  <SwInt:Requestor>cn=rnd9,ou=ro,o=ptsafrkk,o=swift</SwInt:Requestor>
                  <SwInt:Responder>cn=rnda,ou=ro,o=ptsafrkk,o=swift</SwInt:Responder>
                  <SwInt:Service>swift.qualif.ycopf!x</SwInt:Service>
                  <SwInt:RequestType>admi.xxx.fa.nro.hdo</SwInt:RequestType>
                  <SwInt:Priority>Normal</SwInt:Priority>
                </Sw:FileRequestHeader>
                <Sw:ThirdPartyToSenderInformation>
                  <Sw:TPInfo>generic 3rd party to sender information</Sw:TPInfo>
                </Sw:ThirdPartyToSenderInformation>
              </Doc:AuthstnNtfctn>
            </Doc:xsys.002.001.01>
          </Doc:Document>
        </In>
      </YCopyAuthorisationNotification>
    </AddSwParams>

<span id="Example3"></span>

## Example of XML file containing a Refusal Notification system message

The Refusal Notification system message is deposited in the SWIFT parameter file.



    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
      <YCopyRefusalNotification>
        <In>
          <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.003.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl" xmlns:SwSec="urn:swift:snl:ns.SwSec">
            <Doc:xsys.003.001.01>
              <Doc:AuthstnRfslNtfctn>
                <Sw:SnFRef>SNL00112D10045533050123736</Sw:SnFRef>
                <Sw:FileRequestHeader>
                  <SwInt:Requestor>cn=rnd9,ou=ro,o=ptsafrkk,o=swift</SwInt:Requestor>
                  <SwInt:Responder>cn=rnda,ou=ro,o=ptsafrkk,o=swift</SwInt:Responder>
                  <SwInt:Service>swift.qualif.ycopf!x</SwInt:Service>
                  <SwInt:RequestType>admi.xxx.ia.nro.hdo</SwInt:RequestType>
                </Sw:FileRequestHeader>
              </Doc:AuthstnRfslNtfctn>
            </Doc:xsys.003.001.01>
          </Doc:Document>
        </In>
      </YCopyRefusalNotification>
    </AddSwParams>

<span id="Example4"></span>

## Example of XML file containing a Delivery Notification system message


    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
      <DeliveryNotificationMessage>
        <In>
          <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.011.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
            <Doc:xsys.011.001.01>
              <Doc:DlvryNtfctn>
                <Sw:SnFRef>snp10005D11392632259369601</Sw:SnFRef>
                <Sw:OrigSnFRef>SNL02026D11392633171168895</Sw:OrigSnFRef>
                <Sw:RecipientDN>cn=rnda,ou=ro,o=ptsafrkk,o=swift</Sw:RecipientDN>
                <Sw:SnFRefType>FileAct</Sw:SnFRefType>
                <Sw:AcceptStatus>Accepted</Sw:AcceptStatus>
                <Sw:DeliveryTime>2014-02-17T10:17:39Z</Sw:DeliveryTime>
                <Sw:AckSwiftTime>2014-02-17T10:17:48Z</Sw:AckSwiftTime>
                <Sw:FileRequestHeader>
                  <SwInt:Requestor>cn=rnd9,ou=ro,o=ptsafrkk,o=swift</SwInt:Requestor>
                  <SwInt:Responder>cn=distributor,o=swift,o=swift</SwInt:Responder>
                  <SwInt:Service>swift.test.sf.iafa!x</SwInt:Service>
                  <SwInt:RequestType>admi.xxx.fa.nro.hdo</SwInt:RequestType>
                  <SwInt:Priority>Normal</SwInt:Priority>
                </Sw:FileRequestHeader>
              </Doc:DlvryNtfctn>
            </Doc:xsys.011.001.01>
          </Doc:Document>
        </In>
      </DeliveryNotificationMessage>
    </AddSwParams>

<span id="Example5"></span>

## Example of XML file containing a Failed Delivery Notification



    <?xml version="1.0" encoding="UTF-8"?>
    <AddSwParams>
      <FailedDeliveryNotificationMessage>
        <In>
          <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.012.001.01" xmlns:Sw="urn:swift:snl:ns.Sw" xmlns:SwInt="urn:swift:snl:ns.SwInt" xmlns:SwGbl="urn:swift:snl:ns.SwGbl">
            <Doc:xsys.012.001.01>
              <Doc:DlvryNtfctn>
                <Sw:SnFRef>snp10005D11391767405984600</Sw:SnFRef>
                <Sw:OrigSnFRef>SNL02026D11391768304001932</Sw:OrigSnFRef>
                <Sw:RecipientDN>cn=rndbad,ou=ro,o=ptsafrkk,o=swift</Sw:RecipientDN>
                <Sw:SnFRefType>FileAct</Sw:SnFRefType>
                <Sw:AcceptStatus>Rejected</Sw:AcceptStatus>
                <Sw:DeliveryTime>2014-02-07T10:03:26Z</Sw:DeliveryTime>
                <Sw:AckSwiftTime>2014-02-07T10:03:28Z</Sw:AckSwiftTime>
                <Sw:AckDescription>Originator trading partner does not exist</Sw:AckDescription>
                <Sw:FileRequestHeader>
                  <SwInt:Requestor>cn=rnd9,ou=ro,o=ptsafrkk,o=swift</SwInt:Requestor>
                  <SwInt:Responder>cn=distributor,o=swift,o=swift</SwInt:Responder>
                  <SwInt:Service>swift.test.sf.iafa!x</SwInt:Service>
                  <SwInt:RequestType>admi.xxx.fa.nro.hdo</SwInt:RequestType>
                  <SwInt:Priority>Normal</SwInt:Priority>
                </Sw:FileRequestHeader>
              </Doc:DlvryNtfctn>
            </Doc:xsys.012.001.01>
          </Doc:Document>
        </In>
      </FailedDeliveryNotificationMessage>
    </AddSwParams>

Related topics

[SWIFTNet Header Info](../../swiftnet_header_info)

[SWIFTNet Signature List](../../swiftnet_sig_list)

[SWIFTNet Distribution List](../../swiftnet_header_info/swiftnet_distribution_list)

[SWIFTNet File and Message Copy](../../swiftnet_header_info/swiftnet_file_copy)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
