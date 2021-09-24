{
    "title": "nrecfm",
    "linkTitle": "nrecfm",
    "weight": "2330"
}### <span id="nrecfm"></span>nrecfm

#### CFTSEND, SEND

**\[NRECFM = {<u>FRECFM value</u> | F | U
| V}\]     ODETTE,
PeSIT, OS**

File record format defined in protocol terms:

-   F: fixed
-   V: variable
-   U: undefined

<table cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr>
         <td width="26%">
            <p>PeSIT D EXTERN profile<br/>PeSIT ANY profile<br/>PeSIT E</p>
         </td>
         <td width="74%">
            <p>In PeSIT protocol with the  EXTERN profile, the 
 value NFRECFM = U is not known in protocol terms and is changed by the  <span>Transfer CFT</span>
 to NFRECFM = V. This value (U) is sent with no modification in PeSIT 
 D CFT profile or in PeSIT E from  <span>Transfer CFT</span> to  <span>Transfer CFT</span>.</p>
         </td>
      </tr>
      <tr>
         <td width="26%">
            <p><b>ODETTE</b>
</p>
         </td>
         <td width="74%">
            <p>For the ODETTE protocol, refer to the  <span>Transfer CFT</span> <i>Protocol 
 section</i> for the use  of this parameter.</p>
         </td>
      </tr>
      <tr>
         <td width="26%">
            <p><b>PeSIT SIT profile</b>
</p>
         </td>
         <td width="74%">
            <p>The NRECFM = U value is only recognized between two Transfer 
 CFTs.</p>
         </td>
      </tr>
</table>

[Return to Command index](../../)
