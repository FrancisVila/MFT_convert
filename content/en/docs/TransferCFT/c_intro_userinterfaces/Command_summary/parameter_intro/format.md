{
    "title": "format",
    "linkTitle": "format",
    "weight": "1260"
}<span id="format"></span>

### format

<span id="format_CFTLOG"></span>

#### CFTLOG

\[FORMAT = <span style="text-decoration: underline;">V23</span>
| V24 \]

Optional parameter. Indicates the format for log messages.

-   <span style="font-weight: bold;">V23 </span>(Default value): The Identifier’s
    length is truncated to 8 characters.
-   <span style="font-weight: bold;">V24</span>: The complete Identifier is displayed.
    The length of the Identifier can be up to 32 characters. Some messages
    related to a transfer includes the IDTU (Local transfer counter identifier)
    value.

<span id="format_CFTACCNT"></span>

#### CFTACCNT

\[FORMAT = <span style="text-decoration: underline;">V23</span>
| V24 \]

Optional parameter. The FORMAT parameter indicates whether the former
record structure should be used (V23 values for compatibility reasons)
or if the new structure is to be applied (V24 values).

-   <span style="font-weight: bold;">V23 </span>(Default value)
-   V24

<span id="format_CFTEXIT"></span>

#### CFTEXIT

\[ FORMAT = { string } \]

Indicates the file format of the communication area for an exit list. The possible values are 1, 2 C, T, J or X, where <span class="code">1 </span>is the default.

Example


    PARM LRECL = nnnn, FORMAT=X
    SEND STATE = CDHKTX 
    RECV STATE = CDHKTX

##### Format 1

Displays using the same format as in <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> 3.5 and lower, though phase and phasestep no longer display.

##### Format 2

<table>
   <th>
      <tr>
<th><p>Type</p>         </th>
<th><p>V24 length</p>         </th>
<th><p>V23 length</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>1 </p>         </td>
         <td><p>1 </p>         </td>
         <td><p>'L': start of record marker </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>1 </p>         </td>
         <td><p>1 </p>         </td>
         <td><p>SEND/RECV flag </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>1 </p>         </td>
         <td><p>1 </p>         </td>
         <td><p>STATE </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PHASE</p>         </td>
      </tr>
      <tr>
         <td><p>CHAR</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PHASESTEP</p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>64</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>Send partner (PART)</p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>64</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>Receive partner (PART)</p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>32</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>IDF file identifier </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>8</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>IDT transfer identifier </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>10</p>         </td>
         <td><p>10 </p>         </td>
         <td><p>Number of records </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>512</p>         </td>
         <td><p>64 </p>         </td>
         <td><p>Filename </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>3</p>         </td>
         <td><p>3 </p>         </td>
         <td><p>Transfer priority </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>8</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>Date of submission to catalog</p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>8</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>Time submitted to catalog, or time of last modification </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>512</p>         </td>
         <td><p>80 </p>         </td>
         <td><p>User parameter (PARM)</p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>32</p>         </td>
         <td><p>15 </p>         </td>
         <td><p>Send USER </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>32</p>         </td>
         <td><p>15 </p>         </td>
         <td><p>Receive USER </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>160</p>         </td>
         <td><p>160 </p>         </td>
         <td><p>Local user parameter </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>3</p>         </td>
         <td><p>3 </p>         </td>
         <td><p>Diagi </p>         </td>
      </tr>
      <tr>
         <td><p>CHAR </p>         </td>
         <td><p>64</p>         </td>
         <td><p>8 </p>         </td>
         <td><p>Diagp </p>         </td>
      </tr>
   </tbody>
</table>

##### Format C: CSV - Comma Separated Value

Each field is separated by a comma.

For example: <span class="code">S,X,X,X,MARTIN,PARIS,BIN,L1111482,2,,128,20191211,11481147,,,,,0,CP NONE</span>

##### Format T: TSV - Tab Separated Value

Each field is separated by a tab.

##### Format J: JSON



    {"TRANSFERS":[{"DIRECT":"S","STATE":"X","PHASE":"X","PHASESTEP":"X","SPART":"MARTIN","RPART":"PARIS","IDF":"ID_EXITL","IDT":"L1111482","NBR":"2","FNAME":"","PRI":"128","DATEK":"20191211","TIMEK":"11481147","PARM":"","SUSER":"","RUSER":"","COMMENT":"","DIAGI":"0","DIAGP":"CP NONE"}                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
    ,{"DIRECT":"R","STATE":"X","PHASE":"X","PHASESTEP":"X","SPART":"PARIS","RPART":"MARTIN","IDF":"BIN","IDT":"L1111475","NBR":"2","FNAME":"pub\\L1111475_A000002Q.RCV","PRI":"128","DATEK":"20191211","TIMEK":"11475343","PARM":"My \"param\" with quote","SUSER":"","RUSER":"","COMMENT":"","DIAGI":"0","DIAGP":"CP NONE"}                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
    ], "TOTAL":"2"}            

##### Format X: XML


    <?xml version="1.0" encoding="UTF-8"?><CAT><TRANSFER DIRECT="S" STATE="X" PHASE="X" PHASESTEP="X" SPART="MARTIN" RPART="PARIS" IDF="ID_EXITL" IDT="L1111423" NBR="2" FNAME="" PRI="128" DATEK="20191211" TIMEK="11422580" PARM="" SUSER="" RUSER="" COMMENT="" DIAGI="0" DIAGP="CP NONE"/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  <TRANSFER DIRECT="R" STATE="X" PHASE="X" PHASESTEP="X" SPART="PARIS" RPART="MARTIN" IDF="BIN" IDT="L1111415" NBR="2" FNAME="pub\L1111415_A000002K.RCV" PRI="128" DATEK="20191211" TIMEK="11415981" PARM="My  &quot;param&quot; with quote" SUSER="" RUSER="" COMMENT="" DIAGI="0" DIAGP="CP NONE"/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
    <TOTAL>2</TOTAL></CAT>      

                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

[Return to Command index](../../)
