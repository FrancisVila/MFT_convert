{
    "title": "orecfm",
    "linkTitle": "orecfm",
    "weight": "2500"
}### <span id="orecfm"></span>orecfm

#### COPYILE

\[ORECFM = {<u>IRECFM value</u> | F |
V | U}\]

Output record format:

-   F:
    fixed
-   V:
    variable
-   U:
    undefined

The possible values for each system are indicated in the corresponding
specific Operations Guide. If the output file is compressed (OCOMP
not 0), the value of the ORECFM parameter is forced
to V.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>OS</th>
         <th>Details</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="middle">
         <td colspan="1" rowspan="1" width="26%">
            <p>UNIX</p>
         </td>
         <td colspan="1" rowspan="1" width="74%">
            <p>The value "U" is kept for compatibility with previous 
 versions. It has the same meaning as ORECFM=V.</p>
         </td>
      </tr>
   </tbody>
</table>

 

[Return to Command index](../../)
