{
    "title": "Protocol  diagnostic codes",
    "linkTitle": "Protocol diagnostic codes",
    "weight": "490"
}<span id="PeSIT_Protocol_Diagnostic_Codes"></span>

## PeSIT protocol diagnostic codes

The PeSIT protocol uses two PIs to carry diagnostic messages: PI 2 and
PI 29.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is responsible for PI 29, which is valid only in
version E. <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> uses PI 29 to carry a clearform message describing
the error. This message is not seen by the user.

## Diagnostic protocol field format

This section presents the diagnostic protocol fields format for the PeSIT
protocol. In PeSIT protocol, the DIAGP or Diag Protocol
fields can be organized in several ways:

-   "HHHHHHHH"
    format

H represents a hexadecimal digit.

In general for <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, this format represents
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

<span class="autonumber"></span> "XXX
iNN" format values

<table>
   <th>
      <tr>
<th>XXX         </th>
<th>FPDU         </th>
<th>Definition         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ABO </p>         </td>
         <td><p>ABORT  </p>         </td>
         <td><p>Sudden connection interruption </p>         </td>
      </tr>
      <tr>
         <td><p>ACF </p>         </td>
         <td><p>AckCRF  </p>         </td>
         <td><p>File closing confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>ACO </p>         </td>
         <td><p>ACONNECT </p>         </td>
         <td><p>Connection confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>ACR </p>         </td>
         <td><p>AckCREATE  </p>         </td>
         <td><p>File creation confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>ADS </p>         </td>
         <td><p>AckDESELECT </p>         </td>
         <td><p>File deselect confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>AMG </p>         </td>
         <td><p>AckMSG </p>         </td>
         <td><p>Message confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>AOF </p>         </td>
         <td><p>AckORF </p>         </td>
         <td><p>File opening confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>ARD </p>         </td>
         <td><p>AckREAD </p>         </td>
         <td><p>Read confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>ASE </p>         </td>
         <td><p>AckSELECT </p>         </td>
         <td><p>File selection confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>ATE </p>         </td>
         <td><p>AckTRANS.END </p>         </td>
         <td><p>End of transfer confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>AWR </p>         </td>
         <td><p>AckWRITE </p>         </td>
         <td><p>Write confirmation </p>         </td>
      </tr>
      <tr>
         <td><p>CON </p>         </td>
         <td><p>CONNECT </p>         </td>
         <td><p>Connection request </p>         </td>
      </tr>
      <tr>
         <td><p>CRE </p>         </td>
         <td><p>CREATE </p>         </td>
         <td><p>File creation </p>         </td>
      </tr>
      <tr>
         <td><p>CRF </p>         </td>
         <td><p>CRF </p>         </td>
         <td><p>File closing </p>         </td>
      </tr>
      <tr>
         <td><p>DMG </p>         </td>
         <td><p>MSGDM </p>         </td>
         <td><p>Message start </p>         </td>
      </tr>
      <tr>
         <td><p>DSE </p>         </td>
         <td><p>DESELECT </p>         </td>
         <td><p>File deselect </p>         </td>
      </tr>
      <tr>
         <td><p>DTE </p>         </td>
         <td><p>TRANS.END </p>         </td>
         <td><p>End of transfer </p>         </td>
      </tr>
      <tr>
         <td><p>IDT </p>         </td>
         <td><p>IDT </p>         </td>
         <td><p>Transfer interruption </p>         </td>
      </tr>
      <tr>
         <td><p>MSG </p>         </td>
         <td><p>MSG </p>         </td>
         <td><p>Message transmission </p>         </td>
      </tr>
      <tr>
         <td><p>RCO </p>         </td>
         <td><p>RCONNECT </p>         </td>
         <td><p>Connection refusal </p>         </td>
      </tr>
      <tr>
         <td><p>SEL </p>         </td>
         <td><p>SELECT </p>         </td>
         <td><p>File selection </p>         </td>
      </tr>
   </tbody>
</table>

-   "Vxxxxxxx"
    format

The mnemonic Vxxxxxxx represents a protocol
event.

This value should be given to the Technical
support in the event of unexplained transfer difficulties.

<span class="autonumber"></span>Vxxxxxxx format: possible
protocol events

<table>
   <th>
      <tr>
<th>Vxxxxxxx         </th>
<th>Definition         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>"VFxxxxx" </p>         </td>
         <td><p>File transfer event  (eg: VFCAND)  </p>         </td>
      </tr>
      <tr>
         <td><p>"VLOGxxxx" </p>         </td>
         <td><p>Event relative to the pre-connection message  (eg:
VLOGRP) </p>         </td>
      </tr>
      <tr>
         <td><p>"VNxxxxxx" </p>         </td>
         <td><p>Network event  (eg: VNRELI) </p>         </td>
      </tr>
      <tr>
         <td><p>"VRxxxxxx" </p>         </td>
         <td><p>FPDU reception event  (eg: VRABORT) </p>         </td>
      </tr>
      <tr>
         <td><p>"VVxxxxxx" </p>         </td>
         <td><p>Internal event (eg: VVTIMO) </p>         </td>
      </tr>
      <tr>
         <td><p>"VIxxxxxx" </p>         </td>
         <td><p>Induced internal event (eg: VIABORT) </p>         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span>Error code descriptions

<table>
   <th>
      <tr>
<th>Error Code         </th>
<th>FPDU         </th>
<th>Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>100</p>         </td>
         <td><p>RESYNC</p>         </td>
         <td><p>Transmission error (invalid CRC)</p>         </td>
      </tr>
      <tr>
         <td><p>139</p>         </td>
         <td><p> </p>         </td>
         <td><p>Invalid file attributes</p>         </td>
      </tr>
      <tr>
         <td><p>200</p>         </td>
         <td><p>AckCREATE AckSELECT</p>         </td>
         <td><p>Insufficient file characteristics (insufficient file parameters)</p>         </td>
      </tr>
      <tr>
         <td><p>201</p>         </td>
         <td><p>AckCREATE AckSELECT</p>         </td>
         <td><p>System resources currently insufficient</p>         </td>
      </tr>
      <tr>
         <td><p>202</p>         </td>
         <td><p>AckCREATE AckSELECT</p>         </td>
         <td><p>User resources currently insufficient</p>         </td>
      </tr>
      <tr>
         <td><p>203</p>         </td>
         <td><p>AckCREATE AckSELECT</p>         </td>
         <td><p>Non-priority transfer</p>         </td>
      </tr>
      <tr>
         <td><p>204</p>         </td>
         <td><p>AckCREATE</p>         </td>
         <td><p>File already exists</p>         </td>
      </tr>
      <tr>
         <td><p>205</p>         </td>
         <td><p>AckSELECT</p>         </td>
         <td><p>File does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>206</p>         </td>
         <td><p>AckCREATE</p>         </td>
         <td><p>Available disk space smaller than file size</p>         </td>
      </tr>
      <tr>
         <td><p>207</p>         </td>
         <td><p>AckSELECT</p>         </td>
         <td><p>File in use</p>         </td>
      </tr>
      <tr>
         <td><p>209</p>         </td>
         <td><p>AckMSG</p>         </td>
         <td><p>Message type not supported</p>         </td>
      </tr>
      <tr>
         <td><p>210</p>         </td>
         <td><p>AckORF</p>         </td>
         <td><p>Negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>211</p>         </td>
         <td><p>AckORF</p>         </td>
         <td><p>Cannot open file</p>         </td>
      </tr>
      <tr>
         <td><p>212</p>         </td>
         <td><p>AckCRF</p>         </td>
         <td><p>Cannot close file</p>         </td>
      </tr>
      <tr>
         <td><p>213</p>         </td>
         <td><p>IDT AckWRITE</p>         </td>
         <td><p>Fatal file input/output error</p>         </td>
      </tr>
      <tr>
         <td><p>214</p>         </td>
         <td><p>AckREAD</p>         </td>
         <td><p>Restart point negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>215</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Error specific to the system</p>         </td>
      </tr>
      <tr>
         <td><p>216</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Operator-requested premature abort</p>         </td>
      </tr>
      <tr>
         <td><p>217</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Too many synchronization points without acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>218</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Cannot re-synchronize</p>         </td>
      </tr>
      <tr>
         <td><p>219</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>File space exceeded</p>         </td>
      </tr>
      <tr>
         <td><p>220</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Record length greater than that declared</p>         </td>
      </tr>
      <tr>
         <td><p>221</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Time-out</p>         </td>
      </tr>
      <tr>
         <td><p>222</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>Too much data without synchronization point</p>         </td>
      </tr>
      <tr>
         <td><p>223</p>         </td>
         <td><p>AckTRANSFER.</p>
<p>END AckDESELECT</p>         </td>
         <td><p>Abnormal end of transfer</p>         </td>
      </tr>
      <tr>
         <td><p>224</p>         </td>
         <td><p>AckTRANSFER.END</p>         </td>
         <td><p>Declared file size smaller than actual size</p>         </td>
      </tr>
      <tr>
         <td><p>226</p>         </td>
         <td><p>AckCREATE AckSELECT</p>         </td>
         <td><p>Transfer denied</p>         </td>
      </tr>
      <tr>
         <td><p>228</p>         </td>
         <td><p> </p>         </td>
         <td><p>File type not supported</p>         </td>
      </tr>
      <tr>
         <td><p>229</p>         </td>
         <td><p> </p>         </td>
         <td><p>File type incompatible with transfer direction</p>         </td>
      </tr>
      <tr>
         <td><p>230</p>         </td>
         <td><p> </p>         </td>
         <td><p>File type incompatible with application</p>         </td>
      </tr>
      <tr>
         <td><p>231</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer number not unique</p>         </td>
      </tr>
      <tr>
         <td><p>232</p>         </td>
         <td><p> </p>         </td>
         <td><p>Coding incompatible with file type</p>         </td>
      </tr>
      <tr>
         <td><p>233</p>         </td>
         <td><p> </p>         </td>
         <td><p>Restart context not available</p>         </td>
      </tr>
      <tr>
         <td><p>234</p>         </td>
         <td><p> </p>         </td>
         <td><p>Data entity size inconsistent with record</p>         </td>
      </tr>
      <tr>
         <td><p>235</p>         </td>
         <td><p> </p>         </td>
         <td><p>Record format incompatible with file type</p>         </td>
      </tr>
      <tr>
         <td><p>236</p>         </td>
         <td><p> </p>         </td>
         <td><p>Record length incompatible with file type</p>         </td>
      </tr>
      <tr>
         <td><p>237</p>         </td>
         <td><p> </p>         </td>
         <td><p>Incorrect client identifier</p>         </td>
      </tr>
      <tr>
         <td><p>238</p>         </td>
         <td><p> </p>         </td>
         <td><p>Non-authorized client</p>         </td>
      </tr>
      <tr>
         <td><p>239</p>         </td>
         <td><p> </p>         </td>
         <td><p>Non-authorized client / requester / file type combination</p>         </td>
      </tr>
      <tr>
         <td><p>240</p>         </td>
         <td><p> </p>         </td>
         <td><p>Client not authorized on this server</p>         </td>
      </tr>
      <tr>
         <td><p>241</p>         </td>
         <td><p> </p>         </td>
         <td><p>Bank not authorized on this server</p>         </td>
      </tr>
      <tr>
         <td><p>242</p>         </td>
         <td><p> </p>         </td>
         <td><p>Old password invalid</p>         </td>
      </tr>
      <tr>
         <td><p>243</p>         </td>
         <td><p> </p>         </td>
         <td><p>New password invalid</p>         </td>
      </tr>
      <tr>
         <td><p>245</p>         </td>
         <td><p> </p>         </td>
         <td><p>Incorrect file length</p>         </td>
      </tr>
      <tr>
         <td><p>246</p>         </td>
         <td><p> </p>         </td>
         <td><p>No file of this type for this client</p>         </td>
      </tr>
      <tr>
         <td><p>247</p>         </td>
         <td><p> </p>         </td>
         <td><p>No file of this type on this server</p>         </td>
      </tr>
      <tr>
         <td><p>248</p>         </td>
         <td><p> </p>         </td>
         <td><p>Identification type not supported</p>         </td>
      </tr>
      <tr>
         <td><p>249</p>         </td>
         <td><p> </p>         </td>
         <td><p>Nominative reference not supported</p>         </td>
      </tr>
      <tr>
         <td><p>250</p>         </td>
         <td><p> </p>         </td>
         <td><p>File already transferred</p>         </td>
      </tr>
      <tr>
         <td><p>251</p>         </td>
         <td><p> </p>         </td>
         <td><p>Reference type not supported</p>         </td>
      </tr>
      <tr>
         <td><p>252</p>         </td>
         <td><p> </p>         </td>
         <td><p>Start date too old</p>         </td>
      </tr>
      <tr>
         <td><p>253</p>         </td>
         <td><p> </p>         </td>
         <td><p>Incorrect date(s)</p>         </td>
      </tr>
      <tr>
         <td><p>254</p>         </td>
         <td><p> </p>         </td>
         <td><p>File service closed</p>         </td>
      </tr>
      <tr>
         <td><p>299</p>         </td>
         <td><p>All acknowledgment FPDUs</p>         </td>
         <td><p>Other fatal errors</p>         </td>
      </tr>
      <tr>
         <td><p>300</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>Congestion of local communication system</p>         </td>
      </tr>
      <tr>
         <td><p>301</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>Identification of called party unknown</p>         </td>
      </tr>
      <tr>
         <td><p>302</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>Called party not attached to a Service Access Point (SAP)</p>         </td>
      </tr>
      <tr>
         <td><p>303</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>Maximum number of connections reached</p>         </td>
      </tr>
      <tr>
         <td><p>304</p>         </td>
         <td><p>RelCONNECT AckCREATE AckSELECT ABORT</p>         </td>
         <td><p>Non-authorized requester identification</p>         </td>
      </tr>
      <tr>
         <td><p>305</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>SELECT negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>306</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>RESYN negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>307</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>SYNC negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>308</p>         </td>
         <td><p>RelCONNECT</p>         </td>
         <td><p>Version number not supported</p>         </td>
      </tr>
      <tr>
         <td><p>309</p>         </td>
         <td><p>RelCONNECT ABORT</p>         </td>
         <td><p>Too many connections already in progress</p>         </td>
      </tr>
      <tr>
         <td><p>310</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Network incident</p>         </td>
      </tr>
      <tr>
         <td><p>311</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Remote PeSIT protocol error</p>         </td>
      </tr>
      <tr>
         <td><p>312</p>         </td>
         <td><p>RelCONNECT (if partner inactive) ABORT/RELEASE</p>         </td>
         <td><p>Shutdown of service requested by the user</p>         </td>
      </tr>
      <tr>
         <td><p>313</p>         </td>
         <td><p>ABORT/RELEASE</p>         </td>
         <td><p>Connection closed due to inactivity</p>         </td>
      </tr>
      <tr>
         <td><p>314</p>         </td>
         <td><p>ABORT/RELEASE</p>         </td>
         <td><p>Unused connection closed to open a new connection</p>         </td>
      </tr>
      <tr>
         <td><p>315</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>316</p>         </td>
         <td><p>ABORT/RELEASE</p>         </td>
         <td><p>Connection closed by the administrator</p>         </td>
      </tr>
      <tr>
         <td><p>317</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Connection time-out</p>         </td>
      </tr>
      <tr>
         <td><p>318</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Mandatory PI missing or invalid</p>         </td>
      </tr>
      <tr>
         <td><p>319</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Incorrect number of records or bytes</p>         </td>
      </tr>
      <tr>
         <td><p>320</p>         </td>
         <td><p>ABORT</p>         </td>
         <td><p>Excessive number of re-synchronizations</p>         </td>
      </tr>
      <tr>
         <td><p>321</p>         </td>
         <td><p>RelCONNECT AckCREATE AckSELECT</p>         </td>
         <td><p>Call backup number</p>         </td>
      </tr>
      <tr>
         <td><p>322</p>         </td>
         <td><p>RelCONNECT AckCREATE AckSELECT</p>         </td>
         <td><p>Call back later</p>         </td>
      </tr>
      <tr>
         <td><p>323</p>         </td>
         <td><p> </p>         </td>
         <td><p>Incompatible CRC / connection mode</p>         </td>
      </tr>
      <tr>
         <td><p>324</p>         </td>
         <td><p> </p>         </td>
         <td><p>Incorrect requester identifier</p>         </td>
      </tr>
      <tr>
         <td><p>325</p>         </td>
         <td><p> </p>         </td>
         <td><p>Old password invalid</p>         </td>
      </tr>
      <tr>
         <td><p>326</p>         </td>
         <td><p> </p>         </td>
         <td><p>New password invalid</p>         </td>
      </tr>
      <tr>
         <td><p>327</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receive access temporarily closed</p>         </td>
      </tr>
      <tr>
         <td><p>328</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receive access not supported</p>         </td>
      </tr>
      <tr>
         <td><p>329</p>         </td>
         <td><p> </p>         </td>
         <td><p>Send access temporarily closed</p>         </td>
      </tr>
      <tr>
         <td><p>330</p>         </td>
         <td><p> </p>         </td>
         <td><p>Send access not supported</p>         </td>
      </tr>
      <tr>
         <td><p>331</p>         </td>
         <td><p> </p>         </td>
         <td><p>Excessive time-out value</p>         </td>
      </tr>
      <tr>
         <td><p>332</p>         </td>
         <td><p> </p>         </td>
         <td><p>Write not negotiated</p>         </td>
      </tr>
      <tr>
         <td><p>333</p>         </td>
         <td><p> </p>         </td>
         <td><p>Read not negotiated</p>         </td>
      </tr>
      <tr>
         <td><p>334</p>         </td>
         <td><p> </p>         </td>
         <td><p>Reverse charging refused</p>         </td>
      </tr>
      <tr>
         <td><p>335</p>         </td>
         <td><p> </p>         </td>
         <td><p>Invalid calling party number</p>         </td>
      </tr>
      <tr>
         <td><p>336</p>         </td>
         <td><p> </p>         </td>
         <td><p>Server date and time refused</p>         </td>
      </tr>
      <tr>
         <td><p>399</p>         </td>
         <td><p>All ABORT acknowledgment FPDUs</p>         </td>
         <td><p>Other fatal errors</p>         </td>
      </tr>
   </tbody>
</table>

### PeSIT reason code

<table>
   <th>
      <tr>
<th>PeSIT reason code         </th>
<th>Description         </th>
<th><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> internal
diagnostic         </th>
<th>Service item concerned         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Diagnostics imposing a re-synchronization </p>         </td>
      </tr>
      <tr>
         <td><p>100 </p>         </td>
         <td><p>Transmission error </p>         </td>
         <td><p>720 </p>         </td>
         <td><p>F.RESTART </p>         </td>
      </tr>
      <tr>
         <td><p>Diagnostics imposing a restart </p>         </td>
      </tr>
      <tr>
         <td><p>200 </p>         </td>
         <td><p>File characteristics insufficient </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>201 </p>         </td>
         <td><p>System resources temporarily insufficient </p>         </td>
         <td><p>916 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>202 </p>         </td>
         <td><p>User resources temporarily insufficient </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>203 </p>         </td>
         <td><p>Transfer not overriding </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>204 </p>         </td>
         <td><p>File already exists </p>         </td>
         <td><p>613 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>205 </p>         </td>
         <td><p>File does not exist </p>         </td>
         <td><p>610 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>206 </p>         </td>
         <td><p>Reception of the file will cause an overflow of the disk
quota </p>         </td>
         <td><p>611 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>207 </p>         </td>
         <td><p>File occupied </p>         </td>
         <td><p>635 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>208 </p>         </td>
         <td><p>File too old </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>209 </p>         </td>
         <td><p>Message of this type not accepted on the reference installation </p>         </td>
         <td><p>920 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>210 </p>         </td>
         <td><p>Presentation context negotiation failure </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.OPEN </p>         </td>
      </tr>
      <tr>
         <td><p>211 </p>         </td>
         <td><p>Not possible to open file </p>         </td>
         <td><p>604 </p>         </td>
         <td><p>F.OPEN </p>         </td>
      </tr>
      <tr>
         <td><p>212 </p>         </td>
         <td><p>Not possible to close file normally  </p>         </td>
         <td><p>605 </p>         </td>
         <td><p>F.CLOSE </p>         </td>
      </tr>
      <tr>
         <td><p>213 </p>         </td>
         <td><p>Inhibiting input/output error </p>         </td>
         <td><p>600 </p>         </td>
         <td><p>F.READ<br />
F.WRITE<br />
F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>214 </p>         </td>
         <td><p>Restart point negotiation failure  </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.READ<br />
F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>215 </p>         </td>
         <td><p>Specific system error </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>216 </p>         </td>
         <td><p>Intentional premature halt </p>         </td>
         <td><p>621 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>217 </p>         </td>
         <td><p>Too many synchronization points not acknowledged </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>218 </p>         </td>
         <td><p>Re-synchronization not possible </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>219 </p>         </td>
         <td><p>File space full </p>         </td>
         <td><p>614 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>220 </p>         </td>
         <td><p>Article longer than expected </p>         </td>
         <td><p>626 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>221 </p>         </td>
         <td><p>Expected end of transmission time </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>222 </p>         </td>
         <td><p>Too much data without synchronization points </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>223 </p>         </td>
         <td><p>Abnormal end of transfer </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr>
         <td><p>224 </p>         </td>
         <td><p>The size of the file sent is greater than the one announced
in F.CREATE </p>         </td>
         <td><p>600 </p>         </td>
         <td><p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr>
         <td><p>225 </p>         </td>
         <td><p>Workstation application congested: the file has effectively
been received but SCRS has not been able to give it to the workstation
application  </p>         </td>
         <td><p>600 </p>         </td>
         <td><p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr>
         <td><p>226 </p>         </td>
         <td><p>Transfer refusal </p>         </td>
         <td><p>904 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>299 </p>         </td>
         <td><p>Other </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
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
      <tr>
         <td><p>Diagnostics imposing a reconnection </p>         </td>
      </tr>
      <tr>
         <td><p>300 </p>         </td>
         <td><p>Local communication system congested  </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT  </p>         </td>
      </tr>
      <tr>
         <td><p>301 </p>         </td>
         <td><p>Identification requested not known </p>         </td>
         <td><p>909 </p>         </td>
         <td><p>F.CONNECT  </p>         </td>
      </tr>
      <tr>
         <td><p>302 </p>         </td>
         <td><p>Requested system not attached to a SSAP </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>303 </p>         </td>
         <td><p>Remote communication system congested<br />
(too many connections) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT  </p>         </td>
      </tr>
      <tr>
         <td><p>304 </p>         </td>
         <td><p>Requested identification not authorized (security) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.ABORT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>305 </p>         </td>
         <td><p>Negotiation failure (SELECT) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>306 </p>         </td>
         <td><p>Negotiation failure (RESYN) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>307 </p>         </td>
         <td><p>Negotiation failure (SYNC) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>308 </p>         </td>
         <td><p>Version number not supported  </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>309 </p>         </td>
         <td><p>Too many connections already in process for this processing
centre </p>         </td>
         <td><p>916 </p>         </td>
         <td><p>F.CONNECT<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>310 </p>         </td>
         <td><p>Network incident </p>         </td>
         <td><p>802 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>311 </p>         </td>
         <td><p>Remote PeSIT protocol error </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>312 </p>         </td>
         <td><p>Service closure requested by the user </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>313 </p>         </td>
         <td><p>Connection broken at the end of the TD inactivity interval </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>314 </p>         </td>
         <td><p>Connection used to host a new connection </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>315 </p>         </td>
         <td><p>Negotiation failure </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>316 </p>         </td>
         <td><p>Connection broken as a result of an administration command
 </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>317 </p>         </td>
         <td><p>Time-out </p>         </td>
         <td><p>740 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>318 </p>         </td>
         <td><p>Mandatory PI absent or illegal PI contents </p>         </td>
         <td><p>722 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>319 </p>         </td>
         <td><p>Number of bytes or articles incorrect </p>         </td>
         <td><p>620 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>320 </p>         </td>
         <td><p>Excessive number of resynchronizations for a transfer </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>321 </p>         </td>
         <td><p>Call the backup number </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>322 </p>         </td>
         <td><p>Call back later </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>399 </p>         </td>
         <td><p>Other </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.RELEASE<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
   </tbody>
</table>

<span id="ODETTE_Protocol__Diagnostic_Codes"></span>

## ODETTE Protocol Diagnostic Codes

These codes are specific to the ODETTE protocol and correspond to the
"ODETTE diagnostic code" transmitted by the protocol.

The values of these codes consist of the diagnostic code (two digits)
to which the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> adds 100 or 200 depending on the protocol phase concerned.

-   Values between 100 and 199 correspond to the "SFNA" (Start
    File Negative Answer) and "EFNA" (End File Negative Answer)
    protocol messages.
-   Values between 200 and 299 correspond to the "ESID" (End Session
    IDentification) protocol message.
-   This code forms the "NNN NNNN"-type DIAGP protocol diagnostic
    code. Values are expressed in decimal.

<table>
   <th>
      <tr>
<th>Error code         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>101</p>         </td>
         <td><p>File does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>102</p>         </td>
         <td><p>Target site does not exist for the file</p>         </td>
      </tr>
      <tr>
         <td><p>103</p>         </td>
         <td><p>Source site does not exist for the file</p>         </td>
      </tr>
      <tr>
         <td><p>104</p>         </td>
         <td><p>File format not supported</p>         </td>
      </tr>
      <tr>
         <td><p>105</p>         </td>
         <td><p>Record length error (length not supported)</p>         </td>
      </tr>
      <tr>
         <td><p>106</p>         </td>
         <td><p>File too big</p>         </td>
      </tr>
      <tr>
         <td><p>110</p>         </td>
         <td><p>Invalid number of records</p>         </td>
      </tr>
      <tr>
         <td><p>111</p>         </td>
         <td><p>Invalid number of characters</p>         </td>
      </tr>
      <tr>
         <td><p>112</p>         </td>
         <td><p>Fatal file input/output error (file access method problem)</p>         </td>
      </tr>
      <tr>
         <td><p>113</p>         </td>
         <td><p>File already exists</p>         </td>
      </tr>
      <tr>
         <td><p>199</p>         </td>
         <td><p>Non-referenced errors</p>         </td>
      </tr>
      <tr>
         <td><p>201</p>         </td>
         <td><p>NSDU (Network System Data Unit) not recognized (faulty
header)</p>         </td>
      </tr>
      <tr>
         <td><p>202</p>         </td>
         <td><p>Protocol error (reception of a invalid NSDU)</p>         </td>
      </tr>
      <tr>
         <td><p>203</p>         </td>
         <td><p>Requestee identification not known</p>         </td>
      </tr>
      <tr>
         <td><p>204</p>         </td>
         <td><p>Requester identifier not authorized or password incorrect</p>         </td>
      </tr>
      <tr>
         <td><p>205</p>         </td>
         <td><p>Congestion of local communication system (sudden shutdown
of communication system)</p>         </td>
      </tr>
      <tr>
         <td><p>206</p>         </td>
         <td><p>FPDU received with missing parameter or unexpected value</p>         </td>
      </tr>
      <tr>
         <td><p>207</p>         </td>
         <td><p>Invalid NSDU size received</p>         </td>
      </tr>
      <tr>
         <td><p>208</p>         </td>
         <td><p>User resources currently insufficient</p>         </td>
      </tr>
      <tr>
         <td><p>209</p>         </td>
         <td><p>End of time-out</p>         </td>
      </tr>
      <tr>
         <td><p>210</p>         </td>
         <td><p>Incorrect number of records. The number transported by
the EFID FPDU does not correspond to the number of received records counted
by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> (F- or V-format files)</p>         </td>
      </tr>
      <tr>
         <td><p>211</p>         </td>
         <td><p>Number of characters incorrect. The number transported
by the EFID FPDU does not correspond to the number of received characters
counted by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> (T- or U-format files)</p>         </td>
      </tr>
   </tbody>
</table>
