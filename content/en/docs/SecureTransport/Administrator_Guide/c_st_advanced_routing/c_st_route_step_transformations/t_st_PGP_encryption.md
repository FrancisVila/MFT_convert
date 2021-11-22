{
    "title": "PGP Encryption",
    "linkTitle": "PGP Encryption",
    "weight": "220"
}The PGP Encryption transformation step enables the encryption and signing of designated files as part of a route.

Use the following procedure to add a PGP Encryption transformation step to a Route Package Template take the following steps:

1.  Designate the files to be encrypted.
2.  Determine whether or not to proceed with route execution on step failure.
3.  Select PGP settings, including encryption and signature settings.
4.  Set compression level and type.
5.  Determine whether or not to ASCII armor encode transformed files.
6.  Determine post transformation actions.

> **Note:**
>
> Steps 1 and 3 are mandatory. All other steps are optional.

> **Note:**
>
> The buffer size for PGP encryption and decryption is controlled by the Pgp.BufferSize server configuration option.

The following sections provide configuration details for the PGP Encryption transformation step:

-   <a href="#File" class="MCXref xref">Input Files</a>
-   <a href="#Proceed" class="MCXref xref">Proceed with route execution on step failure</a>
-   <a href="#PGP" class="MCXref xref">PGP Settings</a>
-   <a href="#Encryption" class="MCXref xref">Encryption Settings</a>
-   <a href="#Signature" class="MCXref xref">Signature Settings</a>
-   <a href="#Compression" class="MCXref xref">Compression Settings</a>
-   <a href="#Encode" class="MCXref xref">Encode using ASCII Armor</a>
-   <a href="#Post" class="MCXref xref">Post transformation action</a>

<span id="File"></span>

## Input Files

The *Input Files* settings consist of the selection *Process only result from preceding step* and determining the Name Filter.

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

If *Proceed with route execution on step failure* is not checked, the processing stops on the first failed file if there are several files being transformed by the step. The route execution also stops.

*Proceed with route execution on step failure* is not checked by default.

<span id="PGP"></span>

## PGP Settings

The PGP setting can be encrypt and sign, encrypt only, or sign only. If *Encrypt and sign* is selected, the files being processed by the route step are encrypted and signed. If *Encrypt only* is selected, the files being processes by the route step are encrypted but not signed. If *Sign only* is selected, the files being processed by the route step are signed but not encrypted.

By default, {{< SecureTransport/securetransportname  >}} does not allow you to use the same RSA modulus to both sign and encrypt or verify and decrypt. To allow the use of the same RSA modulus for multiple purposes, add the following Java option in &lt;`FILEDRIVEHOME>/bin/start_tm_console`:

`-Dorg.bouncycastle.rsa.allow_multi_use=true`

and restart the TM Server.

<span id="Encryption"></span>

## Encryption Settings

The encryption settings consist of selecting an account and the PGP key to use for encryption.

### Select an account

Either an account name or an Expression Language (EL) string can be specified to determine the recipient based on the environment information (such as filename).

The *Select an account* field has auto-completion which shows a list of existing accounts containing the same letter.

Once an account is selected its publicly available PGP certificates are populated in the *Select an account* field. The certificates can be public for all {{< SecureTransport/componentshortname  >}} accounts, or public for an account assigned to the same Business Unit.

If an account name is unknown (for example, expression based) its PGP certificates are determined at run time. PGP certificates can be expression based as well.

### Encrypt using PGP key

A PGP Encryption key can be selected from PGP Public Keys (within the selected account) or by entering an expression string. The access level of PGP keys is determined by the select access level. The PGP key selected access level can be private, business unit, or public.

Wild card symbols ('\*' and '?') can be used when specifying the PGP key alias (for example, `.*-pgp`). If multiple keys match the pattern the first one is picked up and used.

<span id="Signature"></span>

## Signature Settings

The signature settings consist of selecting the account and the PGP key to use for signing.

### Select an account

Either an account name or an EL string can be specified to determine the recipient based on the environment information (such as filename).

The *Select an account* field has auto-completion which shows a list of existing accounts containing the same letter.

Once an account is selected its publicly available PGP certificates are populated in the *Select an account* field. The certificates can be public for all {{< SecureTransport/componentshortname  >}} accounts, or public for an account assigned to the same Business Unit.

If an account name is unknown (for example, expression based) its PGP certificates are determined at run time. PGP certificates can be expression based as well.

### Sign using PGP key

A PGP signature key can be selected from PGP Public Keys (within the selected account) or by entering an expression string.

Wild card symbols ('\*' and '?') can be used when specifying the PGP key alias (for example, `.*-pgp`). If multiple keys match the pattern the first one is picked up and used.

<span id="Compression"></span>

## Compression Settings

The compression settings consist of selecting the type and level of compression.

### Type

The types of compression that can be selected are:

-   No Compression
-   Use Preferred
-   ZIP
-   ZLIB
-   BZIP2

### Level

The levels of compression that can be selected are:

-   Fast
-   Normal
-   Good
-   Best

<span id="Encode"></span>

## Encode using ASCII Armor

If *Encode using ASCII Armor* is checked, the files processed by the route step are ASCII armor encoded.

<span id="Post"></span>

## Post transformation action

The output file names will be the same as the input file names. To change the file names use a Rename transformation step. To configure a Rename transformation step, refer to <a href="../t_st_rename" class="MCXref xref">Rename</a>.

**Related topics:**

-   <a href="../t_st_pgp_decryption" class="MCXref xref">PGP Decryption</a>
-   <a href="../t_st_compress" class="MCXref xref">Compress</a>
-   <a href="../t_st_decompress" class="MCXref xref">Decompress</a>
-   <a href="../t_st_line_ending" class="MCXref xref">Line Ending</a>
-   <a href="../t_st_external_script" class="MCXref xref">External Script</a>
-   <a href="../t_st_charset_conversion" class="MCXref xref">Encoding Conversion</a>
-   <a href="../t_st_replace" class="MCXref xref">Characters Replace</a>
-   <a href="../t_st_line_padding" class="MCXref xref">Line Padding</a>
-   <a href="../t_st_file_folding" class="MCXref xref">Line Folding</a>
-   <a href="../t_st_line_truncating" class="MCXref xref">Line Truncating</a>
-   <a href="../t_st_rename" class="MCXref xref">Rename</a>
