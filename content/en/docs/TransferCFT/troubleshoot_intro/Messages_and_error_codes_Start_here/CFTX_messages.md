{
    "title": "CFTX messages",
    "linkTitle": "CFTX messages",
    "weight": "410"
}This topic lists the CFTWxx and CFTXxx messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td width="80%">
            <p><a name="CFTX01W"></a>CFTX01W Action &amp;action on object &amp;object not authorized for user &amp;user : ID CFTAPPL=&amp;id CFTX01W Action &amp;action on object &amp;object not authorized for user &amp;user : ID CFTAPPL=&amp;id</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The authorization system does not allow the &amp;user user to 
 set the &amp;idf IDF, as indicated in the preceding message (either CFTC10I or CFTC11I). You should check with your security administrator to determine 
 your access rights.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td width="80%">
            <p><a name="CFTX02W"></a>CFTX02W owner user is &amp;user, owner group is &amp;group </p>
            <p>CFTX02W owner user is &amp;user, owner group is &amp;group</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The user and group names used are displayed. This message is 
 displayed after the CFTX01W message.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td width="80%">
            <p><a name="CFTX03W"></a>CFTX03W Action &amp;action on object &amp;object not 
 authorized for user &amp;user </p>
            <p>CFTX03W+Action &amp;action on object &amp;object not authorized for user &amp;user</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The security system does not allow &amp;user to perform the 
 specified action (contact your security administrator to set the required 
 privileges).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td width="80%">
            <p><a name="CFTX04W"></a>CFTX04W 
 With value &amp;value </p>
            <p>CFTX04W+with value &amp;value</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="20%">
            <p>Warning message.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td width="80%">
            <p><a name="CFTX05W"></a>CFTX05W Action &amp;action on object &amp;object not 
 authorized for user &amp;user: FNAME=&amp;fname </p>
            <p>CFTX05W Action &amp;action on object &amp;object not authorized for user &amp;user : FNAME=&amp;fname</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The security system does not allow &amp;user to specify &amp;fname 
 as the FNAME value (contact your security administrator to set the required 
 privileges).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td rowspan="3" width="20%">
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
         <td width="80%">
            <p><a name="CFTX10I"></a>CFTX10I Warning : security file commands were modified</p>
            <p>CFTX10I Warning : security file commands were modified</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="80%">
            <p><a name="CFTX11I"></a>CFTX11I+ without a generation was done</p>
            <p>CFTX11I+ without a generation was done</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="80%">
            <p><a name="CFTX12I"></a>CFTX12I+ Some queer comportements will happenned.</p>
            <p>CFTX12I+ Some queer comportements will happenned.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="20%">
            <p>Explanation</p>
         </td>
         <td colspan="1" rowspan="1" width="80%">
            <p>Modifications have been made to the authorization system, 
 but the system has not been regenerated. </p>
            <p>Abnormal behavior may arise when <span>Transfer CFT</span> is executed.</p>
         </td>
      </tr>
</table>
