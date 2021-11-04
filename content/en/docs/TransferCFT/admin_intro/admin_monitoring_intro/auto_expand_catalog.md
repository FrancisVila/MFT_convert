{
    "title": "Automatic  catalog expansion",
    "linkTitle": "Automatic  catalog expansion",
    "weight": "300"
}The<span class="italic_in_para"> auto-expand </span>catalog option lets you enlarge the catalog by a preset percentage when an alert is sent that the catalog is reaching its threshold. Additionally you can indicate a script to execute if this expanded limit is exceeded.

## Overview

Once the catalog exceeds the minimum alert level, it can be expanded to the amount defined in the auto-expand option. For example, if you set the auto-expand to 100%, then the catalog doubles. If you define it as 50%, the catalog resizes to 1.5 times the original number of records. After the auto-expand limit is reached, a predefined script can be executed.

If you defined a timer for catalog alerts, TLVCLEAR, once the usage surpasses the allotted time value one of the following occurs:

-   The catalog is expanded and a message sent to the log, but no script is executed
-   The catalog is expanded, a message is sent to the log, and the TLVCEXEC script executes.

## Steps

To enable the auto-expand option, with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> running:

1.  Set the uconf values for:
    -   cft.cftcat.auto\_expand\_percent
    -   cft.cftcat.auto\_expand\_max\_size
2.  To activate the new values, run the command: <span class="code">CFTUTIL reconfig type = uconf</span>
    -   If <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is stopped when setting uconf values, you do not need to execute the <span class="code">reconfig </span>command.

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.cftcat.auto_expand_percent         </td>
         <td>0         </td>
         <td><p>This value indicates the factor increase, as a percentage, that the catalog will automatically expand.</p>
<p>The value 0 disables the automatic expansion feature.</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Tip  </strong></span>         </td>
         <td>We recommend that you set this to a relatively high value, at least 50. When repeatedly expanded, the catalog's internal structure may become fragmented and, consequently, catalog access less efficient.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td>cft.cftcat.auto_expand_max_size         </td>
         <td>1M         </td>
         <td><p>The maximum number of records for the automatic catalog expansion option.</p>         </td>
      </tr>
   </tbody>
</table>

Related parameters:

-   TLVCLEAR: Level below which the alert stops.
-   TLVCEXEC: Batch to execute when the alert ends.
-   TLVWRATE: The minimum amount of time, in seconds, to wait before resending an alert.
-   TLVWEXEC: Batch to execute when CFTCAT/TLVWARN is reached.
-   TLVWARN: Catalog usage limit before issuing an alert. When this limit is reached, the CFTCAT/TLVWEXEC is executed.

Example

The example is based on the following settings:

-   catalog size = 100
-   cft.cftcat.auto\_expand\_percent = 20
-   cft.cftcat.auto\_expand\_max\_size = 140

When you reach the TLVWRATE (level=80%), the following messages are sent to the log:


     12/10/17 17:53:30  CFTC29W Catalog Alert fill threshold reached: level=80% ID=CAT0
     12/10/17 17:53:30  CFTC13I Catalog resize (100 --> 120) done
     12/10/17 17:54:16  CFTT17I _ STATE=HOLD <IDTU=A0000029 PART=PARIS IDF=TXT IDT=J1718064> 
     12/10/17 17:54:16  CFTR12I SEND Treated for USER adaumer  <IDTU=A0000029 PART=PARIS IDF=TXT>
     12/10/17 17:54:16  CFTS20I Communication file row number deleted: 00000252    
     12/10/17 17:54:16  CFTC30W Catalog Alert cleared : level=67% ID=CAT0

The new fill rate is now 80/120 = 66.66%, well below TLVCLEAR, so the alerts stops at next update (the send command in this example).

The message <span class="span_1">CFTC30W Catalog Alert cleared : level=67% ID=CAT0</span> indicates that the catalog is sufficient. If it were not, the catalog would be extended again at next alert in TLVWRATE seconds.

The catalog continues to fill until it reaches 80%. Expanding 20% more would resize the catalog to 144 records, which exceeds the limit (140), and the log displays:


     12/10/17 18:06:57  CFTC29W Catalog Alert fill threshold reached: level=80% ID=CAT0
     12/10/17 18:06:57  CFTC13I Catalog resize (120 --> 144) too much
     12/10/17 18:06:57  CFTC13I Catalog resize (120 --> 140) done
     12/10/17 18:06:57  CFTT17I _ STATE=HOLD <IDTU=A000002P PART=PARIS IDF=TXT IDT=J1718092> 
     12/10/17 18:06:57  CFTR12I SEND Treated for USER adaumer  <IDTU=A000002P PART=PARIS IDF=TXT>
     12/10/17 18:06:57  CFTS20I Communication file row number deleted: 00000269                                
     12/10/17 18:06:57  CFTC30W Catalog Alert cleared : level=69% ID=CAT0

The next time the catalog limit is reached, it can no longer expand and the log displays:


     12/10/19 15:53:21  CFTC29W Catalog Alert fill threshold reached: level=80% ID=CAT0
     12/10/19 15:53:21  CFTC13E Catalog resize (140 --> 210) reached max before expansion
     12/10/19 15:53:21  CFTC08I Purge Treated : no record found to delete.