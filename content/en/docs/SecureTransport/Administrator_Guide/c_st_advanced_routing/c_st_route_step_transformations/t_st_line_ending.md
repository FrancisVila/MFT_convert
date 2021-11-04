{
    "title": "Line Ending",
    "linkTitle": "Line Ending",
    "weight": "260"
}The Line Ending transformation step enables converting line ending formats as part of a route.

> **Note:**
>
> Currently, the Line Ending transformation accepts Unicode or ASCII as an input, or mixed input when the custom line ending format is selected.

> **Note:**
>
> If the encoding a file is changed to IBM500, IBM037, or IBM424; the line ending of the input file should be LF and not CRLF. The CR is preserved in some cases and a new line appears between every original line.

To add a Line Ending transformation step to a Route Package Template take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Select source file setting options.
4.  Select target file setting options.
5.  Determine post transformation actions.

> **Note:**
>
> Steps 1, 3, and 4 are mandatory. All other steps are optional.

The following topics provide configuration details for the Line Ending transformation step:

-   <a href="#Input" class="MCXref xref">Input Files</a>
-   <a href="#Proceed" class="MCXref xref">Proceed with route execution on step failure</a>
-   <a href="#Source" class="MCXref xref">Source file settings</a>
-   <a href="#Target" class="MCXref xref">Target file settings</a>
-   <a href="#Post" class="MCXref xref">Post transformation action</a>

**Related topics:**

-   <a href="../t_st_pgp_encryption" class="MCXref xref">PGP Encryption</a>
-   <a href="../t_st_pgp_decryption" class="MCXref xref">PGP Decryption</a>
-   <a href="../t_st_compress" class="MCXref xref">Compress</a>
-   <a href="../t_st_decompress" class="MCXref xref">Decompress</a>
-   <a href="../t_st_external_script" class="MCXref xref">External Script</a>

<!-- -->

-   <a href="../t_st_charset_conversion" class="MCXref xref">Encoding Conversion</a>
-   <a href="../t_st_replace" class="MCXref xref">Characters Replace</a>
-   <a href="../t_st_line_padding" class="MCXref xref">Line Padding</a>
-   <a href="../t_st_file_folding" class="MCXref xref">Line Folding</a>
-   <a href="../t_st_line_truncating" class="MCXref xref">Line Truncating</a>
-   <a href="../t_st_rename" class="MCXref xref">Rename</a>

<span id="Input"></span>

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

<span id="Source"></span>

## Source file settings

The source file settings consists of selecting a source file line ending format and encoding.

### Line ending format

The selectable line ending formats are:

-   Windows (CR + LF)
-   Unix (LF)
-   Custom

If *Custom* is selected, specify line ending characters in ASCII or Unicode format (\\uXXXX). The hex encoded value of the line ending is any character `\n`, `\r`, and the combination of both. The custom line ending char in Unicode notation:

-   Windows:

    `\u000d\u000a`

-   \*nix, MacOS:

    `\u000a`

-   Mainframe:

    `\u0025`

### File encoding

The file encoding format can be selected from a long list of available formats. Start typing the desired file encoding format in the field and select the desired file encoding format from the list. For a supported list of source and target encodings, refer to [Java SE 11 Documentation](https://docs.oracle.com/en/java/javase/11/intl/supported-encodings.html#GUID-187BA718-195F-4C39-B0D5-F3FDF02C7205).

<span id="Target"></span>

## Target file settings

The target file settings consists of selecting a target file line ending format and encoding.

### Line ending format

The selectable line ending formats are:

-   Windows (CR + LF)
-   Unix (LF)
-   Custom

If *Custom* is selected, the hex encoded value of the line ending character must be specified. The hex encoded value of the line ending is any character `\n`, `\r` combination of both. The custom line ending char in Unicode notation:

-   Windows:

    `\u000d\u000a`

-   \*nix, MacOS:

    `\u000a`

-   Mainframe:

    `\u0025`

### File encoding

The file encoding format can be selected from a long list of available formats. Start typing the desired file encoding format in the field and select the desired file encoding format from the list.

<span id="Post"></span>

## Post transformation action

The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to <a href="../t_st_rename" class="MCXref xref">Rename</a>.
