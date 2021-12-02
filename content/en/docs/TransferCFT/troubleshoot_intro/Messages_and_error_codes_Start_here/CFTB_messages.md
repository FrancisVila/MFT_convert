{
    "title": "Transfer CFT messages: CFTB",
    "linkTitle": "CFTAB messages",
    "weight": "270"
}This topic lists the CFTBxx messages and provides a type, a description, and when applicable a consequence and corrective action.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

### Auto documented messages

Certain auto-documented messages, for example CFTA01I, CFTA02W, CFTA03E, CFTA04F, are not fully detailed as they are considered self-explanatory. The CFTAnnx messages refer to the acceleration feature on all platforms that support acceleration.

-   CFTA01, CFTLOG\_SYS\_INFOR "CFTA01I &str"
-   CFTA02, CFTLOG\_SYS\_WARNI "CFTA02W &str"
-   CFTA03, CFTLOG\_SYS\_ERROR "CFTA03E &str"
-   CFTA04, CFTLOG\_SYS\_FATAL "CFTA04F &str"

 

 

 

 

 

 

 

 

 

 

 

 
