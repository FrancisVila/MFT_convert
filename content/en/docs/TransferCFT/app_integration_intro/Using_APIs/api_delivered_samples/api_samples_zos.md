{
    "title": "Delivered templates for z/OS",
    "linkTitle": "Delivered templates for z/OS",
    "weight": "380"
}This topic lists the Axway Transfer CFT API templates that are delivered for the z/OS platform. You may decide to use the delivered samples as a basis for integrating APIs, or as a model to create your own. Templates include samples in:

-   [Assembler language](#assembl)
-   [C language](#c)
-   [COBOL language](#cobol)

The Transfer CFT z/OS templates are located in the installed Transfer CFT distribution library.

## <span id="Assembl"></span> Assembler language

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Template</th>
         <th>Function</th>
         <th>
            <p>Services</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">AAPIDLL</p>
         </td>
         <td>cftai - cftac - cftinit         </td>
         <td>COM - SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">AXPIDLL</p>
         </td>
         <td>cftaix - cftac - cftinit         </td>
         <td>COM - SEND - OPEN - CLOSE - DO - SELECT (NEXT or NEXT240)         </td>
      </tr>
   </tbody>
</table>

## <span id="C"></span> C language

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Template</th>
         <th>Function</th>
         <th>
            <p>Services</p>
</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">CAPI2A</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize-ipcai2_catalog_open-ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close-ipcai2_finalize-               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
         <td><span>Transfer CFT</span> catalog API sample program, listing all catalog content.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">CAPI2B</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
         <td><span>Transfer CFT</span> catalog API sample program, which changes all Terminated transfers to Ended.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">CAPIC</p>
         </td>
         <td>cftai - cftac - cftau         </td>
         <td>OPEN- SELECT - NEXT - MODIFY - CLOSE - SEND -RECV - HALT - START - DELETE         </td>
         <td>C Sample for <span>Transfer CFT</span> API.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">CAPISYN</p>
         </td>
         <td>cftau         </td>
         <td>COM - SEND - GETXINFO - SWAITCAT         </td>
         <td><span>Transfer CFT</span> communication sample program using
Synchronous Communication media  (multiple send commands are possible).         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">CAPIW</p>
         </td>
         <td>cftai - cftau          </td>
         <td>SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
         <td>Perform a SEND request with an IDA and wait for the transfer to end (completed) until the timer expires or the transfer is aborted.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">CAPIX</p>
         </td>
         <td>cftaix         </td>
         <td>OPEN - CLOSE - SELECT (NEXT - NEXT240) - SORT - DO - COUNT         </td>
         <td>A C language template for a  catalog list with selection and sorting.         </td>
      </tr>
   </tbody>
</table>

## <span id="COBOL"></span>COBOL language

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Template</th>
         <th>Function</th>
         <th>
            <p>Services</p>
</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2A</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
         <td><span>Transfer CFT</span> catalog API template program, which lists all catalog content.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2AS</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
         <td><span>Transfer CFT</span> catalog API template program, which lists all of the catalog content.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2B</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize-               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
         <td><span>Transfer CFT</span> catalog API template program, which changes all successful transfers to a completed state.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2BS</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get-               </li>
               <li>ipcai2_catalog_info_get-               </li>
               <li>ipcai2_catalog_selection_delete-               </li>
               <li>ipcai2_catalog_close-               </li>
               <li>ipcai2_finalize-               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
         <td><span>Transfer CFT</span> catalog API template program, which changes all successful transfers to the completed state.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIC</p>
         </td>
         <td>CFTC         </td>
         <td>SEND -RECV - HALT - START - DELETE         </td>
         <td>
            <p>Issue <span>Transfer CFT</span> commands.</p>
         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPICS</p>
         </td>
         <td>CFTC         </td>
         <td>SEND -RECV - HALT - START - DELETE         </td>
         <td>Issue <span>Transfer CFT</span> commands         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPII</p>
         </td>
         <td>CFTI         </td>
         <td>OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
         <td>
            <p>List the <span>Transfer CFT</span> catalog.</p>
         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIIS</p>
         </td>
         <td>CFTI         </td>
         <td>OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
         <td>List the <span>Transfer CFT</span> catalog.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPISYN</p>
         </td>
         <td>cftau         </td>
         <td>COM - SEND - GETXINFO - SWAITCAT         </td>
         <td><span>Transfer CFT</span> communication sample program using
the synchronous communication media, where multiple SEND commands are possible.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIW</p>
         </td>
         <td>CFTI - CFTU         </td>
         <td>SEND, OPEN, CLOSE , (SELECT - NEXT), or (SELECT240 - NEXT240)         </td>
         <td>Perform a SEND request with an IDA and wait  for the transfer to complete successfully, reach the time out, or abort the transfer.         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIWS</p>
         </td>
         <td>CFTI - CFTU         </td>
         <td>SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
         <td>Perform a SEND request with an IDA and wait  for the transfer to complete successfully, reach the time out, or abort the transfer.         </td>
      </tr>
   </tbody>
</table>

 

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Template</th>
         <th>Function</th>
         <th>
            <p>Services</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2A</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2AS</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2B</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize-               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get               </li>
               <li>ipcai2_catalog_info_get               </li>
               <li>ipcai2_catalog_selection_delete               </li>
               <li>ipcai2_catalog_close               </li>
               <li>ipcai2_finalize               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPI2BS</p>
         </td>
         <td>ipcai2_*         </td>
         <td>
            <ul>
               <li>ipcai2_initialize               </li>
               <li>ipcai2_catalog_open               </li>
               <li>ipcai2_catalog_selection_new               </li>
               <li>ipcai2_catalog_selection_set               </li>
               <li>ipcai2_catalog_selection_sortby               </li>
               <li>ipcai2_catalog_selection_skip               </li>
               <li>ipcai2_catalog_selection_next               </li>
               <li>ipcai2_catalog_record_get-               </li>
               <li>ipcai2_catalog_info_get-               </li>
               <li>ipcai2_catalog_selection_delete-               </li>
               <li>ipcai2_catalog_close-               </li>
               <li>ipcai2_finalize-               </li>
               <li>ipcai2_get_errno_str               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIC </p>
         </td>
         <td>CFTC         </td>
         <td>SEND -RECV - HALT - START - DELETE         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPICS</p>
         </td>
         <td>CFTC         </td>
         <td>SEND -RECV - HALT - START - DELETE         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPII</p>
         </td>
         <td>CFTI         </td>
         <td>OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIIS</p>
         </td>
         <td>CFTI         </td>
         <td>OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPISYN</p>
         </td>
         <td>cftau         </td>
         <td>COM - SEND - GETXINFO - SWAITCAT         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIW</p>
         </td>
         <td>CFTI - CFTU         </td>
         <td>SEND, OPEN, CLOSE , (SELECT - NEXT), or (SELECT240 - NEXT240)         </td>
      </tr>
      <tr>
         <td>
<p data-mc-conditions="axway_conditions.ScreenOnly">OAPIWS</p>
         </td>
         <td>CFTI - CFTU         </td>
         <td>SEND - OPEN - CLOSE - (SELECT - NEXT) or (SELECT240 - NEXT240)         </td>
      </tr>
   </tbody>
</table>
