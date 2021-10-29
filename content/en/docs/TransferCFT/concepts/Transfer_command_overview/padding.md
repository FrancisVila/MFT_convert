{
    "title": "Pad records for text files",
    "linkTitle": "Padding records for text files",
    "weight": "350"
}You can define the pad/unpad character for fixed and variable formats at both the file and network level in the SEND, CFTSEND, CFTRECV and RECV commands when TYPE = FILE.

## <span id="Format"></span>Format options

Use the [FRECFM](../../c_intro_userinterfaces/command_summary/parameter_intro/frecfm) and [NRECFM](../../c_intro_userinterfaces/command_summary/parameter_intro/nrecfm) parameters to set the record format.

### Fixed format

`FRECFM = F` or `NRECFM = F`

When using a fixed format, the parameters FPAD and NPAD define the character to use for padding. If FPAD and NPAD are not set, the character used for padding is a space.

### Variable format

`FRECFM = V` or `NRECFM = V`

When using a variable format, FPAD and NPAD define the character to use to unpad the record. If you do not set FPAD or NPAD, then the record remains unchanged and no unpadding occurs.

## <span id="Paramete"></span>Parameters

FPAD = character

This parameter defines the padding character at the file level.

-   Fixed format: Specifies the character to use for padding using FPAD at file level. If FPAD is not set, the padding character depends on the FCODE used. When FCODE=ASCII it is an ASCII space, FCODE=EBCDIC it is an EBCDIC space, and FCODE=BINARY it is a binary zero.
-   Variable format: Defines the character to use to unpad the record. If FPAD is not set, the record is unchanged.

`NPAD = character`

This parameter defines the padding character at the network level.

-   Fixed format: Pads the record with this character up to the size defined by NLRECL. If NPAD is not set, the padding character depends on the FCODE used. When FCODE=ASCII it is an ASCII space, FCODE=EBCDIC it is an EBCDIC space, and FCODE=BINARY it is a binary zero
-   Variable format: Defines the character used to unpad the record. If NPAD is not set, the record is unchanged.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In addition to printable characters, you can also enter a non-printable character for NPAD or FPAD using the hexadecimal syntax: 0xHH. For example: <span>0xFC, 0xab, 0x00</span>         </td>
      </tr>
   </tbody>
</table>

## Usage

After the input or output file in each example a representation depicts the file sent or received over the network.

#### Example of padding a variable format file on the sender side

In the SEND profile (CFTSEND object) specify:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>fcode=ASCII</p>
            <p>frecfm=V</p>
            <p>nrecfm=F</p>
            <p>nlrecl=&lt;desired_record_size&gt;</p>
            <p>npad=@</p>         </td>
      </tr>
   </tbody>
</table>

**Input file**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway</p>
            <p>Transfer CFT</p>
            <p>v<span>3.9</span></p>         </td>
      </tr>
   </tbody>
</table>

File sent over the network, when nlrecl=20:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway@@@@@@@@@@@@@@@</p>
            <p>Transfer CFT@@@@@@@@</p>
            <p>v3.0.1@@@@@@@@@@@@@@</p>         </td>
      </tr>
   </tbody>
</table>

#### Example of unpadding a fixed format file on the sender side

In SEND profile (CFTSEND object) specify:

Input file when flrecl=20:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway@@@@@@@@@@@@@@@</p>
            <p>Transfer CFT@@@@@@@@</p>
            <p>v<span>3.9</span>@@@@@@@@@@@@@@</p>         </td>
      </tr>
   </tbody>
</table>

File sent over the network:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway</p>
            <p>Transfer CFT</p>
            <p>v<span>3.9</span></p>         </td>
      </tr>
   </tbody>
</table>

#### Example of padding a variable format file on the receiver side

In the RECV profile (CFTRECV object) specify:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>fcode=ASCII</p>
            <p>frecfm=F</p>
            <p>flrecl=&lt;desired_record_size&gt;</p>
            <p>fpad=@</p>         </td>
      </tr>
   </tbody>
</table>

File received from the network:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway</p>
            <p>Transfer CFT</p>
            <p>v<span>3.9</span></p>         </td>
      </tr>
   </tbody>
</table>

**Output file**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway@@@@@@@@@@@@@@@</p>
            <p>Transfer CFT@@@@@@@@</p>
            <p>v<span>3.9</span>@@@@@@@@@@@@@@</p>         </td>
      </tr>
   </tbody>
</table>

#### Example of unpadding a fixed format file on the receiver side

In the RECV profile (CFTRECV object) specify:

fcode=ASCII

frecfm=V

fpad=@

File received from the network

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway@@@@@@@@@@@@@@@</p>
            <p>Transfer CFT@@@@@@@@</p>
            <p>v<span>3.9</span>@@@@@@@@@@@@@@</p>         </td>
      </tr>
   </tbody>
</table>

Output file

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Axway</p>
            <p>Transfer CFT</p>
v<span>3.9</span>         </td>
      </tr>
   </tbody>
</table>
