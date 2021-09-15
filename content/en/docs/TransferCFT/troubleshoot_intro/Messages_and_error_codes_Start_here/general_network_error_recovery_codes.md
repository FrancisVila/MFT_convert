{
    "title": "General network error recovery codes",
    "linkTitle": "General network error recovery codes",
    "weight": "460"
}# <span id="title"></span>RECOV: General network error recovery codes

<span id="RECOV___General_Network_Error_Recovery_Codes"></span>RECOV corresponds to the code common to all network access methods,
providing a general indication about the cause of the error.

One value can correspond to two causes, depending on whether the source
of the error is at the local or remote end; "L" is indicated
in case of ambiguity:

-   L=1:
    local
-   L=0:
    remote

The codes are expressed in decimal form.

RECOV - General Network Error Recovery Codes

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
                            Code
                        </th>
         <th>
                            Meaning
                        </th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="28.271%">
            <p>1</p>
         </td>
         <td width="71.729%">
            <p>Normal remote end disconnection</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>2</p>
         </td>
         <td width="71.729%">
            <p>L=1 Local time-out</p>
            <p>L=0 Network time-out</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>3</p>
         </td>
         <td width="71.729%">
            <p>L=1 Insufficient local resources</p>
            <p>L=0 Protocol procedure error</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>4</p>
         </td>
         <td width="71.729%">
            <p>No more contexts available</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>5</p>
         </td>
         <td width="71.729%">
            <p>Incoming connection request while the maximum number of 
 sessions (MAXCNX) for this resource has been reached</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>9</p>
         </td>
         <td width="71.729%">
            <p>Other non-fatal problems</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>64</p>
         </td>
         <td width="71.729%">
            <p>Invalid call syntax</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>67</p>
         </td>
         <td width="71.729%">
            <p>Incorrect remote address</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>68</p>
         </td>
         <td width="71.729%">
            <p>Incorrect local address</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>99</p>
         </td>
         <td width="71.729%">
            <p>The resources are temporarily unavailable</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p>128</p>
         </td>
         <td width="71.729%">
            <p>Malfunctions on the network</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.271%">
            <p> </p>
         </td>
         <td width="71.729%">
            <p>Undefined refusal reason</p>
         </td>
      </tr>
   </tbody>
</table>
