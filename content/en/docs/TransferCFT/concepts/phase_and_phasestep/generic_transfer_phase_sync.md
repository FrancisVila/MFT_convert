{
    "title": "Generic transfer phase progression",
    "linkTitle": "Generic transfer phase progression",
    "weight": "220"
}A generic transfer cannot progress to the next phase until the last of its children has passed to the following phase.

The table below shows a generic transfer A0000001, in the phase <span class="bold_in_para">A</span> along with its children A0000002 through A000000n.

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>A</p>
<p>Pre-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>T</p>
<p>Transfer</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>Y</p>
<p>Post-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>Z</p>
<p>Ack-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1" style="font-size: 9pt"><p>X</p>
<p>Done</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>A0000001</strong>         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>A0000002         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>A0000003         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>A0000004         </td>
         <td>         </td>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>A0000005         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>A000000n         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

The child transfers begin to pass through the preprocessing, transfer, and post-processing phases.

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>A</p>
<p>Pre-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>T</p>
<p>Transfer</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>Y</p>
<p>Post-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>Z</p>
<p>Ack-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1" style="font-size: 9pt"><p>X</p>
<p>Done</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>A0000001</strong>         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>A0000002         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>A0000003         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>A0000004         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>A0000005         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td><strong>A000000n</strong>         </td>
      </tr>
   </tbody>
</table>

The generic transfer, however, must wait for its last child transfer to move to the next phase and then immediately follows its phases.

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>A</p>
<p>Pre-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>T</p>
<p>Transfer</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>Y</p>
<p>Post-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt"><p>Z</p>
<p>Ack-processing</p>         </th>
<th style="text-align: center;" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1" style="font-size: 9pt"><p>X</p>
<p>Done</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>          </td>
         <td><strong>A0000001</strong>         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>A0000002         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>A0000003         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td><p>A0000004</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>A0000005         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td><strong>A000000n</strong>         </td>
      </tr>
   </tbody>
</table>

**Results**

The child transfers A0000003 through n are completed, and A0000002 now is in the transfer phase (the execution closely follows the last child's).

The following rules apply to the above generic/child phase processing:

-   If a generic transfer is waiting for a child, its phasestep is Hold if no child in the current phase is in error, otherwise it is Keep.
-   If a generic transfer needs to run a preprocessing script, it does this prior to generating its children.
-   If a generic transfer needs to run a post-processing script, it waits for every child to finish their script first.
-   If a generic transfer needs to run a acknowledgement script, it waits for every child to finish their script first.

You can set the policies defining which transfer executes the script using the execution parameters described in [Processing execution policy](../../about_transfer_processing/processing_exec_policy).
