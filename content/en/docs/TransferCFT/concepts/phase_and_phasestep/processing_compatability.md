{
    "title": "Transfer CFT backward compatibility ",
    "linkTitle": "Transfer CFT backward compatibility ",
    "weight": "250"
}In some cases, you may require or prefer backward compatibility. In this case, the uconf:cft.state\_compat and uconf:cft.listcat\_compat parameters can provide the same functionality as in Transfer CFT 2.7.1.

The default value (No) sets:

-   LISTCAT to version 3.0 or higher
-   State to an adapted state, which corresponds to the phase and phase steps described in this section

![](temp_compat.png)

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Phase</th>
         <th>Phasestep </th>
         <th>State</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Pre-processing (A)         </td>
         <td>Hold (H)         </td>
         <td>Pre-processing (A)         </td>
         <td>Pre-processing available         </td>
      </tr>
      <tr>
         <td>Pre-processing (A)         </td>
         <td>Available (D)         </td>
         <td>Pre-processing (A)         </td>
         <td>Pre-processing is waiting on a resource to start         </td>
      </tr>
      <tr>
         <td>Pre-processing (A)         </td>
         <td>Processing (C)         </td>
         <td>Pre-processing (A)         </td>
         <td>Pre-processing in progress         </td>
      </tr>
      <tr>
         <td>Pre-processing (A)         </td>
         <td>Killed (K)         </td>
         <td>Pre-processing (A)         </td>
         <td>Pre-processing is canceled         </td>
      </tr>
      <tr>
         <td>Transfer (T)         </td>
         <td>Hold (H)         </td>
         <td>Hold (H)         </td>
         <td>Transfer available (diagi=0) or interrupted (diagi &lt;&gt; 0)         </td>
      </tr>
      <tr>
         <td>Transfer (T)         </td>
         <td>Available (D)         </td>
         <td>Available (D)         </td>
         <td>Transfer  is waiting resource to start         </td>
      </tr>
      <tr>
         <td>Transfer (T)         </td>
         <td>Processing (C)         </td>
         <td>Processing (C)         </td>
         <td>Transfer is in progress         </td>
      </tr>
      <tr>
         <td>Transfer (T)         </td>
         <td>Killed (K)         </td>
         <td>Killed (K)         </td>
         <td>Transfer is canceled         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Hold (H)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Post-processing is interrupted         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Exit EOT (E)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Exit in progress         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Available (D)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Post-processing  is waiting resource to start         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Processing (C)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Post-processing in progress         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Killed (K)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Post-processing is canceled         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Hold (H)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Ack processing is interrupted         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Processing (C)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Ack processing is not started         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Available (D)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Ack processing in progress         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Killed (K)         </td>
         <td>Transfer finished (T) or post-processing executed (X)         </td>
         <td>Ack processing is canceled         </td>
      </tr>
      <tr>
         <td>Done (X)          </td>
         <td>Done (X)         </td>
         <td>Done (T or X)         </td>
         <td>Flow finished         </td>
      </tr>
   </tbody>
</table>

## <span id="Compatibility unified configuration parameters"></span>Compatibility parameters in unified configuration

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Default value</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Uconf:cft.listcat_compat         </td>
         <td>No         </td>
         <td>
            <p>Defines the LISTCAT display:</p>
            <ul>
               <li>Yes = Display using the former product format, which does not include the new columns. The format in LISTCAT is DTSA.               </li>
               <li>No= Display using the product version 3.0 and higher catalog format. The format in LISTCAT is DTSASPP.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Uconf:cft.state_compat	         </td>
         <td>No          </td>
         <td>
            <p>Defines the transfer states:</p>
            <ul>
               <li>Yes= The phase state is fully compatible with the states in versions prior to 3.0.               </li>
               <li>No = The state reflects the phase used in Transfer CFT 3.0 and higher. This uses phase instead of the former states, except during the Transfer phase, when the former state is the same as the phase step.               </li>
            </ul>
            <p><span>Note</span>: Uconf:cft.state_compat also impacts the <a href="../ack_phase">acknowledgement</a> behavior if ackstate is set to ignore.</p>
         </td>
      </tr>
   </tbody>
</table>
