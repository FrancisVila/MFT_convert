{
    "title": "LISTCAT/DISPLAY - Statistical variables",
    "linkTitle": "LISTCAT - Statistical variables",
    "weight": "330"
}Use the following variables after performing a LISTCAT or DISPLAY command to show the selected statistical information. For example, LISTCAT\_FREE displays the percentage of free records. Additionally, you can use a combination of these variables.

-   \_LISTCAT\_SELECTED: displays the selected record(s) from the original LISTCAT command
-   \_LISTCAT\_CAT: displays the total number of records
-   \_LISTCAT\_FREE: displays the number of available records
-   \_LISTCAT\_FREE\_P: displays the number of available records as a percentage of the total number of records

**Example**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL</p>
            <p>...</p>
            <p>LISTCAT</p>
            <p>PRINT MSG='NbSelected = %_LISTCAT_SELECTED%'</p>
            <p>PRINT MSG='NbTotal = %_LISTCAT_CAT%'</p>
            <p>PRINT MSG='NbFree = %_LISTCAT_FREE%'</p>
            <p>PRINT MSG='Percent free= %_LISTCAT_FREE_P%'</p>
            <p> </p>
            <p> </p>
            <p><strong>Results</strong></p>
            <p>------------------------------------</p>
            <p>BCLPM SFT XX TGTG E0216242 1 1 0 CP 88%</p>
            <p>BCLPRM RFT XX TGTG E0216242 1 1 0 CP 88%</p>
            <p>2 record(s) selected</p>
            <p>1000 record(s) in Catalog file</p>
            <p>998 record(s) free (99%)</p>
            <p>CFTU00I LISTCAT _ Correct ()</p>
            <p>NbSelected = 2</p>
            <p>CFTU00I PRINT _ Correct (MSG='NbSelected = 2')</p>
            <p>NbTotal = 1000</p>
            <p>CFTU00I PRINT _ Correct (MSG='NbTotal = 1000')</p>
            <p>NbFree = 998</p>
            <p>CFTU00I PRINT _ Correct (MSG='NbFree = 998')</p>
            <p>Purcent free= 99</p>
            <p>CFTU00I PRINT _ Correct (MSG='Percent free= 99')</p>         </td>
      </tr>
   </tbody>
</table>
