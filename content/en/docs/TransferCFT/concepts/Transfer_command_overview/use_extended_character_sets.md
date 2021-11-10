{
    "title": "Use extended character sets",
    "linkTitle": "Using extended character sets ",
    "weight": "330"
}Character transcoding (using extended character sets) defines how data are encoded during the transfer process. This is important when transferring files that do not have the same coding requirements on the sending and receiving systems.

## What is extended transcoding?

Typical transcoding, using either XLATE or internal transcoding (ASCII/EBCDIC/BINARY) methods, extends in Transfer CFT to include multi-bytes encoding. Note that using XLATE consumes less CPU than the NCHARSET/FCHARSET method, however XLATE is restricted to single-byte character sets.

The FCHARSET parameter defines the local file encoding, and the NCHARSET
parameter defines the remote and network data encoding. These parameters, FCHARSET and NCHARSET, are available for the following objects:

-   SEND/RECV
-   CFTSEND/CFTRECV
-   CFTPART
-   CFTPROT

<span id="Using"></span>

## Using character sets for transcoding

You can set the FCHARSET and NCHARSET values using the Transfer CFT character sets mapping (CFT\_UTF-8, CFT\_UTF-16, CFT\_ISO8859-1, ...) or directly using most available iconv charsets (UTF-8, UTF-16, ISO8859-1, ...).

The UCONF cft.cft\_charsets parameter defines the Transfer CFT character sets mapping, which you can use to add an abstraction layer to a flow's configuration definition.

For example, if you define an NCHARSET as CFT\_ISO8859-1, the parameter is translated as 'iso88591' for HPUX OSes, as '00819' for IBM i, and as 'ISO8859-1' for all other platforms. We strongly recommend that you use this option.

> **Note:**
>
> On versions of OS/400 prior to Transfer CFT 3.1.3, use the charset number only without the CFT\_ prefix.

### Using the //IGNORE functionality

In some cases you may want to disregard characters either in a file to be sent, or in a file to be received. You can use the //IGNORE functionality to disregard characters that you do not want to be present in the target.

Depending on your operating system, note the following specific //IGNORE behavior:

-   Sun: converts the character to a question mark '?'
-   AIX and HPUX: converts the character to the substitute character (the control character 1A hex)
-   All other systems: no character substitution occurs

**Example 1**

Use the Transfer CFT mapping and the IGNORE functionality to translate a local text file before sending it, for example from UTF-8 to ISO8859-1:



    CFTUTIL SEND PART = NEWYORK,
      IDF = TEST_IGNORE,
      FCHARSET = CFT_UTF-8,
      NCHARSET = CFT_ISO8859-1//IGNORE,
      FTYPE = T

**Example 2**

Use the Transfer CFT mapping and the IGNORE functionality to translate a received file, for example from UTF-8 to ISO8859-1:



    CFTUTIL RECV PART = NEWYORK,
      IDF = TEST_IGNORE,
      FCHARSET = CFT_ISO8859-1//IGNORE,
      NCHARSET = CFT_UTF-8,
      FTYPE = T

See *Adding a character set: transcoding* (in the general unified configuration parameters) for a complete list of the Transfer CFT default charsets.

## FCHARSET/NCHARSET value resolution

The FCHARSET/NCHARSET values for a transfer are defined as follows:

1.  SEND/RECV: The transfer uses
    the charset value provided by the SEND/RECV commands if the corresponding
    CFTSEND/CFTRECV permits it.
2.  CFTSEND/CFTRECV: If the SEND/RECV
    command is empty, the values come from the corresponding CFTSEND/CFTRECV
    objects.
3.  CFTPART: If the charset value
    is still empty, the values come from the corresponding CFTPART object.
4.  CFTPROT: If the charset
    value is still empty, the values come from the corresponding CFTPROT object.

The following rules apply:

-   FCHARSET and NCHARSET
    can be set by independent sources, be that SEND, CFTSEND, CFTPART, or
    CFTPROT.
-   If one or both
    of the FCHARSET and NCHARSET fields are empty, or set to NONE, the extended
    transcoding is disabled and the traditional transcoding applies.
-   If you use FCHARSET/NCHARSET, the FCODE/NCODE parameters are ignored.

### Considerations when choosing the file type

It is generally recommended that you use text files in the variable-length format when possible.

When using multibyte encoding for fixed or limited record size files, please pay attention to the following important considerations:

-   Shrinking a record
    can cause a fatal error if it occurs in the middle of a multibyte character.
-   Padding a record
    can cause a fatal error if the size to be padded is not a multiple of
    the pad character. The pad character is a blank for a text file, and a
    zero for binary files.
-   Errors when using binary files are more likely (with the exception of single-byte encoding).
-   When using FTYPE=J (stream text), an interrupted transfer restarts at the beginning of the transfer, not at the last synchronization point.

<span id="CHARSET"></span>

### CHARSET mapping

The following table shows the CHARSET mapping. Brackets in the UNIX/Windows column indicate platform exceptions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">CFT_ charset         </th>
<th class="HeadE-Column1-Header1">UNIX/Windows         </th>
<th class="HeadD-Column1-Header1">IBM i         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CFT_UTF-8         </td>
         <td>UTF-8         </td>
         <td>01208         </td>
      </tr>
      <tr>
         <td>CFT_UTF-16         </td>
         <td>UTF-16         </td>
         <td>01204         </td>
      </tr>
      <tr>
         <td>CFT_UTF-16LE         </td>
         <td><p>UTF-16LE</p>
<p>[AIX] UTF-16le</p>
<p> </p>         </td>
         <td>01202         </td>
      </tr>
      <tr>
         <td>CFT_UTF-16BE         </td>
         <td><p>UTF-16BE</p>
<p>[AIX] UTF-16</p>
<p>[HPUX] ucs2</p>         </td>
         <td>01200         </td>
      </tr>
      <tr>
         <td>CFT_UTF-32         </td>
         <td><p>UTF-32</p>
<p>[HPUX] UTF-32BE</p>         </td>
         <td>01236         </td>
      </tr>
      <tr>
         <td>CFT_UTF-32LE         </td>
         <td>UTF-32LE         </td>
         <td>01234         </td>
      </tr>
      <tr>
         <td>CFT_UTF-32BE         </td>
         <td><p>UTF-32BE</p>
<p>[AIX] UTF-32</p>
<p>[HPUX] ucs4</p>         </td>
         <td>01232         </td>
      </tr>
      <tr>
         <td>CFT_UCS-2         </td>
         <td><p>UCS-2</p>
<p>[HPUX] = UCS-2BE</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>CFT_UCS-2LE         </td>
         <td><p>UCS-2LE</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>CFT_UCS-2BE         </td>
         <td><p>UCS-2BE</p>
<p>[AIX] UCS-2</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>CFT_CP850         </td>
         <td><p>CP850</p>
<p>[AIX, MVS (z/OS), VMS] IBM-850</p>         </td>
         <td>00850         </td>
      </tr>
      <tr>
         <td>CFT_BIG5         </td>
         <td><p>BIG5</p>
<p>[AIX, HPUX] big5</p>         </td>
         <td>00947         </td>
      </tr>
      <tr>
         <td>CFT_ISO8859-1         </td>
         <td><p>ISO8859-1</p>
<p>[HPUX] iso88591</p>         </td>
         <td>00819         </td>
      </tr>
      <tr>
         <td>CFT_ISO8859-15         </td>
         <td><p>ISO8859-15</p>
<p>[HPUX] iso885915</p>         </td>
         <td>00923         </td>
      </tr>
      <tr>
         <td>CFT_EBCDIC-FR         </td>
         <td><p>[UNIX] EBCDIC-FR</p>
<p>[AIX, SUN] IBM-297</p>
<p>[HPUX, Windows] cp1147</p>         </td>
         <td>00297         </td>
      </tr>
   </tbody>
</table>
