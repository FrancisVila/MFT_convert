{
    "title": "Monitoring a PeSIT Hors SIT transfer",
    "linkTitle": "Monitoring a PeSIT transfer",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[PeSIT diagnostic codes](#PeSIT_diagnostic_codes)

[Protocol trace messages](#Protocol_trace_messages)

<span id="PeSIT_diagnostic_codes"></span>

## PeSIT diagnostic codes

The following protocol diagnostic return codes are found in end-of-transfer exits and in the log file:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>PeSIT diagnostic codes</p>         </td>
      </tr>
      <tr>
         <td><p>000</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>100</p>         </td>
         <td><p>Transmission error</p>         </td>
      </tr>
      <tr>
         <td><p>200</p>         </td>
         <td><p>Insufficient file attributes</p>         </td>
      </tr>
      <tr>
         <td><p>201</p>         </td>
         <td><p>System resources temporarily insufficient</p>         </td>
      </tr>
      <tr>
         <td><p>202</p>         </td>
         <td><p>User resources temporarily insufficient</p>         </td>
      </tr>
      <tr>
         <td><p>203</p>         </td>
         <td><p>Non-priority transfer</p>         </td>
      </tr>
      <tr>
         <td><p>204</p>         </td>
         <td><p>File already exists</p>         </td>
      </tr>
      <tr>
         <td><p>205</p>         </td>
         <td><p>File does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>206</p>         </td>
         <td><p>Receiving the file will exceed the disk quota</p>         </td>
      </tr>
      <tr>
         <td><p>207</p>         </td>
         <td><p>File busy</p>         </td>
      </tr>
      <tr>
         <td><p>208</p>         </td>
         <td><p>File too old (predates D-2 in the SIT context)</p>         </td>
      </tr>
      <tr>
         <td><p>209</p>         </td>
         <td><p>Message type not accepted on the specified installation</p>         </td>
      </tr>
      <tr>
         <td><p>210</p>         </td>
         <td><p>Presentation context negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>211</p>         </td>
         <td><p>File cannot be opened</p>         </td>
      </tr>
      <tr>
         <td><p>212</p>         </td>
         <td><p>File cannot be closed normally</p>         </td>
      </tr>
      <tr>
         <td><p>213</p>         </td>
         <td><p>Blocking I/O error</p>         </td>
      </tr>
      <tr>
         <td><p>214</p>         </td>
         <td><p>Restart point negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>215</p>         </td>
         <td><p>System error</p>         </td>
      </tr>
      <tr>
         <td><p>216</p>         </td>
         <td><p>Intentional premature shutdown</p>         </td>
      </tr>
      <tr>
         <td><p>217</p>         </td>
         <td><p>Too many synchronization points without acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>218</p>         </td>
         <td><p>Resynchronization not possible</p>         </td>
      </tr>
      <tr>
         <td><p>219</p>         </td>
         <td><p>No more file space</p>         </td>
      </tr>
      <tr>
         <td><p>220</p>         </td>
         <td><p>Record longer than expected</p>         </td>
      </tr>
      <tr>
         <td><p>221</p>         </td>
         <td><p>End-of-transmission timeout</p>         </td>
      </tr>
      <tr>
         <td><p>222</p>         </td>
         <td><p>Too much data without synchronization point</p>         </td>
      </tr>
      <tr>
         <td><p>223</p>         </td>
         <td><p>Transfer ended abnormally</p>         </td>
      </tr>
      <tr>
         <td><p>224</p>         </td>
         <td><p>The file sent is bigger than the one specified in F.CREATE</p>         </td>
      </tr>
      <tr>
         <td><p>225</p>         </td>
         <td><p>Workstation application congestion: the file was received but CRS could not transfer it to the workstation application</p>         </td>
      </tr>
      <tr>
         <td><p>226</p>         </td>
         <td><p>Transfer refused</p>         </td>
      </tr>
      <tr>
         <td><p>299</p>         </td>
         <td><p>Other</p>         </td>
      </tr>
      <tr>
         <td><p>300</p>         </td>
         <td><p>Congestion in local communication system</p>         </td>
      </tr>
      <tr>
         <td><p>301</p>         </td>
         <td><p>Called party identification not known</p>         </td>
      </tr>
      <tr>
         <td><p>302</p>         </td>
         <td><p>Called party not attached to an SSAP</p>         </td>
      </tr>
      <tr>
         <td><p>303</p>         </td>
         <td><p>Congestion in the remote communication system (too many connections)</p>         </td>
      </tr>
      <tr>
         <td><p>304</p>         </td>
         <td><p>Initiator identification not allowed (security)</p>         </td>
      </tr>
      <tr>
         <td><p>305</p>         </td>
         <td><p>Negotiation failure: SELECT</p>         </td>
      </tr>
      <tr>
         <td><p>306</p>         </td>
         <td><p>Negotiation failure: RESYN</p>         </td>
      </tr>
      <tr>
         <td><p>307</p>         </td>
         <td><p>Negotiation failure: SYNC</p>         </td>
      </tr>
      <tr>
         <td><p>308</p>         </td>
         <td><p>Version number not supported</p>         </td>
      </tr>
      <tr>
         <td><p>309</p>         </td>
         <td><p>Too many connections already in progress for this CT</p>         </td>
      </tr>
      <tr>
         <td><p>310</p>         </td>
         <td><p>Network fault</p>         </td>
      </tr>
      <tr>
         <td><p>311</p>         </td>
         <td><p>Remote PeSIT protocol error</p>         </td>
      </tr>
      <tr>
         <td><p>312</p>         </td>
         <td><p>Requested service closed</p>         </td>
      </tr>
      <tr>
         <td><p>313</p>         </td>
         <td><p>Connection interrupted at the end of TD inactivity time</p>         </td>
      </tr>
      <tr>
         <td><p>314</p>         </td>
         <td><p>Unused connection disconnected to allow a new connection</p>         </td>
      </tr>
      <tr>
         <td><p>315</p>         </td>
         <td><p>Negotiation failure</p>         </td>
      </tr>
      <tr>
         <td><p>316</p>         </td>
         <td><p>Connection disconnected due to administration command</p>         </td>
      </tr>
      <tr>
         <td><p>317</p>         </td>
         <td><p>Timer failure</p>         </td>
      </tr>
      <tr>
         <td><p>318</p>         </td>
         <td><p>Mandatory PI missing or illegal PI content</p>         </td>
      </tr>
      <tr>
         <td><p>319</p>         </td>
         <td><p>Incorrect number of bytes or records</p>         </td>
      </tr>
      <tr>
         <td><p>320</p>         </td>
         <td><p>Too many resynchronizations for a transfer</p>         </td>
      </tr>
      <tr>
         <td><p>321</p>         </td>
         <td><p>Call standby number</p>         </td>
      </tr>
      <tr>
         <td><p>322</p>         </td>
         <td><p>Call back later</p>         </td>
      </tr>
      <tr>
         <td><p>399</p>         </td>
         <td><p>Other</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Protocol_trace_messages"></span>

## Protocol trace messages

Each protocol command or response corresponds to a protocol trace message that you can record in the log file. The protocol trace is an optional feature that you define for transfer activity for a given Site.

You can enable or disable trace printing for a Site object at either of the following stages:

-   During Site creation
-   On modifying attributes of an existing Site
-   During Gateway processing (dynamically)

Enabling or disabling protocol tracing using this method is only valid for the current session. The update is lost when you stop Gateway.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
