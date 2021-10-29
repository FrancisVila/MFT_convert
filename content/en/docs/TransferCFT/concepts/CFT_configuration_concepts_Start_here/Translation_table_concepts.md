{
    "title": "Define translation tables",
    "linkTitle": "Conversion tables CFTXLATE",
    "weight": "200"
}This topic describes the Transfer CFT translation table concept and how to use the corresponding CFTXLATE object to manage machine language translation. You can create and use a translation table between 2 computers each
using a different alphabet. Each table is built using a file containing a unique 256-character
record, where through its position and value each character defines
the correspondence between two alphabets.

You can use a new translation table when sending or receiving a file, and ONLINE to the data sent as the transmission
proceeds, or OFF LINE to any file using the COPYFILE command.

-   [Create a new translation table](#Create)
    -   Delivered tools
    -   Reduced alphabets
-   [Define a translation and execute a transfer](#Define)
-   [Limitations](#Limitati)
-   [CFTXLATE command syntax](../../c_intro_userinterfaces/command_summary)
-   [Code pages and translation tables](#Code2)
-   Default translation tables

## <span id="Create"></span>Default translation tables

By default, Transfer CFT provides 4 internal ASCII/EBCDIC translation
tables, two for each transfer direction. These tables are bijective. These correspond loosely to translation between code pages EBCDIC 1047 and ASCII 437, with some small differences.

## Create a new translation table

Begin by creating a translation table file, and modify as needed. You can use the [OS specific delivered tool](#Use2) to help with this task. Or use the following procedure:

1.  Create a file as shown in the following example, containing hexadecimal characters from 00 to FF.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>00 01 02 03 04 05 06 07 - 08 09 0A 0B 0C 0D 0E 0F</p>
            <p>10 11 12 13 14 15 16 17 - 18 19 1A 1B 1C 1D 1E 1F</p>
            <p>20 21 22 23 24 25 26 27 - 28 29 2A 2B 2C 2D 2E 2F</p>
            <p>30 31 32 33 34 35 36 37 - 38 39 3A 3B 3C 3D 3E 3F</p>
            <p>40 41 42 43 44 45 46 47 - 48 49 4A 4B 4C 4D 4E 4F</p>
            <p>50 51 52 53 54 55 56 57 - 58 59 5A 5B 5C 5D 5E 5F</p>
            <p>60 61 62 63 64 65 66 67 - 68 69 6A 6B 6C 6D 6E 6F</p>
            <p>70 71 72 73 74 75 76 77 - 78 79 7A 7B 7C 7D 7E 7F</p>
            <p>80 81 82 83 84 85 86 87 - 88 89 8A 8B 8C 8D 8E 8F</p>
            <p>90 91 92 93 94 95 96 97 - 98 99 9A 9B 9C 9D 9E 9F</p>
            <p>A0 A1 A2 A3 A4 A5 A6 A7 - A8 A9 AA AB AC AD AE AF</p>
            <p>B0 B1 B2 B3 B4 B5 B6 B7 - B8 B9 BA BB BC BD BE BF</p>
            <p>C0 C1 C2 C3 C4 C5 C6 C7 - C8 C9 CA CB CC CD CE CF</p>
            <p>D0 D1 D2 D3 D4 D5 D6 D7 - D8 D9 DA DB DC DD DE DF</p>
            <p>E0 E1 E2 E3 E4 E5 E6 E7 - E8 E9 EA EB EC ED EE EF</p>
            <p>F0 F1 F2 F3 F4 F5 F6 F7 - F8 F9 FA FB FC FD FE FF</p>         </td>
      </tr>
   </tbody>
</table>

You can use the following `CFTXLATE `command to generate an ASCII CP437 to EBCDIC CP1047 translation table.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td><pre><code>CFTXLATE ID=CP437TOCP1047,FCODE=ASCII,NCODE=EBCDIC,DIRECT=BOTH,TABLE=00010203372D2E2F1605250B0C0D0E0F-
10111213B6B5322618191C27071D1E1F-
405A7F7B5B6C507D4D5D5C4E6B604B61-
F0F1F2F3F4F5F6F7F8F97A5E4C7E6E6F-
7CC1C2C3C4C5C6C7C8C9D1D2D3D4D5D6-
D7D8D9E2E3E4E5E6E7E8E9ADE0BD5F6D-
79818283848586878889919293949596-
979899A2A3A4A5A6A7A8A9C04FD0A13F-
68DC5142434447485253545756586367-
719C9ECBCCCDDBDDDFECFC4AB1B2BFFF-
4555CEDE49699A9BABAFB0B8B7AA8A8B-
2B2C092128656264B438313433708024-
22172906202A46661A35083936303A9F-
8CAC7273740A757677231514046A783B-
EE59EBEDCFEFA08EAEFEFBFD8DBABCBE-
CA8F1BB93C3DE19D90BBB3DAFAEA3E41</code></pre>         </td>
      </tr>
   </tbody>
</table>

In the Transfer CFT UI or Swagger REST API, you can use the format:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td><pre xml:space="preserve"><code> CFTXLATE ID=CP437TOCP1047,FCODE=ASCII,NCODE=EBCDIC,DIRECT=BOTH,TABLE=00010203372D2E2F1605250B0C0D0E0F-</code></pre>
<pre xml:space="preserve"><code>00010203372D2E2F1605250B0C0D0E0F10111213B6B5322618191C27071D1E1F405A7F7B5B6C507D4D5D5C4E6B604B61F0F1F2F3F4F5F6F7F8F97A5E4C7E6E6F7CC1C2C3C4C5C6C7C8C9D1D2D3D4D5D6D7D8D9E2E3E4E5E6E7E8E9ADE0BD5F6D79818283848586878889919293949596979899A2A3A4A5A6A7A8A9C04FD0A13F68DC5142434447485253545756586367719C9ECBCCCDDBDDDFECFC4AB1B2BFFF4555CEDE49699A9BABAFB0B8B7AA8A8B2B2C092128656264B43831343370802422172906202A46661A35083936303A9F8CAC7273740A757677231514046A783BEE59EBEDCFEFA08EAEFEFBFD8DBABCBECA8F1BB93C3DE19D90BBB3DAFAEA3E41</code></pre>         </td>
      </tr>
   </tbody>
</table>

Or alternatively, you can use the following `CFTXLATE `command to generate a ASCII CP850 to EBCDIC CP1047 translation table.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td><pre><code>CFTXLATE ID=CP850T0CP1047,FCODE=ASCII,NCODE=EBCDIC,DIRECT=BOTH,TABLE=00010203372D2E2F1605250B0C0D0E0F-
10111213B6B5322618191C27071D1E1F-
405A7F7B5B6C507D4D5D5C4E6B604B61-
F0F1F2F3F4F5F6F7F8F97A5E4C7E6E6F-
7CC1C2C3C4C5C6C7C8C9D1D2D3D4D5D6-
D7D8D9E2E3E4E5E6E7E8E9ADE0BD5F6D-
79818283848586878889919293949596-
979899A2A3A4A5A6A7A8A9C04FD0A13F-
68DC5142434447485253545756586367-
719C9ECBCCCDDBDDDFECFC4AB1B2BFFF-
4555CEDE49699A9BABAFB0B8B7AA8A8B-
2B2C092128656264B438313433708024-
22172906202A46661A35083936303A9F-
8CAC7273740A757677231514046A783B-
EE59EBEDCFEFA08EAEFEFBFD8DBABCBE-
CA8F1BB93C3DE19D90BBB3DAFAEA3E41</code></pre>         </td>
      </tr>
   </tbody>
</table>

### <span id="Use2"></span>Delivered tools

Transfer CFT is delivered with a platform specific tool to help you create an XLATE table.

-   Mainframes - A JCL is provided to help with creating both local and remote tables. Refer to the CFTXLATE member in the installation library.

-   UNIX/Windows - Use the Axway delivered [xvi utility<span aria-hidden="true"> Use this utility to update a conversion table.
    </span>](javascript:void(0)) located in the home/bin folder.

    xvi syntax

    xvi \[-d | -a | -e | -l &lt;file> \] &lt;table>

    **Standard use**

    xvi &lt;table>: updates a valid existing &lt;table> (256 characters)

    **Advanced use**

    -d: displays a valid existing table in ASCII

    -a: creates a &lt;table> to convert from ASCII to EBCDIC (if CFTXLATE command table exists, it is overwritten)

    -e: creates a &lt;table> to convert from EBCDIC to ASCII (if CFTXLATE command table exists, it is overwritten)

    -l: creates a &lt;table> from an ASCII &lt;file>, generally the file from option -d (if the table exists, it is overwritten)

The correct base table means that a table behaves exactly the same as the current default mapping from EBCDIC to ASCII.

### <span id="Reduced"></span>Reduced alphabet

You can also manually create a translation table for a reduced alphabet.
The invalid characters are associated with the character &lt;DEL> of
the target alphabet.

## <span id="Define"></span>Define a translation and execute a transfer

Use the CFTXLATE object to define translation tables between 2 alphabets. A definition includes:

-   Transfer direction (DIRECT: SEND, RECV, or BOTH)
-   File data code
    type (FCODE: ASCII or EBCDIC)
-   Data network
    code type (NCODE: ASCII or EBCDIC)
-   Translation table file name (FNAME)

If DIRECT = SEND (or = BOTH), the file (FNAME) contains the description
of the send translation table (FCODE to NCODE) and if DIRECT = RECV (or
= BOTH), it contains the description of the receive table (NCODE to FCODE).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If FCODE or NCODE are BINARY no translation
takes place.         </td>
      </tr>
   </tbody>
</table>

The identifier
of these tables is the value of the DEFAULT parameter of the CFTPARM command.
It is, however, possible to replace, modify or delete these internal tables
by CFTXLATE commands having this identifier. When Transfer CFT does not find an associated table for these 4 transfer
criteria, it looks for the default table (value of the DEFAULT
parameter of the CFTPARM command, for the XLATE parameter).

If the values of the FCODE and NCODE parameters are different, Transfer
CFT has to find a valid translation table. It is consequently not authorized
to delete a default translation table.

### Create a new CFTXLATE

Create the following new object, which you can use instead of the default in file transfers. In this example, for a given partner you want to use explicitly this translation table.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftxlate id=new, fcode=ebcdic, ncode=ascii, direct=both, mode=create, fname=cp1047tocp437         </td>
      </tr>
   </tbody>
</table>

If you created a translation table that maps ASCII to ASCII, for example, remember to set both the ncode and fcode to ASCII.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftxlate id=new, fcode=ascii, ncode=ascii, direct=both, mode=create, fname=cp850tocp437         </td>
      </tr>
   </tbody>
</table>

### Override default CFTXLATE

Create the following objects one for each translation direction. These new objects override the default translation table.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftxlate id=bin, fcode=ebcdic, ncode=ascii, direct=both, mode=create, fname=cp1047tocp437
            <p>cftxlate id=bin, fcode=ascii, ncode=ebcidic, direct=both, mode=create, fname=cp437tocp1047</p>         </td>
      </tr>
   </tbody>
</table>

### Execute the transfer command

Translation tables are used if FCODE and NCODE are not set to BINARY. When sending a file, Transfer CFT translates FCODE to NCODE. When receiving a file, Transfer CFT translates from NCODE to FCODE.

In the following example, the translation table that is specified by the xlate parameter is used instead of the default translation table.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>send part=paris, idf=myflow, xlate=cp437tocp1047, fcode=ascii, ncode=ebcdic         </td>
      </tr>
   </tbody>
</table>

However in the following example the default translation tables are used, provided the send template model does not include an xlate definition.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>send part=paris,idf=myflow, fcode=ascii, ncode=ebcdic         </td>
      </tr>
   </tbody>
</table>

A translation table is used if one of the following conditions are met, in the
order of priority indicated:

-   the table identifier
    has been indicated in the SEND/CFTSEND command  
    (SEND XLATE = identifier) or RECV/CFTRECV command
-   the table identifier
    has been indicated in the CFTPART command  
    (CFTPART XLATE = identifier)
-   the table identifier
    is the default identifier of the Transfer CFT  
    (CFTPARM DEFAULT = identifier)

And if all the following conditions are met:

-   transfer direction
    corresponding to the DIRECT parameter
-   data code specified
    for this file in the FCODE parameter
-   network data
    code in the NCODE parameter

## <span id="Limitati"></span>Limitations and usage restrictions

-   Central Governance **interoperability** Central Governance allows you to use the default translation tables, but not to create new translation tables via the Central Governance user interface. To create and use additional tables, in Transfer CFT  manually create translation tables as described in this section, and refer to them using the XLATE parameter in a SEND or RECV command.
-   In the event of file store and forward by partner, there is no translation
    on the intermediate site.
-   You cannot override the default translation table when using COPYFILE.

## <span id="Code2"></span>Code pages and translation tables

The following tables provide basic mapping printable hexadecimal characters for translation as a reference.

### <span id="Code"></span>Code pages

#### Printable hexadecimal EBCDIC (CP1047)

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p> </p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p>1</p>         </td>
         <td>            <p>2</p>         </td>
         <td>            <p>3</p>         </td>
         <td>            <p>4</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>6</p>         </td>
         <td>            <p>7</p>         </td>
         <td>            <p>8</p>         </td>
         <td>            <p>9</p>         </td>
         <td>            <p>A</p>         </td>
         <td>            <p>B</p>         </td>
         <td>            <p>C</p>         </td>
         <td>            <p>D</p>         </td>
         <td>            <p>E</p>         </td>
         <td>            <p>F</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>4</p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p>ƒ</p>         </td>
         <td>            <p>„</p>         </td>
         <td>            <p>…</p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>†</p>         </td>
         <td>            <p>‡</p>         </td>
         <td>            <p>¤</p>         </td>
         <td>            <p>›</p>         </td>
         <td>            <p>.</p>         </td>
         <td>            <p>&lt;</p>         </td>
         <td>            <p>(</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>|</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>5</p>         </td>
         <td>            <p>&amp;</p>         </td>
         <td>            <p>‚</p>         </td>
         <td>            <p>ˆ</p>         </td>
         <td>            <p>‰</p>         </td>
         <td>            <p>Š</p>         </td>
         <td>            <p>¡</p>         </td>
         <td>            <p>Œ</p>         </td>
         <td>            <p>‹</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>á</p>         </td>
         <td>            <p>!</p>         </td>
         <td>            <p>$</p>         </td>
         <td>            <p>*</p>         </td>
         <td>            <p>)</p>         </td>
         <td>            <p>;</p>         </td>
         <td>            <p>^</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>6</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>Ž</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>€</p>         </td>
         <td>            <p>¥</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>","</p>         </td>
         <td>            <p>%</p>         </td>
         <td>            <p>_</p>         </td>
         <td>            <p>&gt;</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>7</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>`</p>         </td>
         <td>            <p>:</p>         </td>
         <td>            <p>#</p>         </td>
         <td>            <p>@</p>         </td>
         <td>            <p>'</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>""""</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>8</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>a</p>         </td>
         <td>            <p>b</p>         </td>
         <td>            <p>c</p>         </td>
         <td>            <p>d</p>         </td>
         <td>            <p>e</p>         </td>
         <td>            <p>f</p>         </td>
         <td>            <p>g</p>         </td>
         <td>            <p>h</p>         </td>
         <td>            <p>i</p>         </td>
         <td>            <p>®</p>         </td>
         <td>            <p>¯</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>ñ</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>9</p>         </td>
         <td>            <p>ø</p>         </td>
         <td>            <p>j</p>         </td>
         <td>            <p>k</p>         </td>
         <td>            <p>l</p>         </td>
         <td>            <p>m</p>         </td>
         <td>            <p>n</p>         </td>
         <td>            <p>o</p>         </td>
         <td>            <p>p</p>         </td>
         <td>            <p>q</p>         </td>
         <td>            <p>r</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>§</p>         </td>
         <td>            <p>‘</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>’</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>A</p>         </td>
         <td>            <p>æ</p>         </td>
         <td>            <p>~</p>         </td>
         <td>            <p>s</p>         </td>
         <td>            <p>t</p>         </td>
         <td>            <p>u</p>         </td>
         <td>            <p>v</p>         </td>
         <td>            <p>w</p>         </td>
         <td>            <p>x</p>         </td>
         <td>            <p>y</p>         </td>
         <td>            <p>z</p>         </td>
         <td>            <p>­</p>         </td>
         <td>            <p>¨</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>[</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>B</p>         </td>
         <td>            <p>ª</p>         </td>
         <td>            <p>œ</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>ú</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>¬</p>         </td>
         <td>            <p>«</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>]</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>C</p>         </td>
         <td>            <p>{</p>         </td>
         <td>            <p>A</p>         </td>
         <td>            <p>B</p>         </td>
         <td>            <p>C</p>         </td>
         <td>            <p>D</p>         </td>
         <td>            <p>E</p>         </td>
         <td>            <p>F</p>         </td>
         <td>            <p>G</p>         </td>
         <td>            <p>H</p>         </td>
         <td>            <p>I</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>“</p>         </td>
         <td>            <p>”</p>         </td>
         <td>            <p>•</p>         </td>
         <td>            <p>¢</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>D</p>         </td>
         <td>            <p>}</p>         </td>
         <td>            <p>J</p>         </td>
         <td>            <p>K</p>         </td>
         <td>            <p>L</p>         </td>
         <td>            <p>M</p>         </td>
         <td>            <p>N</p>         </td>
         <td>            <p>O</p>         </td>
         <td>            <p>P</p>         </td>
         <td>            <p>Q</p>         </td>
         <td>            <p>R</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>–</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>—</p>         </td>
         <td>            <p>£</p>         </td>
         <td>            <p>˜</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>E</p>         </td>
         <td>            <p>\</p>         </td>
         <td>            <p>ö</p>         </td>
         <td>            <p>S</p>         </td>
         <td>            <p>T</p>         </td>
         <td>            <p>U</p>         </td>
         <td>            <p>V</p>         </td>
         <td>            <p>W</p>         </td>
         <td>            <p>X</p>         </td>
         <td>            <p>Y</p>         </td>
         <td>            <p>Z</p>         </td>
         <td>            <p>ý</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>™</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>F</p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p>1</p>         </td>
         <td>            <p>2</p>         </td>
         <td>            <p>3</p>         </td>
         <td>            <p>4</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>6</p>         </td>
         <td>            <p>7</p>         </td>
         <td>            <p>8</p>         </td>
         <td>            <p>9</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>š</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p>?</p>         </td>
         <td>            <p> </p>         </td>
      </tr>
   </tbody>
</table>

#### Printable hexadecimal ASCII (CP437)

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p> </p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p>1</p>         </td>
         <td>            <p>2</p>         </td>
         <td>            <p>3</p>         </td>
         <td>            <p>4</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>6</p>         </td>
         <td>            <p>7</p>         </td>
         <td>            <p>8</p>         </td>
         <td>            <p>9</p>         </td>
         <td>            <p>A</p>         </td>
         <td>            <p>B</p>         </td>
         <td>            <p>C</p>         </td>
         <td>            <p>D</p>         </td>
         <td>            <p>E</p>         </td>
         <td>            <p>F</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>2</p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p>!</p>         </td>
         <td>            <p>"</p>         </td>
         <td>            <p>#</p>         </td>
         <td>            <p>$</p>         </td>
         <td>            <p>%</p>         </td>
         <td>            <p>&amp;</p>         </td>
         <td>            <p>'</p>         </td>
         <td>            <p>(</p>         </td>
         <td>            <p>)</p>         </td>
         <td>            <p>*</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>,</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>.</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>3</p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p>1</p>         </td>
         <td>            <p>2</p>         </td>
         <td>            <p>3</p>         </td>
         <td>            <p>4</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>6</p>         </td>
         <td>            <p>7</p>         </td>
         <td>            <p>8</p>         </td>
         <td>            <p>9</p>         </td>
         <td>            <p>:</p>         </td>
         <td>            <p>;</p>         </td>
         <td>            <p>&lt;</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>&gt;</p>         </td>
         <td>            <p>?</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>4</p>         </td>
         <td>            <p>@</p>         </td>
         <td>            <p>A</p>         </td>
         <td>            <p>B</p>         </td>
         <td>            <p>C</p>         </td>
         <td>            <p>D</p>         </td>
         <td>            <p>E</p>         </td>
         <td>            <p>F</p>         </td>
         <td>            <p>G</p>         </td>
         <td>            <p>H</p>         </td>
         <td>            <p>I</p>         </td>
         <td>            <p>J</p>         </td>
         <td>            <p>K</p>         </td>
         <td>            <p>L</p>         </td>
         <td>            <p>M</p>         </td>
         <td>            <p>N</p>         </td>
         <td>            <p>O</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>5</p>         </td>
         <td>            <p>P</p>         </td>
         <td>            <p>Q</p>         </td>
         <td>            <p>R</p>         </td>
         <td>            <p>S</p>         </td>
         <td>            <p>T</p>         </td>
         <td>            <p>U</p>         </td>
         <td>            <p>V</p>         </td>
         <td>            <p>W</p>         </td>
         <td>            <p>X</p>         </td>
         <td>            <p>Y</p>         </td>
         <td>            <p>Z</p>         </td>
         <td>            <p>[</p>         </td>
         <td>            <p>\</p>         </td>
         <td>            <p>]</p>         </td>
         <td>            <p>^</p>         </td>
         <td>            <p>_</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>6</p>         </td>
         <td>            <p>`</p>         </td>
         <td>            <p>a</p>         </td>
         <td>            <p>b</p>         </td>
         <td>            <p>c</p>         </td>
         <td>            <p>d</p>         </td>
         <td>            <p>e</p>         </td>
         <td>            <p>f</p>         </td>
         <td>            <p>g</p>         </td>
         <td>            <p>h</p>         </td>
         <td>            <p>i</p>         </td>
         <td>            <p>j</p>         </td>
         <td>            <p>k</p>         </td>
         <td>            <p>l</p>         </td>
         <td>            <p>m</p>         </td>
         <td>            <p>n</p>         </td>
         <td>            <p>o</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>7</p>         </td>
         <td>            <p>p</p>         </td>
         <td>            <p>q</p>         </td>
         <td>            <p>r</p>         </td>
         <td>            <p>s</p>         </td>
         <td>            <p>t</p>         </td>
         <td>            <p>u</p>         </td>
         <td>            <p>v</p>         </td>
         <td>            <p>w</p>         </td>
         <td>            <p>x</p>         </td>
         <td>            <p>y</p>         </td>
         <td>            <p>z</p>         </td>
         <td>            <p>{</p>         </td>
         <td>            <p>|</p>         </td>
         <td>            <p>}</p>         </td>
         <td>            <p>~</p>         </td>
         <td>            <p> </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>8</p>         </td>
         <td>            <p>Ç</p>         </td>
         <td>            <p>ü</p>         </td>
         <td>            <p>é</p>         </td>
         <td>            <p>â</p>         </td>
         <td>            <p>ä</p>         </td>
         <td>            <p>à</p>         </td>
         <td>            <p>å</p>         </td>
         <td>            <p>ç</p>         </td>
         <td>            <p>ê</p>         </td>
         <td>            <p>ë</p>         </td>
         <td>            <p>è</p>         </td>
         <td>            <p>ï</p>         </td>
         <td>            <p>î</p>         </td>
         <td>            <p>ì</p>         </td>
         <td>            <p>Ä</p>         </td>
         <td>            <p>Å</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>9</p>         </td>
         <td>            <p>É</p>         </td>
         <td>            <p>æ</p>         </td>
         <td>            <p>Æ</p>         </td>
         <td>            <p>ô</p>         </td>
         <td>            <p>ö</p>         </td>
         <td>            <p>ò</p>         </td>
         <td>            <p>û</p>         </td>
         <td>            <p>ù</p>         </td>
         <td>            <p>ÿ</p>         </td>
         <td>            <p>Ö</p>         </td>
         <td>            <p>Ü</p>         </td>
         <td>            <p>¢</p>         </td>
         <td>            <p>£</p>         </td>
         <td>            <p>¥</p>         </td>
         <td>            <p>P</p>         </td>
         <td>            <p>ƒ</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>A</p>         </td>
         <td>            <p>á</p>         </td>
         <td>            <p>í</p>         </td>
         <td>            <p>ó</p>         </td>
         <td>            <p>ú</p>         </td>
         <td>            <p>ñ</p>         </td>
         <td>            <p>Ñ</p>         </td>
         <td>            <p>ª</p>         </td>
         <td>            <p>º</p>         </td>
         <td>            <p>¿</p>         </td>
         <td>            <p>¬</p>         </td>
         <td>            <p>¬</p>         </td>
         <td>            <p>½</p>         </td>
         <td>            <p>¼</p>         </td>
         <td>            <p>¡</p>         </td>
         <td>            <p>«</p>         </td>
         <td>            <p>»</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>B</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>C</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>-</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>D</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>+</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>_</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p>¯</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>E</p>         </td>
         <td>            <p>a</p>         </td>
         <td>            <p>ß</p>         </td>
         <td>            <p>G</p>         </td>
         <td>            <p>p</p>         </td>
         <td>            <p>S</p>         </td>
         <td>            <p>s</p>         </td>
         <td>            <p>µ</p>         </td>
         <td>            <p>t</p>         </td>
         <td>            <p>F</p>         </td>
         <td>            <p>T</p>         </td>
         <td>            <p>O</p>         </td>
         <td>            <p>d</p>         </td>
         <td>            <p>8</p>         </td>
         <td>            <p>f</p>         </td>
         <td>            <p>e</p>         </td>
         <td>            <p>n</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>F</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>±</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>(</p>         </td>
         <td>            <p>)</p>         </td>
         <td>            <p>÷</p>         </td>
         <td>            <p>˜</p>         </td>
         <td>            <p>°</p>         </td>
         <td>            <p>·</p>         </td>
         <td>            <p>·</p>         </td>
         <td>            <p>v</p>         </td>
         <td>            <p>n</p>         </td>
         <td>            <p>²</p>         </td>
         <td>            <p>¦</p>         </td>
         <td>            <p> </p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Translat"></span>Translation tables

This section demonstrates how the translation table works. In a translation table, the "s" character takes the value "t":

-   "s" is
    the value of the character of the "source" alphabet
-   "t" is
    the value of the character of the corresponding "target" alphabet

The first character is in position 0, and the first position is 00. In this example the hexadecimal value 40, which is the EBCDIC blank character, corresponds to the value 20, which is the blank character ASCII blank character.

![](/Images/TransferCFT/temp_translation_table.png)

Related
topics

-   Command syntax
    [CFTXLATE](../../c_intro_userinterfaces/command_summary)
-   Parameter list
    [CFTXLATE](../../CFTUTIL/Conf/CFTXLATE.htm)
-   UI operations
    Defining translation tables
