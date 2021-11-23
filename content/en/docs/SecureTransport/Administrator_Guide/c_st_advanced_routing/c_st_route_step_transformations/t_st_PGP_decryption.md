{
    "title": "PGP Decryption",
    "linkTitle": "PGP Decryption",
    "weight": "230"
}The PGP Decryption transformation step enables the decryption and signature verification of designated files as part of a route. To add a PGP Decryption transformation step to a Route Package Template take the following steps:

1.  Designate file filtering.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Select decryption settings.
4.  Determine post transformation actions.

> **Note:**
>
> Step 1 is mandatory. All other steps are optional.

> **Note:**
>
> The buffer size for PGP encryption and decryption is controlled by the Pgp.BufferSize server configuration option.

The following topics provide configuration details for the PGP Decryption transformation step:

-   [Input Files](#Input)
-   [Proceed with route execution on failure](#Proceed)
-   [Decryption Settings](#Decryption)
-   [Post transformation action](#Post)

**Related topics:**

-   [PGP Encryption](../t_st_pgp_encryption)
-   [Compress](../t_st_compress)
-   [Decompress](../t_st_decompress)
-   [Line Ending](../t_st_line_ending)
-   [External Script](../t_st_external_script)

<!-- -->

-   [Encoding Conversion](../t_st_charset_conversion)
-   [Characters Replace](../t_st_replace)
-   [Line Padding](../t_st_line_padding)
-   [Line Folding](../t_st_file_folding)
-   [Line Truncating](../t_st_line_truncating)
-   [Rename](../t_st_rename)

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

## Proceed with route execution on failure

If *Proceed with route execution on step failure* is checked, the route execution continues even if the step execution fails.

If *Proceed with route execution on step failure* is not checked, the processing stops on the first failed file if there are several files being transformed by the step. The route execution also stops.

*Proceed with route execution on step failure* is not checked by default.

<span id="Decryption"></span>

## Decryption Settings

The two selections for decryption settings are:

-   Require Trusted Signature
-   Require Encryption

PGP private keys are automatically determined on runtime.

> **Note:**
>
> PGP private and public keys are only searched for within the key store of the account subscribed to this route.

### Require Trusted Signature

If *Require Trusted Signature* is selected, the transformation of the designated file or files requires a PGP partner key for signature verification. If a signature is required, but the file is not signed, the signature verification fails. If encryption is required but the file is not encrypted, the PGP Decryption fails. If both trusted signature and encryption are required but the file is neither encrypted or signed, the decryption fails. PGP Decryption step also fails if there is a problem with the certificate selected (not valid, expired, not signed, and so forth).

### Require Encryption

If *Require Encryption* is selected, the transformation of the designated file or files requires a PGP private key for decryption.

<span id="Post"></span>

## Post transformation action

The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to [Rename](../t_st_rename).
