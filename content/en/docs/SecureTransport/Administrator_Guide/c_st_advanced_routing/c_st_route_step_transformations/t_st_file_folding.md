{
    "title": "Line Folding",
    "linkTitle": "Line Folding",
    "weight": "330"
}The Line Folding transformation will break file lines to a maximum width specified in number of characters. The maximum file width is specified in the transformation step settings. If a file line exceeds the maximum width, the extra characters will be moved to the next line. The moved extra characters are moved to a line of their own and not appended in front of the next line.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the encoding a file is changed to IBM500, IBM037, or IBM424; the line ending of the input file should be LF and not CRLF. The CR is preserved in some cases and a new line appears between every original line. If the line ending is not LF, a Line Ending step can used before the Line Folding step.         </td>
      </tr>
</table>

To add a Line Folding transformation step to a Route Package Template take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Determine file fold width.
4.  Select source file encoding.
5.  Select output file encoding.
6.  Determine post transformation actions.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Steps 1, 3, and 4 are mandatory. All other steps are optional.         </td>
      </tr>
</table>

The following topics provide configuration details for the File Folding transformation step.:

-   [Input Files](#file)
-   [Proceed with route execution on step failure](#proceed)
-   [File fold transformation](#file2)
-   [File encoding](#file3)
-   [Post transformation action](#post)

**Related topics:**

-   [PGP Encryption](../t_st_pgp_encryption)
-   [PGP Decryption](../t_st_pgp_decryption)
-   [Compress](../t_st_compress)
-   [Decompress](../t_st_decompress)
-   [Line Ending](../t_st_line_ending)
-   [External Script](../t_st_external_script)
-   [Encoding Conversion](../t_st_charset_conversion)
-   [Characters Replace](../t_st_replace)
-   [Line Padding](../t_st_line_padding)
-   [Line Truncating](../t_st_line_truncating)
-   [Rename](../t_st_rename)

## <span id="File"></span>Input Files

The Input Files settings consist of the selection *Process only result from preceding step* and determining the Name Filter.

### Process only result from preceding step

When *Process only result from preceding step* is **enabled** only files produced by the preceding step will be used as input for this step.

When *Process only result from preceding step* is **disabled** or this is the first step all current working files will be used as input for this step.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Name Filter settings will also be applied on a given set of input files.         </td>
      </tr>
</table>

### Name Filter

Name filtering can either be set to process all files, process all text files, or process files based on a designated filename pattern forwarded by the selection of *Process only result from preceding step*.

If *Process all files* is selected, all files forwarded by the selection of *Process only result from preceding step* are processed.

If *Process all text files* is selected, all text files forwarded by the selection of *Process only result from preceding step* are processed.

Text file selection is determined based on the file extension and the MIME type that corresponds to that extension. MIME types are defined in the `mime.types` configuration file located in:

**Administrator's Tool &gt; Server Configuration &gt; Configuration Files**

Furthermore, some MIME types can be defined as text by configuring the `AdvancedRouting.TextMimeSubtypes` server configuration option. For example, to configure the `application/xml` MIME type to be treated as text, add `xml` to the server configuration option.

If *Process files based on a filename pattern* is selected, only the files that match the file globbing or regular expression all files forwarded by the selection of *Process only result from preceding step* are processed.

#### Filename patterns

Filename pattern matching supports `glob` and `regexp` syntax expressions.

When the designated pattern type is *File Globbing* then the `String` representation of the filename is matched using a limited pattern language that resembles regular expressions but with a simpler syntax. For example:

-   Matches files ending in `.xml`.

    `*.xml`

-   Matches file names starting with `foo.` that have a double character extension.

    `foo.??`

-   Matches file names ending in `.1`, `.2`, `.3`, `.4`, `.5`, `.6`, `.7`, `.8`, `.9`, `.0`.

    `*.[0-9]`

-   Matches file names having a single character extension different from `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `0`.

    `*.[!0-9]`

When the designated syntax is *Regular Expression* then the `String` representation of the filename is matched against a `Perl5.003` regular expressions. Perl5 extended regular expressions are also supported. For example:

-   Matches files ending in `.xml` or `.txt`.

    `.*\.(xml|txt)`

-   Case insensitive match of` data.xml` file.

    `(?i)data\.xml`

## <span id="Proceed"></span>Proceed with route execution on step failure

If *Proceed with route execution on step failure* is checked, the route execution continues even if the step execution fails.

## <span id="File2"></span>File fold transformation

The file fold width must be configured.

### File fold width

Maximum allowed file line width as specified in number of characters. The maximum number of characters is 1024.

## <span id="File3"></span>File encoding

The source file encoding must be configured. Configuring the output file encoding is not mandatory. If it is not set, the output file encoding will be the same as the source file encoding.

### Source file encoding

Encoding of the file that will be transformed specified by the name of a SecureTransport supported character set. The **Source file encoding:** field has an auto-complete function that lists matching SecureTransport supported character sets.

### Output file encoding

Encoding of the file that will be produced specified by the name of a SecureTransport supported character set. The **Output file encoding:** field has an auto-complete function that lists matching SecureTransport supported character sets.

## <span id="Post"></span>Post transformation action

The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to [Rename](../t_st_rename).