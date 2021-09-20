{
    "title": "PeSIT variables",
    "linkTitle": "PeSIT variables",
    "weight": "330"
}The following expressions are valid in transfer profiles:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Expression</th>
         <th>PeSIT PI code</th>
         <th>Applicability to Push / Pull operations</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>${pesit.crc}</code>
         </td>
         <td>PI 1         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.diagCode}</code>
         </td>
         <td>PI 2         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.callerID}</code>
         </td>
         <td>PI 3         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.senderID}</code>
         </td>
         <td>PI 3         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.serverID}</code>
         </td>
         <td>PI 4         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.receiverID}</code>
         </td>
         <td>PI 4         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.version}</code>
         </td>
         <td>PI 6         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.checkPointInterval}</code>
         </td>
         <td>PI 7         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.checkPointWindow}</code>
         </td>
         <td>PI 7         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.fileType}</code>
         </td>
         <td>PI 11         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.fileName}</code>
         </td>
         <td>PI 12         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.transferID}</code>
         </td>
         <td>PI 13         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.fileAttributes}</code>
         </td>
         <td>PI 14         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.restart}</code>
         </td>
         <td>PI 15         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.dataEncoding}</code>
         </td>
         <td>PI 16         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.priority}</code>
         </td>
         <td>PI 17         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.restartCheckPoint}</code>
         </td>
         <td>PI 18         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.cancelCode}</code>
         </td>
         <td>PI 19         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.checkPointNumber}</code>
         </td>
         <td>PI 20         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.compressed}</code>
         </td>
         <td>PI 21         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.compressionType}</code>
         </td>
         <td>PI 21         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.accessType}</code>
         </td>
         <td>PI 22         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.resyncAllowed}</code>
         </td>
         <td>PI 23         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.exchangeBufferSize}</code>
         </td>
         <td>PI 25         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.totalBytes}</code>
         </td>
         <td>PI 27         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.totalRecords}</code>
         </td>
         <td>PI 28         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.diagnosticText}</code>
         </td>
         <td>PI 29         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.recordFormat}</code>
         </td>
         <td>PI 31         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.recordLength}</code>
         </td>
         <td>PI 32         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.fileOrganization}</code>
         </td>
         <td>PI 33         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.fileLabel}</code>
         </td>
         <td>PI 37         </td>
         <td>Both Push and Pull         </td>
      </tr>
      <tr>
         <td><code>${pesit.keyLength}</code>
         </td>
         <td>PI 38         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.keyOffset}</code>
         </td>
         <td>PI 39         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.allocationUnit}</code>
         </td>
         <td>PI 41         </td>
         <td>Push only         </td>
      </tr>
      <tr>
         <td><code>${pesit.allocationSize}</code>
         </td>
         <td>PI 42         </td>
         <td>Push only         </td>
      </tr>
      <tr>
         <td><code>${pesit.creationDateTime}</code>
         </td>
         <td>PI 51         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.extractionDateTime}</code>
         </td>
         <td>PI 52         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${extractionDateTimepesit.originalSenderID}</code>
         </td>
         <td>PI 61         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.finalDestinationID}</code>
         </td>
         <td>PI 62         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.msgData}</code>
         </td>
         <td>PI 91         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.serviceParam}</code>
         </td>
         <td>PI 99         </td>
         <td>Pull only         </td>
      </tr>
      <tr>
         <td><code>${pesit.accountName}</code>
         </td>
         <td>—         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.datetime}</code>
         </td>
         <td>—         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><code>${pesit.details}</code>
         </td>
         <td>—         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

 

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The expressions <code>${pesit.originalSenderID}</code> and are <code>${pesit.finalDestinationID}</code> are set only for routed transfers.         </td>
      </tr>
</table>
