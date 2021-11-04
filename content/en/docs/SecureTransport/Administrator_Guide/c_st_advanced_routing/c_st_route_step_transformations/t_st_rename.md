{
    "title": "Rename",
    "linkTitle": "Rename",
    "weight": "330"
}The Rename transformation step enables the renaming of a designated file or files as part of a route. To add a Rename transformation step to a Route Package Template take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Determine output file names.

> **Note:**
>
> Step 1 and 3 are mandatory. Step 2 is optional.

The following topics provide configuration details for the Rename transformation step:

-   <a href="#File" class="MCXref xref">Input Files</a>
-   <a href="#Proceed" class="MCXref xref">Proceed with route execution on step failure</a>
-   <a href="#Rename" class="MCXref xref">Rename settings</a>

**Related topics:**

-   <a href="../t_st_pgp_encryption" class="MCXref xref">PGP Encryption</a>
-   <a href="../t_st_pgp_decryption" class="MCXref xref">PGP Decryption</a>
-   <a href="../t_st_compress" class="MCXref xref">Compress</a>
-   <a href="../t_st_decompress" class="MCXref xref">Decompress</a>
-   <a href="../t_st_line_ending" class="MCXref xref">Line Ending</a>
-   <a href="../t_st_external_script" class="MCXref xref">External Script</a>
-   <a href="../t_st_charset_conversion" class="MCXref xref">Encoding Conversion</a>
-   <a href="../t_st_replace" class="MCXref xref">Characters Replace</a>
-   <a href="../t_st_line_padding" class="MCXref xref">Line Padding</a>
-   <a href="../t_st_line_truncating" class="MCXref xref">Line Truncating</a>
-   <a href="../t_st_file_folding" class="MCXref xref">Line Folding</a>

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

The Name Filter can either be set to process all files forwarded by the selection of *Process only result from preceding step* or process files based on a designated filename pattern forwarded by the selection of *Process only result from preceding step*. If *Process all files* is selected, all files forwarded by the selection of *Process only result from preceding step* are processed. If *Process files based on a filename pattern* is selected, only the files that match the file globbing or regular expression pattern are processed.

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

<span id="Rename"></span>

## Rename settings

The rename settings determine the naming of the output file or files.

### Output file names

The output file or files are renamed according to the expression entered in the *Output File Names* field. All input files are renamed based on the configured expression.

Examples:

-   New filename based on the current filename:
    -   `${basename(currentfulltarget)}.transformed`
-   New filename bases on the original filename with a timestamp:
    -   `${basename(currentfulltarget)}​.${timestamp}​.${extension(currentfulltarget)}`

The path of the new file (if any) will be stripped off and only the filename will be left.
