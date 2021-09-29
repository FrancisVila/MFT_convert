{
    "title": "format",
    "linkTitle": "format",
    "weight": "1290"
}### <span id="format"></span>format

#### <span id="format_CFTLOG"></span>CFTLOG

\[FORMAT = V23
| V24 \]

Optional parameter. Indicates the format for log messages.

-   V23 (Default value): The Identifier’s
    length is truncated to 8 characters.
-   V24: The complete Identifier is displayed.
    The length of the Identifier can be up to 32 characters. Some messages
    related to a transfer includes the IDTU (Local transfer counter identifier)
    value.

#### <span id="format_CFTACCNT"></span>CFTACCNT

\[FORMAT = V23
| V24 \]

Optional parameter. The FORMAT parameter indicates whether the former
record structure should be used (V23 values for compatibility reasons)
or if the new structure is to be applied (V24 values).

-   V23 (Default value)
-   V24

#### <span id="format_CFTEXIT"></span>CFTEXIT

\[ FORMAT = { string } \]

Indicates the file format of the communication area for an exit list. The possible values are 1, 2 C, T, J or X, where 1 is the default.

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PARM LRECL = nnnn, FORMAT=X<br />
SEND STATE = CDHKTX<br />
RECV STATE = CDHKTX</td>
</tr>
</tbody>
</table>

##### Format 1

Displays using the same format as in Transfer CFT 3.5 and lower, though phase and phasestep no longer display.

##### Format 2

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Type</p></th>
<th><p>V24 length</p></th>
<th><p>V23 length</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>1 </p></td>
<td><p>1 </p></td>
<td><p>'L': start of record marker </p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>1 </p></td>
<td><p>1 </p></td>
<td><p>SEND/RECV flag </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>1 </p></td>
<td><p>1 </p></td>
<td><p>STATE </p></td>
</tr>
<tr class="even">
<td><p>CHAR</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>PHASE</p></td>
</tr>
<tr class="odd">
<td><p>CHAR</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>PHASESTEP</p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
<td><p>Send partner (PART)</p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
<td><p>Receive partner (PART)</p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>32</p></td>
<td><p>8 </p></td>
<td><p>IDF file identifier </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>8</p></td>
<td><p>8 </p></td>
<td><p>IDT transfer identifier </p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>10</p></td>
<td><p>10 </p></td>
<td><p>Number of records </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>512</p></td>
<td><p>64 </p></td>
<td><p>Filename </p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>3</p></td>
<td><p>3 </p></td>
<td><p>Transfer priority </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>8</p></td>
<td><p>8 </p></td>
<td><p>Date of submission to catalog</p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>8</p></td>
<td><p>8 </p></td>
<td><p>Time submitted to catalog, or time of last modification </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>512</p></td>
<td><p>80 </p></td>
<td><p>User parameter (PARM)</p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>32</p></td>
<td><p>15 </p></td>
<td><p>Send USER </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>32</p></td>
<td><p>15 </p></td>
<td><p>Receive USER </p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>160</p></td>
<td><p>160 </p></td>
<td><p>Local user parameter </p></td>
</tr>
<tr class="odd">
<td><p>CHAR </p></td>
<td><p>3</p></td>
<td><p>3 </p></td>
<td><p>Diagi </p></td>
</tr>
<tr class="even">
<td><p>CHAR </p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
<td><p>Diagp </p></td>
</tr>
</tbody>
</table>

##### Format C: CSV - Comma Separated Value

Each field is separated by a comma.

For example: S,X,X,X,MARTIN,PARIS,BIN,L1111482,2,,128,20191211,11481147,,,,,0,CP NONE

##### Format T: TSV - Tab Separated Value

Each field is separated by a tab.

##### Format J: JSON

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>{<code>"TRANSFERS"</code>:[{<code>"DIRECT"</code>:<code>"S"</code>,<code>"STATE"</code>:<code>"X"</code>,<code>"PHASE"</code>:<code>"X"</code>,<code>"PHASESTEP"</code>:<code>"X"</code>,<code>"SPART"</code>:<code>"MARTIN"</code>,<code>"RPART"</code>:<code>"PARIS"</code>,<code>"IDF"</code>:<code>"ID_EXITL"</code>,<code>"IDT"</code>:<code>"L1111482"</code>,<code>"NBR"</code>:<code>"2"</code>,<code>"FNAME"</code>:<code>"","</code>PRI<code>":"</code>128<code>","</code>DATEK<code>":"</code>20191211<code>","</code>TIMEK<code>":"</code>11481147<code>","</code>PARM<code>":"","</code>SUSER<code>":"","</code>RUSER<code>":"","</code>COMMENT<code>":"","</code>DIAGI<code>":"</code>0<code>","</code>DIAGP<code>":"</code>CP NONE"}                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        </p>
<p>,{<code>"DIRECT"</code>:<code>"R"</code>,<code>"STATE"</code>:<code>"X"</code>,<code>"PHASE"</code>:<code>"X"</code>,<code>"PHASESTEP"</code>:<code>"X"</code>,<code>"SPART"</code>:<code>"PARIS"</code>,<code>"RPART"</code>:<code>"MARTIN"</code>,<code>"IDF"</code>:<code>"BIN"</code>,<code>"IDT"</code>:<code>"L1111475"</code>,<code>"NBR"</code>:<code>"2"</code>,<code>"FNAME"</code>:<code>"pub\\L1111475_A000002Q.RCV"</code>,<code>"PRI"</code>:<code>"128"</code>,<code>"DATEK"</code>:<code>"20191211"</code>,<code>"TIMEK"</code>:<code>"11475343"</code>,<code>"PARM"</code>:<code>"My \"</code>param\<code>" with quote"</code>,<code>"SUSER"</code>:<code>"","</code>RUSER<code>":"","</code>COMMENT<code>":"","</code>DIAGI<code>":"</code>0<code>","</code>DIAGP<code>":"</code>CP NONE"}                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         </p>
<p>], <code>"TOTAL"</code>:<code>"2"</code>}            </p></td>
</tr>
</tbody>
</table>

##### Format X: XML

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;&lt;CAT&gt;&lt;TRANSFER DIRECT="S" STATE="X" PHASE="X" PHASESTEP="X" SPART="MARTIN" RPART="PARIS" IDF="ID_EXITL" IDT="L1111423" NBR="2" FNAME="" PRI="128" DATEK="20191211" TIMEK="11422580" PARM="" SUSER="" RUSER="" COMMENT="" DIAGI="0" DIAGP="CP NONE"/&gt;</code>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 
<p><code>&lt;TRANSFER DIRECT="R" STATE="X" PHASE="X" PHASESTEP="X" SPART="PARIS" RPART="MARTIN" IDF="BIN" IDT="L1111415" NBR="2" FNAME="pub\L1111415_A000002K.RCV" PRI="128" DATEK="20191211" TIMEK="11415981" PARM="My  &amp;quot;param&amp;quot; with quote" SUSER="" RUSER="" COMMENT="" DIAGI="0" DIAGP="CP NONE"/&gt;</code>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </p>
<p><code>&lt;TOTAL&gt;</code>2<code>&lt;/TOTAL&gt;&lt;/CAT&gt;</code>      </p></td>
</tr>
</tbody>
</table>

                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

[Return to Command index](../../)
