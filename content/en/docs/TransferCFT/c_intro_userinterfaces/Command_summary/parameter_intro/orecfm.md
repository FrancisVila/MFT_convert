{
    "title": "orecfm",
    "linkTitle": "orecfm",
    "weight": "2470"
}<span id="orecfm"></span>

### <span class="mc-variable System.Title variable">orecfm</span>

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

<table>
   <th>
      <tr>
<th>OS         </th>
<th>Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>UNIX</p>         </td>
         <td><p>The value "U" is kept for compatibility with previous
versions. It has the same meaning as ORECFM=V.</p>         </td>
      </tr>
   </tbody>
</table>

 

[Return to Command index](../../)
