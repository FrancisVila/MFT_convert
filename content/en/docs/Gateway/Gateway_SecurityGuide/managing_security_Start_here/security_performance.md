{
    "title": "The performance cost of encryption",
    "linkTitle": "Performance cost of encryption",
    "weight": "150"
}Performance impact on various mailbox operation when data files are encrypted, N=1000 transfers:

<table>
   <tbody>
      <tr>
         <td>Operation         </td>
         <td>Average times         </td>
         <td>Performance decrease         </td>
      </tr>
      <tr>
         <td>Create one item         </td>
         <td>2.33ms/2.39ms         </td>
         <td>2.74%         </td>
      </tr>
      <tr>
         <td>Update one item         </td>
         <td>1.85ms/1.97ms         </td>
         <td>6.15%         </td>
      </tr>
      <tr>
         <td>Select one item with criteria         </td>
         <td>2.125ms/2.144ms         </td>
         <td>0.91%         </td>
      </tr>
      <tr>
         <td>Select one item         </td>
         <td>945ms/1.968ms         </td>
         <td>1.19%         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
