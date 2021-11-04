{
    "title": "Pre-built test cases",
    "linkTitle": "Testing TARGET2 configurations",
    "weight": "280"
}The Gateway TARGET2 package includes a set of pre-built test case files that you can use to test TARGET2 exchanges in either Real or Simulation mode.

You can launch test cases either from the GUI or via line commands.

The following test cases are provided to enable you to analyze your configuration:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Test case number         </th>
<th class="HeadD-Column1-Header1">Case result         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>0000</p>         </td>
         <td><p>Returns a technical final response, not compressed</p>         </td>
      </tr>
      <tr>
         <td><p>0001</p>         </td>
         <td><p>Returns a technical final response, compressed</p>         </td>
      </tr>
      <tr>
         <td><p>1001</p>         </td>
         <td><p>Returns the response "Execution timeout limit exceeded".</p>         </td>
      </tr>
      <tr>
         <td><p>1002</p>         </td>
         <td><p>Returns the response "Data not yet available".</p>         </td>
      </tr>
      <tr>
         <td><p>1003</p>         </td>
         <td><p>Returns the response "Message size limit exceeded". [Uncompressed file put at disposal.]</p>         </td>
      </tr>
      <tr>
         <td><p>1003b</p>         </td>
         <td><p>Returns the response "Message size limit exceeded". [Compressed file put at disposal.]</p>         </td>
      </tr>
      <tr>
         <td><p>1111</p>         </td>
         <td><p>Returns a response with an unhandled SSP error code.</p>         </td>
      </tr>
      <tr>
         <td><p>7777</p>         </td>
         <td><p>Simulation will send a functional response, not compressed</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
