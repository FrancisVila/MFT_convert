{
    "title": "About phase and phasestep",
    "linkTitle": "About phase and phasestep",
    "weight": "180"
}Transfer CFT provides a complete processing workflow that includes file preprocessing, transfer processing, post processing script execution and acknowledgement. As  of Transfer CFT 3.0 processing features have evolved, replacing the former state with the Phase/Phase step pair, to improve the visibility of a flow. The processing phase shows where you are in your transfer. Within each phase there is a phase step, which can be either a process or a step.

This topic presents processing concepts, step overviews in the following sections:

-   [Types of processing phases](#types)
-   [Phasesteps in each phase](#types2)
-   [About backward compatibility](#about)
-   [Example usage](#example)

## <span id="Types"></span>Types of processing phases

The term phase refers to the highest level in the transfer flow cycle:

-   \(A\) Pre-processing: All pre-transfer script execution occurs here
-   \(T\) Transferring: All transfer execution occurs in this phase
-   \(Y\) Post-processing: All post-transfer script execution occurs here
-   \(Z\) Acknowledgement: Acknowledgement reception/send steps and ack script execution occur here
-   \(X\) Done: End condition when all of the previous phases are completed

![](temp_phase_steps.png)

## <span id="Types2"></span>Phasesteps in each phase

The phasestep refers to the details that can occur during any given phase:

-   \(D\) At disposal: The processing of the Phase is ready to be executed; it is ready to go.
-   \(H\) Hold: The processing of the Phase is on hold and waiting for an action to be executed.
-   \(C\) Processing/Current: The Phase processing is being executed.
-   \(K\) Keep: The Phase processing is stopped.
-   \(X\) Done: This phase step only exists for the Done phase, once all previous phases are complete.
-   \(E\) Exit EOT: This phase step only exists for the Post-processing phase, to signal an [end-of-transfer exit](../../../app_integration_intro/managing_exits/about_the_end_of_transfer_type_exit).

![](temp_phase_steps.png)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The CFTSTATE in the Transfer CFT catalog corresponds to the transfer state in diagrams and tables.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Phase</th>
         <th>Phasestep </th>
         <th><a name="State"></a>State</th>
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
         <td>Pre-processing is waiting resource to start         </td>
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
         <td>Hold transfer (H)         </td>
         <td>Transfer available (diagi=0) or interrupted (diagi &lt;&gt; 0)         </td>
      </tr>
      <tr>
         <td>Transfer (T)         </td>
         <td>Available (D)         </td>
         <td>Available (D)         </td>
         <td>Transfer is waiting on a resource to start         </td>
      </tr>
      <tr>
         <td>Transfer (T)         </td>
         <td>Processing (C)         </td>
         <td>Processing (C)         </td>
         <td>Transfer  is in progress         </td>
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
         <td>Post-processing (Y)         </td>
         <td>Post-processing is interrupted         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Exit EOT (E)         </td>
         <td>Post-processing (Y)         </td>
         <td>Exit in progress         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Available (D)         </td>
         <td>Post-processing  (Y)         </td>
         <td>Post-processing  is waiting for a resource to start         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Processing (C)         </td>
         <td>Post-processing  (Y)         </td>
         <td>Post-processing in progress         </td>
      </tr>
      <tr>
         <td>Post-processing (Y)         </td>
         <td>Killed (K)         </td>
         <td>Post-processing   (Y)         </td>
         <td>Post-processing is canceled         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Hold (H)         </td>
         <td>Ack (Z)         </td>
         <td>Transfer request waits for an application acknowledgement before continuing the flow         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Available (D)         </td>
         <td>Ack  (Z)         </td>
         <td>Ack processing is not started         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Processing (C)         </td>
         <td>Ack (Z)         </td>
         <td>Ack processing in progress         </td>
      </tr>
      <tr>
         <td>Ack (Z)         </td>
         <td>Killed (K)         </td>
         <td>Ack  (Z)         </td>
         <td>Ack processing is canceled         </td>
      </tr>
      <tr>
         <td>Done (X)         </td>
         <td>Done (X)         </td>
         <td>Done (X)         </td>
         <td>Flow finished         </td>
      </tr>
   </tbody>
</table>

## <span id="About"></span>About backward compatibility

For continued compatibility and to help in transitioning, clients may still use the former states, which were not modified. Alternately, they can use the adapted states that reflect the phase and phase step. See [Compatibility](../processing_compatability).

## <span id="Example"></span>Example usage

This guide provides the following usage example for implementation: [Adding a zip script.](../../about_transfer_processing/preprocess_use_case2)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See <a href="../../about_transfer_processing/proc_commands">Processing commands: general usage</a> for a description of the processing command parameters and values.         </td>
      </tr>
</table>
