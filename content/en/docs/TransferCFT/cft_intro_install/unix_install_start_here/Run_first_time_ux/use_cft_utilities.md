{
    "title": "Management utilities",
    "linkTitle": "Management utilities",
    "weight": "180"
}This section describes Transfer
CFT UNIX utilities located in the `cft/<installdir>/bin/`
sub-directory after completing installation.

> **Note:**
>
> In this section, the term
> Transfer CFT designates the Transfer
> CFT software package on UNIX platforms.

The utilities described here, do not replace the
basic commands described elsewhere in this document. Their purpose is
to simplify common tasks performed with {{< TransferCFT/componentshortname  >}}.

## Utility descriptions

The following utilities are detailed in this page.


|  Utility  |  Definition  |
| --- | --- |
| <a href="#cftinit">cftinit</a>  | General Transfer CFT initialization utility.  |
| <a href="#cftutil">cftutil</a>  | Simplified display of the standard CFTUTIL commands.  |
| <a href="#cftupdate">cftupdate</a>  | Management Utility updating the Transfer CFT configuration.  |
|  <a href="#cftcatal">cftcatal</a>  |  Utility migrating and/or extending the {{< TransferCFT/componentshortname  >}} catalog file.  |
|  <a href="#xfbadm">xfbadmgrp</a>  |  Group management utility (all users accessing the Transfer CFT Copilot server).  |
|  <a href="#xfbadmusr1">xfbadmusr</a>  |  Utility managing users accessing the Transfer CFT Copilot server.  |
|  <a href="#xvi">xvi</a>  |  Utility processing the conversion tables.  |
|  <a href="#Conversion_tables">atoe</a>  |  ISO 8859-1 ASCII to EBCDIC conversion table.  |
|  <a href="#Conversion_tables">etoa</a>  |  EBCDIC to ISO 8859-1 ASCII conversion table.  |


<span id="cftinit"></span>

## cftinit

*cftinit* is a general {{< TransferCFT/componentshortname  >}}
initialization utility.

**Syntax**

cftinit \[&lt;filename> \[&lt;filename>...\]\]

**Standard use**

*cftinit* is normally used with a single
parameter, which is the name of the {{< TransferCFT/componentshortname  >}} configuration file.

cftinit my\_config.cft

**Advanced use**

You can include several file names in the command line. Normally, all
{{< TransferCFT/componentshortname  >}} parameters are declared in a single file. However, for organizational
reasons, you may wish to separate the configuration into several files
(for example, a file describing the CFTPART cards and another file containing
the CFTPARM, CFTLOG cards, and so on).

cftinit partners.cft the\_rest.cft

> **Note:**
>
>  

-   If no file name
    is passed as a parameter, the program requests one or more file names.
-   If no name is supplied,
    the program stops.
-   When you run `cftinit`, it creates the catalog and communication files. You can modify the default sizes of these files to suit your requirements by updating the uconf values for `cft.cftcat.default_size` and `cft.cftcom.default_size` (these values are expressed as a number of records).

<span id="cftupdate"></span>

## cftupdate

The *cftupdate* utility is used to update the configuration.

**Syntax**

cftupdate &lt;filename> \[&lt;filename> ...\]

> **Note:**
>
>  

-   You can only update
    the CFTPART, CFTxxx (for the networks), CFTSEND cards, and so on
-   This command should
    be considered to be an alias of CFTUTIL @&lt;filename> for each file
    name passed as a parameter in the command line

<span id="cftutil"></span>

## cftutil

The *cftutil* command submits a standard CFTUTIL instruction, but
displays the results without a banner. In addition, if the command return
code is non-null, a message is displayed.

**Syntax**

cftutil &lt;command>

**Use**

```
% cftutil listcat type=z
CFTU26E LISTCAT \_ Error (TYPE Bad value for parameter)
cftutil code 115
%
```
<span id="cftcatal"></span>

## cftcatal

You can use the *cftcatal* utility to increase
the size of the {{< TransferCFT/componentshortname  >}} catalog file without losing information. In a multi-node environment, this action resizes all nodes.

**Syntax**

cftcatal

<span id="xfbadm"></span>

## xfbadmgrp

The *xfbadmgrp* utility is used
to create, delete, modify and check a group (of users) with access rights to
the Transfer CFT Copilot server. It can be used in interactive mode associated with a command
(add, delete, and so on) or in batch mode, specifying each of the required
commands (-G group –p passwd, and so on).

Syntax

Add a user group:

xfbadmgrp add \[-G &lt;group>\] \[-p &lt;passwd>\] \[-g
&lt;GID>\] \[-u &lt;users>\]

Delete a user group:

xfbadmgrp delete \[-G &lt;group>\]

Modify a user group:

xfbadmgrp modify \[-G &lt;group>\] \[-p &lt;passwd>\] \[-g
&lt;GID>\] \[-u &lt;users>\]

Display information on existing groups:

xfbadmgrp print \[-G &lt;group>\]

This command displays information on a given group (if the -G option
is used) or on all existing groups.

Standard use

xfbadmgrp  add
| delete | modify | print | check | help

Advanced use

Various options can be used to make it easier to enter information or
allow you to work in batch mode:

-   -G &lt;group>: ASCII name of the user group
-   -p &lt;passwd>: Password required to access this group
-   -g &lt;GID>: Numeric identifier of the group. If it is set to AUTO, the GID is generated
    automatically
-   -u &lt;usr1,usr2>: List of existing users, separated by a comma

<span id="xfbadmusr1"></span>

## xfbadmusr

You can use the `xfbadmusr`
utility to create, delete, check, and modify a user with access rights
to the Transfer CFT Copilot server. It can be used in interactive mode associated with
a command (add, delete, and so on) or in batch mode, specifying each of
the required commands (-G group -p passwd, and so on).

Syntax

Add a user. If the group does not exist, it is automatically created with the user
login name.

xfbadmusr add \[-l &lt;login>\] \[-p &lt;passwd>\] \[-u
&lt;UID>\] \[-g &lt;GID>\]

Delete a user. Users in the `group `file are automatically deleted from all the groups
with which they are associated.

xfbadmusr delete \[-l &lt;login>\]

Modify a user. If necessary, modifications are applied automatically to the `group `file.

xfbadmusr modify \[-l &lt;login>\] \[-p &lt;passwd>\] \[-u
&lt;UID>\] \[-g &lt;GID>\]

Check a user.

xfbadmusr check \[-l &lt;login\] \[-p passwd\]

Display information on existing users. Display information on a given user (if the -l option
is used) or on all existing users.

xfbadmusr print \[-l &lt;login>\]:

Standard use

xfbadmusr add | delete | modify | print | check | help

Advanced use

You can use the following options to make it easier to enter information,
or to work in batch mode:

-   **-l
    &lt; login >**: Login name
-   <span style="font-weight: bold;font-family: 'Courier New', monospace;">-p
    &lt; passwd ></span>: Password
-   <span style="font-weight: bold;font-family: 'Courier New', monospace;">-u
    &lt; UID ></span>: User identifier - When set to AUTO, a UID is generated
    automatically
-   <span style="font-weight: bold;font-family: 'Courier New', monospace;">-g
    &lt; GID ></span>: Group identifier - When set to AUTO, the GID is
    generated automatically

Example

```
xfbadmusr add -l user1 -p thepassword -u AUTO -g AUTO
```

To check that the user1 is created, run:

```
xfbadmusr print
```

The output should resemble the following:

```
user1:$6$2clPU2CY..2clPU2$g0cm8rHz8X0Fvu1lz7TUVa2YfpPMkbs03wQWhd5f0IMEWDbCQHK9IumSObNF4voLEM/BlsSdNMlw1k01iPOdv0:106:106:::
```
<span id="xvi"></span>

## xvi

The *xvi* utility is used to update a conversion table.

**Syntax**

xvi \[-d | -a | -e | -l
&lt;file> \] &lt;table>

Standard use

xvi &lt;table>: updates an existing, valid &lt;table> (256 characters).

**Advanced use**

The following options can be used with *xvi*:

-   -d: displays an existing, valid &lt;table>
    in ASCII
-   -a: creates a &lt;table> to convert
    ASCII to EBCDIC; this table is identical to the one accessed via the Transfer
    CFT CFTXLATE command (if &lt;table> exists, it is overwritten)
-   -e: creates a &lt;table> to convert
    EBCDIC to ASCII; this table is identical to the one accessed via the Transfer
    CFT CFTXLATE command (if &lt;table> exists, it is overwritten)
-   -l:
    creates a &lt;table> from an ASCII &lt;file>; the file generally
    used is the file produced after running option -d (if &lt;table> exists,
    it is overwritten)

<span id="Conversion_tables"></span>

## Conversion tables

By default, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> uses internal tables to convert ASCII characters
to EBCDIC and vice versa. They are based on the ASCII character set as
defined on PC/DOS systems.

To perform a conversion using the ISO 8859-1
ASCII character set, run the CFTXLATE command with the
following external conversion tables:

-   atoe:
    ISO 8859-1 ASCII to EBCDIC
-   etoa:
    EBCDIC to ISO 8859-1 ASCII

You can use the [xvi](#xvi) utility, described above,
to create specific conversion tables or modify existing tables.
