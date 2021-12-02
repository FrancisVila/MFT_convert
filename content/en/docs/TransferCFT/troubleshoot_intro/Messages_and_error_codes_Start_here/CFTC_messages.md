{
    "title": "Transfer CFT messages: CFTC",
    "linkTitle": "CFTC messages",
    "weight": "280"
}This topic lists the CFTC (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

 

 

 

 

 

 

 


|  V23 format<br/>V24 format Information  |  <span id="CFTC08I"></span>CFTC08I &amp;str<br/>CFTC08I &amp;str  |
| --- | --- |
| Explanation  |  Possible values for &amp;str are described here. The following messages are displayed when the catalog is purged on {{< TransferCFT/componentshortname  >}} startup, or at the time set for the daily purge. For example:<br/>When there are no transfers to delete: <div class="indentTableNested"> Purge Started<br /> Purge catalog-size=1000 in-use=0 pre-filtered=0(0%)<br /> Purge Treated: catalog empty<br /> Purge deleted= n treated=n(d%) match=d%.<br /> Purge Treated<br /> Purge Treated: no record found to delete </div> When there are transfers to delete: <div class="indentTableNested"> Catalog: Loading...<br /> Catalog: Load Done<br /> Catalog: Size=100, Used=8(8%)<br /> Purge Started.<br /> Purge catalog-size=100 in-use=8 pre-filtered=8(100)<br /> Purge deleted=1 treated=1(12) match=100<br /> Purge deleted=2 treated=2(25) match=100<br /> ….<br /> Purge deleted=8 treated=8(100) match=100<br /> Purge Treated. </div> When {{< TransferCFT/componentshortname  >}} starts: <div class="indentTableNested"> If there are no transfers to delete: <div class="indentTableNested"> Catalog: Loading...<br /> Catalog: Load Done<br /> Catalog: Size= &amp;00, Used=0(0%)<br /> </div> If there are transfers to delete: <div class="indentTableNested"> Catalog: Loading...<br /> Catalog: Load Done<br /> Catalog: Size=100, Used=8(8%) </div> </div> If there is a problem with the catalog INIT: <div class="indentTableNested"> Catalog: Recovering<br /> Catalog: Recovery Done: n errors<br /> Catalog Recovery: n transfers from C to D state </div>  |


 

 

 

 

 

 

 

 

 
