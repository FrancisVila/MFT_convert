{
    "title": "Protocol  diagnostic codes",
    "linkTitle": "Protocol diagnostic codes",
    "weight": "510"
}## <span id="PeSIT_Protocol_Diagnostic_Codes"></span>PeSIT protocol diagnostic codes

The PeSIT protocol uses two PIs to carry diagnostic messages: PI 2 and
PI 29.

Transfer CFT is responsible for PI 29, which is valid only in
version E. Transfer CFT uses PI 29 to carry a clearform message describing
the error. This message is not seen by the user.

## Diagnostic protocol field format

This section presents the diagnostic protocol fields format for the PeSIT
protocol. In PeSIT protocol, the DIAGP or Diag Protocol
fields can be organized in several ways:

-   "HHHHHHHH"
    format

H represents a hexadecimal digit.

In general for Transfer CFT, this format represents
an error code specific to the operating system of the host computer and
only relates to NON network resources (file access, task management, system
services, etc.).

For PeSIT, this field can also represent an error
code specific to the method of access to the network of the system concerned.
In this case, the code is associated with the following internal diagnostics:

-   301: network
    addressing error in connection phase
-   302: network
    error (cut, timeout) during the data exchange phase
-   303: network
    parameter error in connection phase
-   "eNNsNN"
    format

N represents a decimal digit. An unexpected event
has arisen in the protocol controller.

This value should be given to the Technical support
in the event of unexplained transfer difficulties.

-   "PDU
    iNN" format

N represents a decimal digit. Reception of an FPDU
not conforming to the protocol specifications. The meanings associated
with this message are explained further on in this book. For example,
DIAGP = "PDU i16" means that the header of an FPDU received
does non conform, because its size is greater than the length of the network
message received.

-   "XXX
    NNN" format

X represents an alphabetical character.

N represents a decimal digit. Reception of an FPDU
featuring an error diagnostic (PI 2) conforming to the PeSIT protocol.
XXX represents the FPDU received. NNN represents the PeSIT
reason code (the two least significant bytes sent in the PI 2 code
of FPDUs). The possible values for the PeSIT reason code are given
further on in this appendix. The possible values for XXX are given
in the following table.

-   "XXX
    iNN" format

X represents an alphabetical character.  
N represents a decimal digit.  
Reception of an FPDU having a parameter not conforming to the protocol
specifications. As for the previous format, XXX represents the
FPDU received. NN indicates an error code which is used to refine
the problem detected. The possible values for XXX are given in
the following table.  
For example, DIAGP = "CRE i12" means that a CREATE FPDU
has been received with an unknown space reservation unit (PI 41).

 "XXX
iNN" format values

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>XXX</th>
         <th>FPDU</th>
         <th>Definition</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ABO </p>         </td>
         <td data-valign="top" width="27%">            <p>ABORT  </p>         </td>
         <td data-valign="top" width="54%">            <p>Sudden connection interruption </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ACF </p>         </td>
         <td data-valign="top" width="27%">            <p>AckCRF  </p>         </td>
         <td data-valign="top" width="54%">            <p>File closing confirmation </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ACO </p>         </td>
         <td data-valign="top" width="27%">            <p>ACONNECT </p>         </td>
         <td data-valign="top" width="54%">            <p>Connection confirmation </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ACR </p>         </td>
         <td data-valign="top" width="27%">            <p>AckCREATE  </p>         </td>
         <td data-valign="top" width="54%">            <p>File creation confirmation </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ADS </p>         </td>
         <td data-valign="top" width="27%">            <p>AckDESELECT </p>         </td>
         <td data-valign="top" width="54%">            <p>File deselect confirmation </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>AMG </p>         </td>
         <td data-valign="top" width="27%">            <p>AckMSG </p>         </td>
         <td data-valign="top" width="54%">            <p>Message confirmation </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>AOF </p>         </td>
         <td data-valign="top" width="27%">            <p>AckORF </p>         </td>
         <td data-valign="top" width="54%">            <p>File opening confirmation </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ARD </p>         </td>
         <td data-valign="top" width="27%">            <p>AckREAD </p>         </td>
         <td data-valign="top" width="54%">            <p>Read confirmation </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ASE </p>         </td>
         <td data-valign="top" width="27%">            <p>AckSELECT </p>         </td>
         <td data-valign="top" width="54%">            <p>File selection confirmation </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>ATE </p>         </td>
         <td data-valign="top" width="27%">            <p>AckTRANS.END </p>         </td>
         <td data-valign="top" width="54%">            <p>End of transfer confirmation </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>AWR </p>         </td>
         <td data-valign="top" width="27%">            <p>AckWRITE </p>         </td>
         <td data-valign="top" width="54%">            <p>Write confirmation </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>CON </p>         </td>
         <td data-valign="top" width="27%">            <p>CONNECT </p>         </td>
         <td data-valign="top" width="54%">            <p>Connection request </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>CRE </p>         </td>
         <td data-valign="top" width="27%">            <p>CREATE </p>         </td>
         <td data-valign="top" width="54%">            <p>File creation </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>CRF </p>         </td>
         <td data-valign="top" width="27%">            <p>CRF </p>         </td>
         <td data-valign="top" width="54%">            <p>File closing </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>DMG </p>         </td>
         <td data-valign="top" width="27%">            <p>MSGDM </p>         </td>
         <td data-valign="top" width="54%">            <p>Message start </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>DSE </p>         </td>
         <td data-valign="top" width="27%">            <p>DESELECT </p>         </td>
         <td data-valign="top" width="54%">            <p>File deselect </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>DTE </p>         </td>
         <td data-valign="top" width="27%">            <p>TRANS.END </p>         </td>
         <td data-valign="top" width="54%">            <p>End of transfer </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>IDT </p>         </td>
         <td data-valign="top" width="27%">            <p>IDT </p>         </td>
         <td data-valign="top" width="54%">            <p>Transfer interruption </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>MSG </p>         </td>
         <td data-valign="top" width="27%">            <p>MSG </p>         </td>
         <td data-valign="top" width="54%">            <p>Message transmission </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="18%">            <p>RCO </p>         </td>
         <td data-valign="top" width="27%">            <p>RCONNECT </p>         </td>
         <td data-valign="top" width="54%">            <p>Connection refusal </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="18%">            <p>SEL </p>         </td>
         <td data-valign="top" width="27%">            <p>SELECT </p>         </td>
         <td data-valign="top" width="54%">            <p>File selection </p>         </td>
      </tr>
   </tbody>
</table>

-   "Vxxxxxxx"
    format

The mnemonic Vxxxxxxx represents a protocol
event.

This value should be given to the Technical
support in the event of unexplained transfer difficulties.

Vxxxxxxx format: possible
protocol events

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Vxxxxxxx</th>
         <th>Definition</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="24%">            <p>"VFxxxxx" </p>         </td>
         <td data-valign="top" width="76%">            <p>File transfer event  (eg: VFCAND)  </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="24%">            <p>"VLOGxxxx" </p>         </td>
         <td data-valign="top" width="76%">            <p>Event relative to the pre-connection message  (eg:
VLOGRP) </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="24%">            <p>"VNxxxxxx" </p>         </td>
         <td data-valign="top" width="76%">            <p>Network event  (eg: VNRELI) </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="24%">            <p>"VRxxxxxx" </p>         </td>
         <td data-valign="top" width="76%">            <p>FPDU reception event  (eg: VRABORT) </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="24%">            <p>"VVxxxxxx" </p>         </td>
         <td data-valign="top" width="76%">            <p>Internal event (eg: VVTIMO) </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="24%">            <p>"VIxxxxxx" </p>         </td>
         <td data-valign="top" width="76%">            <p>Induced internal event (eg: VIABORT) </p>         </td>
      </tr>
   </tbody>
</table>

Error code descriptions

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Error Code</th>
         <th>FPDU</th>
         <th>Meaning</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>100</p>         </td>
         <td width="22.743%">            <p>RESYNC</p>         </td>
         <td width="57.431%">            <p>Transmission error (invalid CRC)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>139</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Invalid file attributes</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>200</p>         </td>
         <td width="22.743%">            <p>AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>Insufficient file characteristics (insufficient file parameters)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>201</p>         </td>
         <td width="22.743%">            <p>AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>System resources currently insufficient</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>202</p>         </td>
         <td width="22.743%">            <p>AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>User resources currently insufficient</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>203</p>         </td>
         <td width="22.743%">            <p>AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>Non-priority transfer</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>204</p>         </td>
         <td width="22.743%">            <p>AckCREATE</p>         </td>
         <td width="57.431%">            <p>File already exists</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>205</p>         </td>
         <td width="22.743%">            <p>AckSELECT</p>         </td>
         <td width="57.431%">            <p>File does not exist</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>206</p>         </td>
         <td width="22.743%">            <p>AckCREATE</p>         </td>
         <td width="57.431%">            <p>Available disk space smaller than file size</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>207</p>         </td>
         <td width="22.743%">            <p>AckSELECT</p>         </td>
         <td width="57.431%">            <p>File in use</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>209</p>         </td>
         <td width="22.743%">            <p>AckMSG</p>         </td>
         <td width="57.431%">            <p>Message type not supported</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>210</p>         </td>
         <td width="22.743%">            <p>AckORF</p>         </td>
         <td width="57.431%">            <p>Negotiation failure</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>211</p>         </td>
         <td width="22.743%">            <p>AckORF</p>         </td>
         <td width="57.431%">            <p>Cannot open file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>212</p>         </td>
         <td width="22.743%">            <p>AckCRF</p>         </td>
         <td width="57.431%">            <p>Cannot close file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>213</p>         </td>
         <td width="22.743%">            <p>IDT AckWRITE</p>         </td>
         <td width="57.431%">            <p>Fatal file input/output error</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>214</p>         </td>
         <td width="22.743%">            <p>AckREAD</p>         </td>
         <td width="57.431%">            <p>Restart point negotiation failure</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>215</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Error specific to the system</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>216</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Operator-requested premature abort</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>217</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Too many synchronization points without acknowledgment</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>218</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Cannot re-synchronize</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>219</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>File space exceeded</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>220</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Record length greater than that declared</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>221</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Time-out</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>222</p>         </td>
         <td width="22.743%">            <p>IDT</p>         </td>
         <td width="57.431%">            <p>Too much data without synchronization point</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>223</p>         </td>
         <td width="22.743%">            <p>AckTRANSFER.</p>
            <p>END AckDESELECT</p>         </td>
         <td width="57.431%">            <p>Abnormal end of transfer</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>224</p>         </td>
         <td width="22.743%">            <p>AckTRANSFER.END</p>         </td>
         <td width="57.431%">            <p>Declared file size smaller than actual size</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>226</p>         </td>
         <td width="22.743%">            <p>AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>Transfer denied</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>228</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>File type not supported</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>229</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>File type incompatible with transfer direction</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>230</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>File type incompatible with application</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>231</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Transfer number not unique</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>232</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Coding incompatible with file type</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>233</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Restart context not available</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>234</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Data entity size inconsistent with record</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>235</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Record format incompatible with file type</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>236</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Record length incompatible with file type</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>237</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Incorrect client identifier</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>238</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Non-authorized client</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>239</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Non-authorized client / requester / file type combination</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>240</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Client not authorized on this server</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>241</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Bank not authorized on this server</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>242</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Old password invalid</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>243</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>New password invalid</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>245</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Incorrect file length</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>246</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>No file of this type for this client</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>247</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>No file of this type on this server</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>248</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Identification type not supported</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>249</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Nominative reference not supported</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>250</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>File already transferred</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>251</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Reference type not supported</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>252</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Start date too old</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>253</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Incorrect date(s)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>254</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>File service closed</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>299</p>         </td>
         <td width="22.743%">            <p>All acknowledgment FPDUs</p>         </td>
         <td width="57.431%">            <p>Other fatal errors</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>300</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>Congestion of local communication system</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>301</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>Identification of called party unknown</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>302</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>Called party not attached to a Service Access Point (SAP)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>303</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>Maximum number of connections reached</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>304</p>         </td>
         <td width="22.743%">            <p>RelCONNECT AckCREATE AckSELECT ABORT</p>         </td>
         <td width="57.431%">            <p>Non-authorized requester identification</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>305</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>SELECT negotiation failure</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>306</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>RESYN negotiation failure</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>307</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>SYNC negotiation failure</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>308</p>         </td>
         <td width="22.743%">            <p>RelCONNECT</p>         </td>
         <td width="57.431%">            <p>Version number not supported</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>309</p>         </td>
         <td width="22.743%">            <p>RelCONNECT ABORT</p>         </td>
         <td width="57.431%">            <p>Too many connections already in progress</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>310</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Network incident</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>311</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Remote PeSIT protocol error</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>312</p>         </td>
         <td width="22.743%">            <p>RelCONNECT (if partner inactive) ABORT/RELEASE</p>         </td>
         <td width="57.431%">            <p>Shutdown of service requested by the user</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>313</p>         </td>
         <td width="22.743%">            <p>ABORT/RELEASE</p>         </td>
         <td width="57.431%">            <p>Connection closed due to inactivity</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>314</p>         </td>
         <td width="22.743%">            <p>ABORT/RELEASE</p>         </td>
         <td width="57.431%">            <p>Unused connection closed to open a new connection</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>315</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Negotiation failure</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>316</p>         </td>
         <td width="22.743%">            <p>ABORT/RELEASE</p>         </td>
         <td width="57.431%">            <p>Connection closed by the administrator</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>317</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Connection time-out</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>318</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Mandatory PI missing or invalid</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>319</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Incorrect number of records or bytes</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>320</p>         </td>
         <td width="22.743%">            <p>ABORT</p>         </td>
         <td width="57.431%">            <p>Excessive number of re-synchronizations</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>321</p>         </td>
         <td width="22.743%">            <p>RelCONNECT AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>Call backup number</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>322</p>         </td>
         <td width="22.743%">            <p>RelCONNECT AckCREATE AckSELECT</p>         </td>
         <td width="57.431%">            <p>Call back later</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>323</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Incompatible CRC / connection mode</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>324</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Incorrect requester identifier</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>325</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Old password invalid</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>326</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>New password invalid</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>327</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Receive access temporarily closed</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>328</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Receive access not supported</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>329</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Send access temporarily closed</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>330</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Send access not supported</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>331</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Excessive time-out value</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>332</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Write not negotiated</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>333</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Read not negotiated</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>334</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Reverse charging refused</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>335</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Invalid calling party number</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.826%">            <p>336</p>         </td>
         <td width="22.743%">            <p> </p>         </td>
         <td width="57.431%">            <p>Server date and time refused</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="19.826%">            <p>399</p>         </td>
         <td width="22.743%">            <p>All ABORT acknowledgment FPDUs</p>         </td>
         <td width="57.431%">            <p>Other fatal errors</p>         </td>
      </tr>
   </tbody>
</table>

### PeSIT reason code

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>PeSIT reason code</th>
         <th>Description</th>
         <th><span>Transfer CFT</span> internal
diagnostic</th>
         <th>Service item concerned</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td colspan="4" data-bgcolor="#FFFFFF" data-valign="top">            <p>Diagnostics imposing a re-synchronization </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>100 </p>         </td>
         <td data-valign="top" width="49%">            <p>Transmission error </p>         </td>
         <td data-valign="top" width="16%">            <p>720 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.RESTART </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td colspan="4" data-bgcolor="#FFFFFF" data-valign="top">            <p>Diagnostics imposing a restart </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>200 </p>         </td>
         <td data-valign="top" width="49%">            <p>File characteristics insufficient </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>201 </p>         </td>
         <td data-valign="top" width="49%">            <p>System resources temporarily insufficient </p>         </td>
         <td data-valign="top" width="16%">            <p>916 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>202 </p>         </td>
         <td data-valign="top" width="49%">            <p>User resources temporarily insufficient </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>203 </p>         </td>
         <td data-valign="top" width="49%">            <p>Transfer not overriding </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>204 </p>         </td>
         <td data-valign="top" width="49%">            <p>File already exists </p>         </td>
         <td data-valign="top" width="16%">            <p>613 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>205 </p>         </td>
         <td data-valign="top" width="49%">            <p>File does not exist </p>         </td>
         <td data-valign="top" width="16%">            <p>610 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>206 </p>         </td>
         <td data-valign="top" width="49%">            <p>Reception of the file will cause an overflow of the disk
quota </p>         </td>
         <td data-valign="top" width="16%">            <p>611 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>207 </p>         </td>
         <td data-valign="top" width="49%">            <p>File occupied </p>         </td>
         <td data-valign="top" width="16%">            <p>635 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>208 </p>         </td>
         <td data-valign="top" width="49%">            <p>File too old </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>209 </p>         </td>
         <td data-valign="top" width="49%">            <p>Message of this type not accepted on the reference installation </p>         </td>
         <td data-valign="top" width="16%">            <p>920 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>210 </p>         </td>
         <td data-valign="top" width="49%">            <p>Presentation context negotiation failure </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.OPEN </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>211 </p>         </td>
         <td data-valign="top" width="49%">            <p>Not possible to open file </p>         </td>
         <td data-valign="top" width="16%">            <p>604 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.OPEN </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>212 </p>         </td>
         <td data-valign="top" width="49%">            <p>Not possible to close file normally  </p>         </td>
         <td data-valign="top" width="16%">            <p>605 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CLOSE </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>213 </p>         </td>
         <td data-valign="top" width="49%">            <p>Inhibiting input/output error </p>         </td>
         <td data-valign="top" width="16%">            <p>600 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.READ<br />
F.WRITE<br />
F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>214 </p>         </td>
         <td data-valign="top" width="49%">            <p>Restart point negotiation failure  </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.READ<br />
F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>215 </p>         </td>
         <td data-valign="top" width="49%">            <p>Specific system error </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>216 </p>         </td>
         <td data-valign="top" width="49%">            <p>Intentional premature halt </p>         </td>
         <td data-valign="top" width="16%">            <p>621 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>217 </p>         </td>
         <td data-valign="top" width="49%">            <p>Too many synchronization points not acknowledged </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>218 </p>         </td>
         <td data-valign="top" width="49%">            <p>Re-synchronization not possible </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>219 </p>         </td>
         <td data-valign="top" width="49%">            <p>File space full </p>         </td>
         <td data-valign="top" width="16%">            <p>614 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>220 </p>         </td>
         <td data-valign="top" width="49%">            <p>Article longer than expected </p>         </td>
         <td data-valign="top" width="16%">            <p>626 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>221 </p>         </td>
         <td data-valign="top" width="49%">            <p>Expected end of transmission time </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>222 </p>         </td>
         <td data-valign="top" width="49%">            <p>Too much data without synchronization points </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>223 </p>         </td>
         <td data-valign="top" width="49%">            <p>Abnormal end of transfer </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>224 </p>         </td>
         <td data-valign="top" width="49%">            <p>The size of the file sent is greater than the one announced
in F.CREATE </p>         </td>
         <td data-valign="top" width="16%">            <p>600 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>225 </p>         </td>
         <td data-valign="top" width="49%">            <p>Workstation application congested: the file has effectively
been received but SCRS has not been able to give it to the workstation
application  </p>         </td>
         <td data-valign="top" width="16%">            <p>600 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>226 </p>         </td>
         <td data-valign="top" width="49%">            <p>Transfer refusal </p>         </td>
         <td data-valign="top" width="16%">            <p>904 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>299 </p>         </td>
         <td data-valign="top" width="49%">            <p>Other </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CREATE<br />
F.SELECT<br />
F.OPEN<br />
F.CLOSE<br />
F.READ<br />
F.WRITE<br />
F.DATA.END<br />
F.CANCEL<br />
F.TRANSFER.END<br />
F.DESELECT<br />
F.RESTART </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td colspan="4" data-bgcolor="#FFFFFF" data-valign="top">            <p>Diagnostics imposing a reconnection </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>300 </p>         </td>
         <td data-valign="top" width="49%">            <p>Local communication system congested  </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT  </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>301 </p>         </td>
         <td data-valign="top" width="49%">            <p>Identification requested not known </p>         </td>
         <td data-valign="top" width="16%">            <p>909 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT  </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>302 </p>         </td>
         <td data-valign="top" width="49%">            <p>Requested system not attached to a SSAP </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>303 </p>         </td>
         <td data-valign="top" width="49%">            <p>Remote communication system congested<br />
(too many connections) </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT  </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>304 </p>         </td>
         <td data-valign="top" width="49%">            <p>Requested identification not authorized (security) </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT<br />
F.ABORT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>305 </p>         </td>
         <td data-valign="top" width="49%">            <p>Negotiation failure (SELECT) </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>306 </p>         </td>
         <td data-valign="top" width="49%">            <p>Negotiation failure (RESYN) </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>307 </p>         </td>
         <td data-valign="top" width="49%">            <p>Negotiation failure (SYNC) </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>308 </p>         </td>
         <td data-valign="top" width="49%">            <p>Version number not supported  </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>309 </p>         </td>
         <td data-valign="top" width="49%">            <p>Too many connections already in process for this processing
centre </p>         </td>
         <td data-valign="top" width="16%">            <p>916 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>310 </p>         </td>
         <td data-valign="top" width="49%">            <p>Network incident </p>         </td>
         <td data-valign="top" width="16%">            <p>802 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>311 </p>         </td>
         <td data-valign="top" width="49%">            <p>Remote PeSIT protocol error </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>312 </p>         </td>
         <td data-valign="top" width="49%">            <p>Service closure requested by the user </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>313 </p>         </td>
         <td data-valign="top" width="49%">            <p>Connection broken at the end of the TD inactivity interval </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>314 </p>         </td>
         <td data-valign="top" width="49%">            <p>Connection used to host a new connection </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>315 </p>         </td>
         <td data-valign="top" width="49%">            <p>Negotiation failure </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>316 </p>         </td>
         <td data-valign="top" width="49%">            <p>Connection broken as a result of an administration command
 </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>317 </p>         </td>
         <td data-valign="top" width="49%">            <p>Time-out </p>         </td>
         <td data-valign="top" width="16%">            <p>740 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>318 </p>         </td>
         <td data-valign="top" width="49%">            <p>Mandatory PI absent or illegal PI contents </p>         </td>
         <td data-valign="top" width="16%">            <p>722 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>319 </p>         </td>
         <td data-valign="top" width="49%">            <p>Number of bytes or articles incorrect </p>         </td>
         <td data-valign="top" width="16%">            <p>620 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>320 </p>         </td>
         <td data-valign="top" width="49%">            <p>Excessive number of resynchronizations for a transfer </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>321 </p>         </td>
         <td data-valign="top" width="49%">            <p>Call the backup number </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="13%">            <p>322 </p>         </td>
         <td data-valign="top" width="49%">            <p>Call back later </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="13%">            <p>399 </p>         </td>
         <td data-valign="top" width="49%">            <p>Other </p>         </td>
         <td data-valign="top" width="16%">            <p>730 </p>         </td>
         <td data-valign="top" width="22%">            <p>F.CONNECT<br />
F.RELEASE<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
   </tbody>
</table>

## <span id="ODETTE_Protocol__Diagnostic_Codes"></span>ODETTE Protocol Diagnostic Codes

These codes are specific to the ODETTE protocol and correspond to the
"ODETTE diagnostic code" transmitted by the protocol.

The values of these codes consist of the diagnostic code (two digits)
to which the Transfer CFT adds 100 or 200 depending on the protocol phase concerned.

-   Values between 100 and 199 correspond to the "SFNA" (Start
    File Negative Answer) and "EFNA" (End File Negative Answer)
    protocol messages.
-   Values between 200 and 299 correspond to the "ESID" (End Session
    IDentification) protocol message.
-   This code forms the "NNN NNNN"-type DIAGP protocol diagnostic
    code. Values are expressed in decimal.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Error code</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>101</p>         </td>
         <td width="74.218%">            <p>File does not exist</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>102</p>         </td>
         <td width="74.218%">            <p>Target site does not exist for the file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>103</p>         </td>
         <td width="74.218%">            <p>Source site does not exist for the file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>104</p>         </td>
         <td width="74.218%">            <p>File format not supported</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>105</p>         </td>
         <td width="74.218%">            <p>Record length error (length not supported)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>106</p>         </td>
         <td width="74.218%">            <p>File too big</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>110</p>         </td>
         <td width="74.218%">            <p>Invalid number of records</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>111</p>         </td>
         <td width="74.218%">            <p>Invalid number of characters</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>112</p>         </td>
         <td width="74.218%">            <p>Fatal file input/output error (file access method problem)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>113</p>         </td>
         <td width="74.218%">            <p>File already exists</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>199</p>         </td>
         <td width="74.218%">            <p>Non-referenced errors</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>201</p>         </td>
         <td width="74.218%">            <p>NSDU (Network System Data Unit) not recognized (faulty
header)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>202</p>         </td>
         <td width="74.218%">            <p>Protocol error (reception of a invalid NSDU)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>203</p>         </td>
         <td width="74.218%">            <p>Requestee identification not known</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>204</p>         </td>
         <td width="74.218%">            <p>Requester identifier not authorized or password incorrect</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>205</p>         </td>
         <td width="74.218%">            <p>Congestion of local communication system (sudden shutdown
of communication system)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>206</p>         </td>
         <td width="74.218%">            <p>FPDU received with missing parameter or unexpected value</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>207</p>         </td>
         <td width="74.218%">            <p>Invalid NSDU size received</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>208</p>         </td>
         <td width="74.218%">            <p>User resources currently insufficient</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>209</p>         </td>
         <td width="74.218%">            <p>End of time-out</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="25.782%">            <p>210</p>         </td>
         <td width="74.218%">            <p>Incorrect number of records. The number transported by
the EFID FPDU does not correspond to the number of received records counted
by the <span>Transfer CFT</span> (F- or V-format files)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="25.782%">            <p>211</p>         </td>
         <td width="74.218%">            <p>Number of characters incorrect. The number transported
by the EFID FPDU does not correspond to the number of received characters
counted by the <span>Transfer CFT</span> (T- or U-format files)</p>         </td>
      </tr>
   </tbody>
</table>
