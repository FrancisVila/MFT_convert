{
    "title": "CFTXLATE - Conversion tables",
    "linkTitle": "CFTXLATE - Conversion tables",
    "weight": "480"
}# <span id="kanchor54"></span><span id="Title"></span>CFTXLATE - Conversion tables

This topic describes how to define a translation table to be used during
a transfer. There are two ways to generate a translation table, either using the FNAME parameter or the TABLE parameter as described below.

Related
topics

-   Command syntax
    [CFTXLATE](../../../command_summary)
-   Object concepts
    [Conversion
    tables](../../../../concepts/cft_configuration_concepts_start_here/translation_table_concepts)

Use this object to define translation tables between 2
alphabets for:

-   Transfer
    direction
-   File
    data code type (FCODE: ASCII or EBCDIC)
-   Data
    network code type (NCODE: ASCII or EBCDIC)

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a> </p>
         </td>
         <td>
            <p>Transfer direction for which the table applies:</p>
            <ul>
               <li>SEND: 
 translation table for send transfers               </li>
               <li>RECV: 
 translation table for receive transfers               </li>
               <li>BOTH: 
 translation table which can be used for send transfers and receive transfers               </li>
            </ul>
            <p>If the value of the parameter is BOTH, the data read in 
 the file allows a translation table for send transfers (SEND) to be created. 
 The translation table for receive transfers (RECV) is deduced automatically.</p>
            <p>To provide for bijection (i.e. any character of the source 
 alphabet translated into the target alphabet, and then re-translated from 
 the target alphabet into the source alphabet, takes up its initial value 
 again), the table has to contain 256 different values. It is not essential 
 to strictly comply with this principle for transfer applications using 
 reduced alphabets.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/fcode">FCODE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Data code of the file sent.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/fname">FNAME</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the file containing the description of the translation 
 table.</p>
            <p>This file must have a sequential organization. Examples 
 of such files are given with the various products (refer to the Operations 
 Guide specific to each system).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Translation table identifier.</p>
            <p>Several CFTXLATE commands may have the same identifier, 
 if the values of DIRECT, FCODE or NCODE are different.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/ncode">NCODE</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Code of data sent over the network.</p>
         </td>
      </tr>
      <tr>
         <td><a href="table.htm">TABLE</a>
         </td>
         <td> A digital representation of the table as a hexadecimal string.          </td>
      </tr>
   </tbody>
</table>

**Example using FNAME**

In this example, the Transfer CFT internal translation tables (identifier
DEFAUT) are replaced by the user tables, which can be used in both transfer
directions.

For send transfers, the Transfer CFT translates
from ASCII into EBCDIC and for receive transfers, from EBCDIC into ASCII.
The ASCII to EBCDIC table is defined in the file ATOE and the EBCDIC to
ASCII table is deduced automatically.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTXLATE</p>
            <p>ID = DEFAUT,</p>
            <p>DIRECT = BOTH,</p>
            <p>FCODE = ASCII,      Dft: 
 OS</p>
            <p>FNAME = ATOE,</p>
            <p>NCODE = EBCDIC</p>
            <p> </p>
            <p>CFTPARM </p>
            <p>DEFAULT = DEFAUT,</p>
            <p>DIRECT = BOTH,</p>
            <p>FCODE = ASCII,      Dft: 
 OS</p>
            <p>FNAME = ATOE,</p>
            <p>NCODE = EBCDIC</p>
         </td>
      </tr>
   </tbody>
</table>

Example of generating a translation table using the TABLE parameter

You can use the following `CFTXLATE `command with the TABLE parameter, instead of FNAME, to generate an ASCII CP437 to EBCDIC CP1047 translation table.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTXLATE ID=CP437TOCP1047,FCODE=ASCII,NCODE=EBCDIC,DIRECT=BOTH,TABLE=00010203372D2E2F1605250B0C0D0E0F-</p>
            <p>10111213B6B5322618191C27071D1E1F-</p>
            <p>405A7F7B5B6C507D4D5D5C4E6B604B61-</p>
            <p>F0F1F2F3F4F5F6F7F8F97A5E4C7E6E6F-</p>
            <p>7CC1C2C3C4C5C6C7C8C9D1D2D3D4D5D6-</p>
            <p>D7D8D9E2E3E4E5E6E7E8E9ADE0BD5F6D-</p>
            <p>79818283848586878889919293949596-</p>
            <p>979899A2A3A4A5A6A7A8A9C04FD0A13F-</p>
            <p>68DC5142434447485253545756586367-</p>
            <p>719C9ECBCCCDDBDDDFECFC4AB1B2BFFF-</p>
            <p>4555CEDE49699A9BABAFB0B8B7AA8A8B-</p>
            <p>2B2C092128656264B438313433708024-</p>
            <p>22172906202A46661A35083936303A9F-</p>
            <p>8CAC7273740A757677231514046A783B-</p>
            <p>EE59EBEDCFEFA08EAEFEFBFD8DBABCBE-</p>
            <p>CA8F1BB93C3DE19D90BBB3DAFAEA3E41</p>
         </td>
      </tr>
   </tbody>
</table>

Or alternatively, you can use the following `CFTXLATE `command to generate an ASCII CP850 to EBCDIC CP1047 translation table.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTXLATE ID=CP850T0CP1047,FCODE=ASCII,NCODE=EBCDIC,DIRECT=BOTH,TABLE=00010203372D2E2F1605250B0C0D0E0F-
</p>
            <p>101112133C3D322618191C27071D1E1F-</p>
            <p>405A7F7B5B6C507D4D5D5C4E6B604B61-</p>
            <p>F0F1F2F3F4F5F6F7F8F97A5E4C7E6E6F-</p>
            <p>7CC1C2C3C4C5C6C7C8C9D1D2D3D4D5D6-</p>
            <p>D7D8D9E2E3E4E5E6E7E8E9ADE0BD5F6D-</p>
            <p>79818283848586878889919293949596-</p>
            <p>979899A2A3A4A5A6A7A8A9C04FD0A13F-</p>
            <p>68DC5142434447485253545756586367-</p>
            <p>719C9ECBCCCDDBDDDFECFC70B180BFFF-</p>
            <p>4555CEDE49699A9BABAFB0B8B7AA8A8B-</p>
            <p>2B2C092128656264B4383134334AB224-</p>
            <p>22172906202A46661A35083936303A9F-</p>
            <p>8CAC7273740A757677231514046A783B-</p>
            <p>EE59EBEDCFEFA08EAEFEFBFD8DBABCBE-</p>
            <p>CA8F1BB9B6B5E19D90BBB3DAFAEA3E41</p>
         </td>
      </tr>
   </tbody>
</table>
