{
    "title": "C API usage examples",
    "linkTitle": "Usage examples",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Customizing Gateway Processes

[Overview](#overview)

[Transfers](#transfers)

[Messages](#messages)

<span id="overview"></span>

## Overview

Use C API primitive calls to implement actions on Transfers and messages.

User programs always call:

-   **GikSessionOpen()** primitive to start communication with Gateway
-   <span style="font-weight: bold;">GikSessionOpenFromNotif()</span> primitive to use call the API from external exits
-   <span style="font-weight: bold;">GikSessionClose()</span> primitive to end communication
-   <span style="font-weight: bold;">GikSessionCloseFromNotif()</span> primitive to close a session that was opened with GikSessionOpenFromNotif()

<span id="transfers"></span>

## Transfers

### Submitting Transfers

Use the following primitives to submit Transfers:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen(cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open the communication session</p>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams(GIK_TRANSFER, &amp;params)</p>         </td>
         <td><p>To initialize a parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSetxxx(params, fieldIdent_1, value_1</p>
<p>GikSetxxx(params, fieldIdent_i, value_i)</p>
<p>GikSetxxx(params, fieldIdent_n, value_n)</p>         </td>
         <td><p>To set the value of the fieldIdent field in the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferPut(session, params, &amp;ident)</p>         </td>
         <td><p>To retrieve the Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams(params)</p>         </td>
         <td><p>To free the handle on the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

### Retrieving Transfer parameters

Use the following primitives to retrieve Transfer parameters:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen(cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open the communication session</p>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams(GIK_TRANSFER, &amp;params)</p>         </td>
         <td><p>To retrieve a parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferGet(session, option, &amp;ident, params)</p>         </td>
         <td><p>To retrieve a Transfer Request and copy the Transfer parameters to the parameters list <em>xferParams</em>.</p>
<p>The value of:</p>
<ul>
<li><em>option</em> is XFER_LOCK or 0</li>
<li><em>ident</em> is the Transfer Request identifier supplied by the user</li>
<li><em>params</em> is the parameters list built by the GikXferGet primitive</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>GikGetxxx(params, fieldIdent_1, &amp;value_1)</p>
<p>GikGetxxx(params, fieldIdent_i, &amp;value_i)</p>
<p>GikGetxxx(params, fieldIdent_n, &amp;value_n)</p>         </td>
         <td><p>To retrieve the value of the fieldIdent field from the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams(params)</p>         </td>
         <td><p>To free the handle on the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

### Updating Transfers

Use the following primitives to update Transfers:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen(cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open the session</p>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams(GIK_TRANSFER, &amp;params)</p>         </td>
         <td><p>To retrieve the handle on a parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferGet(session, option, &amp;ident, params)</p>         </td>
         <td><p>To retrieve a Transfer Request and copy the Transfer parameters to the parameters list <em>xferParams</em>.</p>
<p>The value of:</p>
<ul>
<li><em>option</em> is XFER_LOCK</li>
<li><em>ident</em> is the Transfer Request identifier supplied by the user</li>
<li><em>params</em> is the parameters list built by the GikXferGet primitive</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>GikSetxxx(params, fieldIdent_1, value_1)</p>
<p>GikSetxxx(params, fieldIdent_i, value_i)</p>
<p>GikSetxxx(params, fieldIdent_n, value_n)</p>         </td>
         <td><p>To update the value of the fieldIdent field in the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferUpdate(session, params)</p>         </td>
         <td><p>To update the last Transfer Request retrieved by GikXferGet (or GikXferGetNext)</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams(params)</p>         </td>
         <td><p>To free the handle on the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

### Deleting Transfers from the Mailbox

Use the following primitives to delete Transfers from the Mailbox:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen(cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open a session</p>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams(GIK_TRANSFER, &amp;xferParams)</p>         </td>
         <td><p>To initialize the parameters list for use in:</p>
<ul>
<li>GikXferPut</li>
<li>GikXferGet</li>
<li>GikGetNext</li>
<li>GikXferUpdate</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams(GIK_SELECTION, &amp;selectParams)</p>         </td>
         <td><p>To initialize the parameters list for use in GikXferOpenSet</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferOpenSet(session, selectParams)</p>         </td>
         <td><p>To select a set of Transfer Requests</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferGetNext(session, options, xferParams)</p>         </td>
         <td><p>To read the Transfer Requests previously selected by GikXferOpenSet.</p>
<p>The value of <span style="font-style: italic;">options</span> is XFER_LOCK.</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferDelete(session)</p>         </td>
         <td><p>To delete the last Transfer Request retrieved by GikXferGet (or GikXferGetNext).</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferCloseSet(session)</p>         </td>
         <td><p>To close the set of Transfer Requests previously opened by GikXferOpenSet.</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams(xferParams)</p>         </td>
         <td><p>To free parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams(selectParams)</p>         </td>
         <td><p>To free parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

### Suspending Transfers

Use the following primitives to suspend Transfers:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen (cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open a session. The Transfer Request must be in one of the following states:</p>
<ul>
<li>XFER_TO_BEGIN</li>
<li>XFER_PROGRESSING</li>
<li>XFER_SERVICING</li>
<li>XFER_DELAYED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>GikXferModifState(session, &amp;ident, SUSPEND)</p>         </td>
         <td><p>To modify the state of the Transfer Request that you identify by the parameter <em>ident</em>.</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

<span id="messages"></span>

## Messages

### Submitting message requests via a buffer

Use the following primitives to submit message requests via a buffer:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen(cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open a session</p>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams(GIK_TRANSFER, &amp;params)</p>         </td>
         <td><p>To initialize a parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSetxxx(params, fieldIdent_1, value_1)</p>
<p>GikSetxxx(params, fieldIdent_i, value_i)</p>
<p>GikSetxxx(params, fieldIdent_n, value_n)</p>         </td>
         <td><p>To set the value of the fieldIdent field in the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSetBuff(params, GIK_T_MSG_BUF, ptr, length)</p>         </td>
         <td><p>GiKSetBuff is used to allocate buffer space. The parameter must be previously allocated and filled.</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferPut(session, params, &amp;ident)</p>         </td>
         <td><p>To retrieve the identifier of the Transfer to submit</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams(params)</p>         </td>
         <td><p>To free the parameters</p>         </td>
      </tr>
      <tr>
         <td><p>free(ptr)</p>         </td>
         <td><p>The parameter can be freed after a call to GikFreeParams</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

### Retrieving message requests via a buffer

Use the following primitives to retrieve message requests via a buffer:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GikSessionOpen (cs_profile_name, user, password, &amp;session)</p>         </td>
         <td><p>To open a session</p>         </td>
      </tr>
      <tr>
         <td><p>GikInitParams (GIK_TRANSFER, &amp;params)</p>         </td>
         <td><p>To initialize a parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSetInt (params, GIK_T_MSG_MAX, max)</p>         </td>
         <td><p>To set the maximum message size that you can retrieve, via the <em>max</em> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p>GikXferGet (session, option, &amp;ident, params)</p>         </td>
         <td><p>To retrieve the identifier of the Transfer Request to read</p>         </td>
      </tr>
      <tr>
         <td><p>GikGetxxx (params, fieldIdent_1, &amp;value_1)</p>
<p>GikGetxxx (params, fieldIdent_i, &amp;value_i)</p>
<p>GikGetxxx (params, fieldIdent_n, &amp;value_n)</p>
<p>GikGetBuffSize (params, GIK_T_MSG_BUF, size); (allocation of ptr)</p>
<p>GikGetBuff (params, GIK_T_MSG_BUF, ptr, length)</p>         </td>
         <td><p>To retrieve Transfer Request parameters and buffer size.</p>
<p>The length (size allocated in ptr) must be less than <em>max</em> and greater than (or equal to) <em>size</em>. It is often equal to size.</p>         </td>
      </tr>
      <tr>
         <td><p>GikFreeParams (params)</p>         </td>
         <td><p>To free the parameters list</p>         </td>
      </tr>
      <tr>
         <td><p>GikSessionClose(session)</p>         </td>
         <td><p>To close the session</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About C API](../)

[C API primitives](../c_api_primitives)

[C API Transfer and Selection parameters](../c_api_trans_and_sel_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
