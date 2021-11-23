{
    "title": "Characters Replace",
    "linkTitle": "Characters Replace",
    "weight": "290"
}> **Note:**
>
> Currently, the Character Replace transformation accepts Unicode or ASCII as an input, or mixed input for the Find and Replace fields.

> **Note:**
>
> If the encoding a file is changed to IBM500, IBM037, or IBM424; the line ending of the input file should be LF and not CRLF. The CR is preserved in some cases and a new line appears between every original line. If the line ending is not LF, a Line Ending step can used before the Characters Replace step.

> **Note:**
>
> The comma (,) symbol can be used in ASCII only as a separator and not as find criteria. For find criteria, the comma (,) symbol can only be used in Unicode.

The Characters Replace transformation has two working modes. Only one mode can be active at a time.

## Find/Replace mode

The Characters Replace transformation will search the input file for character sequences matching the specified search sequences and if a match is found it will be replaced with the replace character sequence. The search and replace character sequences are specified in the transformation step settings. More than one search sequence can be configured separating the sequences with a comma character.

This mode can be configured in one of two ways:

1.  The number of find sequences is one or greater. The replace sequence is only 1.  
    Multiple find sequences are specified separated with commas (,) and only a single replace sequence. In this case all find sequences have the same corresponding replace sequence. The transformation will search the input file for matches to the specified find sequences. If multiple sequences match the same text for replacement, only the first sequence that is found to fully match the text will be replaced.  

    > **Note:**
    >
    > Empty replace sequence is a valid configuration. If such is specified, when a search match is found the matching sequence will effectively be removed from the file content.

2.  The number of find and replace sequences is the same.  
    In this case each find character sequence has its own replace character sequence. The correlation between find and replace sequences is based on their position in the configuration (the first find sequence corresponds to the first replace sequence, the second find to the second replace and so on).  
    The transformation will search the input file for matches to the specified search sequences. When a match to a find sequence is found, it will be replaced by its own corresponding replace sequence. If multiple sequences match the same text for replacement, only the first sequence that is found to fully match the text will be replaced.

## Find/Line strip

The Characters Replace transformation will strip all file lines starting with a specified search character sequence. The search character sequence is specified in the transformation step settings. More than one search sequence can be configured separating the sequences with a comma character.

The transformation will search the input file for matches at the start of each row to the specified find sequences. If a match is found, the row will be removed from the file content.

## Characters Replace configuration

To add a Characters Replace transformation step to a Route Package Template take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Determine the working mode. If Find/Replace mode, complete the **Find** and **Replace** fields. If Find/Line strip mode, select **Strip lines starting with find string.** and complete the **Find** field.
4.  Select source file encoding option.
5.  Select output file encoding option.
6.  Determine post transformation actions.

> **Note:**
>
> Steps 1, 3, and 4 are mandatory. All other steps are optional.

The following topics provide configuration details for the Replace transformation step:

-   [Input Files](#File)
-   [Proceed with route execution on step failure](#Proceed)
-   [Find/Replace mode](#Find/Rep)
-   [Find/Line strip](#Find/Lin)
-   [File encoding](#File2)
-   [Post transformation action](#Post)

**Related topics:**

-   [PGP Encryption](../t_st_pgp_encryption)
-   [PGP Decryption](../t_st_pgp_decryption)
-   [Compress](../t_st_compress)
-   [Decompress](../t_st_decompress)
-   [Line Ending](../t_st_line_ending)
-   [External Script](../t_st_external_script)
-   [Encoding Conversion](../t_st_charset_conversion)
-   [Line Padding](../t_st_line_padding)
-   [Line Folding](../t_st_file_folding)
-   [Line Truncating](../t_st_line_truncating)
-   [Rename](../t_st_rename)

<span id="File"></span>

## Input Files

The Input Files settings consist of the selection *Process only result from preceding step* and determining the Name Filter.

### Process only result from preceding step

When *Process only result from preceding step* is **enabled** only files produced by the preceding step will be used as input for this step.

When *Process only result from preceding step* is **disabled** or this is the first step all current working files will be used as input for this step.

> **Note:**
>
> The Name Filter settings will also be applied on a given set of input files.

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

<span id="Proceed"></span>

## Proceed with route execution on step failure

If *Proceed with route execution on step failure* is checked, the route execution continues even if the step execution fails.

<span id="Find/Rep"></span>

## Find/Replace mode

If Find/Replace mode, complete the **Find** and **Replace** fields.

### Find

Specify the find character sequence. Unicode notation (\\uXXXX) can be used. Multiple find character sequences separated with a comma (,) can be specified.

> **Note:**
>
> Comma must be Unicode encoded (\\002c) if used in the find sequence.

### Replace

Specify the replace character sequence. Unicode notation (\\uXXXX) can be used. Multiple replace character sequences separated with a comma (,) can be specified. The number of replace sequences must be equal to the number of find sequences or just a single sequence.

> **Note:**
>
> Leaving this field blank is a valid configuration. Empty replace sequence is treated as an empty character.

> **Note:**
>
> Comma must be Unicode encoded (\\002c) if used in the replace sequence.

<span id="Find/Lin"></span>

## Find/Line strip

If Find/Line strip, select **Strip lines starting with find string.** and complete the **Find** field.

<span id="File2"></span>

## File encoding

The source file encoding must be configured. Configuring the output file encoding is not mandatory. If it is not set, the output file encoding will be the same as the source file encoding.

### Source file encoding

Encoding of the file that will be transformed specified by the name of a {{< SecureTransport/componentshortname  >}} supported character set. The **Source file encoding:** field has an auto-complete function that lists matching {{< SecureTransport/componentshortname  >}} supported character sets.

### Output file encoding

Encoding of the file that will be produced specified by the name of a {{< SecureTransport/componentshortname  >}} supported character set. The **Output file encoding:** field has an auto-complete function that lists matching {{< SecureTransport/componentshortname  >}} supported character sets.

<span id="Post"></span>

## Post transformation action

The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to [Rename](../t_st_rename).
