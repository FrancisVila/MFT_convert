{
    "title": "C API primitives",
    "linkTitle": "C API",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

This topic introduces the C API primitives supplied with Gateway.

<span id="Interface_header"></span>

## Interface header

The <span class="code" style="font-weight: bold;">gikapic.h</span> header file contains the API primitive prototypes. This file is located in <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/inc</span>.

<span id="list_primitives"></span>

## List of API primitives

The following table lists the available API primitives.

Follow the links for details about using these primitives.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">API primitive         </th>
<th class="HeadD-Column1-Header1">Usage         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="c_api_primitives#GikSetTraceLevel">GikSetTraceLevel</a></p>         </td>
         <td><p>Use this function to set the desired trace level.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikSessionOpen">GikSessionOpen</a></p>
<p><a href="c_api_primitives#GikSessionOpenFromNotif">GikSessionOpenFromNotif</a></p>         </td>
         <td><p>Use the GikSessionOpen function to open the communication session. This function provides access security features, to use the interface in client/server mode. You must call the function before you use any other API primitive.</p>
<p>Use the GikSessionOpenFromNotif function to open the session from external exits.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikSessionClose">GikSessionClose</a></p>
<p><a href="c_api_primitives#GikSessionCloseFromNotif">GikSessionCloseFromNotif</a></p>         </td>
         <td><p>Use these functions to close the communication session and releases all resources. The last Transfer Request locked is automatically unlocked.</p>
<p>Use the GikSessionCloseFromNotif function to close a session opened with GikSessionOpenFromNotif.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikErrMsg">GikErrMsg</a></p>         </td>
         <td><p>When an error occurs, API primitives return <span style="font-weight: bold;">1</span> and set an error code in the global variable ErrCod. This function returns the error message text that corresponds to the value of ErrCod.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikGetErrCod">GikGetErrCod</a></p>         </td>
         <td><p>When an error occurs, API primitives return <span style="font-weight: bold;">1</span> and set an error code in the global variable ErrCod. This function returns the value of ErrCod.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikInitParams">GikInitParams</a></p>         </td>
         <td><p>Use this function to retrieve a handle on an empty parameter list.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikFreeParams">GikFreeParams</a></p>         </td>
         <td><p>Use this function to free a handle on a parameter list.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikSetxxx">GikSetxxx</a></p>         </td>
         <td><p>Use the GikSetxxx series of functions to set the value of a field in the parameters list.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikGetxxx">GikGetxxx</a></p>         </td>
         <td><p>Use the GikGetxxx series of functions to retrieve the value of a field from the parameter list.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferPut">GikXferPut</a></p>         </td>
         <td><p>Use this function to submit a Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferGet">GikXferGet</a></p>         </td>
         <td><p>Use this function to read the Transfer Request that you specify by its identifier <span class="code">ident</span>, and copy the Transfer parameters in the parameter list <span class="code">xferParams</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferUpdate">GikXferUpdate</a></p>         </td>
         <td><p>Use this function to modify a Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferDelete">GikXferDelete</a></p>         </td>
         <td><p>Use this function to delete a Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferUnlock">GikXferUnlock</a></p>         </td>
         <td><p>Use this function to unlock a Transfer Request that was previously locked during a read operation.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferOpenSet">GikXferOpenSet</a></p>         </td>
         <td><p>Use this function to select a set of Transfer Requests, depending on the criteria specified in the parameter list <span class="code">selectParams</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferGetNext">GikXferGetNext</a></p>         </td>
         <td><p>Use this function to read the Transfer Requests previously selected by the GikXferOpenSet primitive. It copies the Transfer parameters to the parameters list <span class="code">xferParams</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferCloseSet">GikXferCloseSet</a></p>         </td>
         <td><p>Use this function to close the set of Transfer Requests previously selected using the GikXferOpenSet primitive.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="c_api_primitives#GikXferModifState">GikXferModifState</a></p>         </td>
         <td><p>Use this function to modify the state of the Transfer identified by the <span class="code">ident</span> parameter.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[C API primitives](c_api_primitives)

[C API usage examples](c_api_usage_examples)

[C API Transfer and Selection parameters](c_api_trans_and_sel_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
