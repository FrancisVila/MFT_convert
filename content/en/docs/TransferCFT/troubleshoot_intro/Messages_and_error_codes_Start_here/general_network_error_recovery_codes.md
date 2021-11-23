{
    "title": "RECOV: General  network error recovery codes",
    "linkTitle": "General network error recovery codes",
    "weight": "440"
}<span id="RECOV___General_Network_Error_Recovery_Codes"></span>RECOV corresponds to the code common to all network access methods,
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

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Code         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Normal remote end disconnection</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>L=1 Local time-out</p>
<p>L=0 Network time-out</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>L=1 Insufficient local resources</p>
<p>L=0 Protocol procedure error</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>No more contexts available</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Incoming connection request while the maximum number of
sessions (MAXCNX) for this resource has been reached</p>         </td>
      </tr>
      <tr>
         <td><p>9</p>         </td>
         <td><p>Other non-fatal problems</p>         </td>
      </tr>
      <tr>
         <td><p>64</p>         </td>
         <td><p>Invalid call syntax</p>         </td>
      </tr>
      <tr>
         <td><p>67</p>         </td>
         <td><p>Incorrect remote address</p>         </td>
      </tr>
      <tr>
         <td><p>68</p>         </td>
         <td><p>Incorrect local address</p>         </td>
      </tr>
      <tr>
         <td><p>99</p>         </td>
         <td><p>The resources are temporarily unavailable</p>         </td>
      </tr>
      <tr>
         <td><p>128</p>         </td>
         <td><p>Malfunctions on the network</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>Undefined refusal reason</p>         </td>
      </tr>
   </tbody>
</table>
