{
    "title": "nrecfm",
    "linkTitle": "nrecfm",
    "weight": "2300"
}<span id="nrecfm"></span>

### nrecfm

#### CFTSEND, SEND

**\[NRECFM = {<u>FRECFM value</u> | F | U
| V}\]     ODETTE,
PeSIT, OS**

File record format defined in protocol terms:

-   <span style="font-weight: bold;">F</span>: fixed
-   <span style="font-weight: bold;">V</span>: variable
-   <span style="font-weight: bold;">U</span>: undefined

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>PeSIT D EXTERN profile<br />
PeSIT ANY profile<br />
PeSIT E</p>         </td>
         <td><p>In PeSIT protocol with the EXTERN profile, the
value NFRECFM = U is not known in protocol terms and is changed by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
to NFRECFM = V. This value (U) is sent with no modification in PeSIT
D CFT profile or in PeSIT E from <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>ODETTE</strong></p>         </td>
         <td><p>For the ODETTE protocol, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <em>Protocol
section</em> for the use of this parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>PeSIT SIT profile</strong></p>         </td>
         <td><p>The NRECFM = U value is only recognized between two Transfer
CFTs.</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
