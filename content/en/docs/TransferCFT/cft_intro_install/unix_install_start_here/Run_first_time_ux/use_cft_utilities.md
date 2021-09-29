{
    "title": "Management utilities",
    "linkTitle": "Management utilities",
    "weight": "190"
}This section describes Transfer
CFT UNIX utilities located in the cft/&lt;installdir>/bin/
sub-directory after completing installation.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In this section, the term
<span>Transfer CFT</span> designates the Transfer
CFT software package on UNIX platforms.</td>
</tr>
</tbody>
</table>

The utilities described here, do not replace the
basic commands described elsewhere in this document. Their purpose is
to simplify common tasks performed with Transfer CFT.

## Utility descriptions

The following utilities are detailed in this page.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Utility  </p></th>
<th><p>Definition  </p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="#cftinit">cftinit</a></td>
<td>General Transfer CFT initialization utility.</td>
</tr>
<tr class="even">
<td><a href="#cftutil">cftutil</a></td>
<td>Simplified display of the standard CFTUTIL commands.</td>
</tr>
<tr class="odd">
<td><a href="#cftupdate">cftupdate</a></td>
<td>Management Utility updating the Transfer CFT configuration.</td>
</tr>
<tr class="even">
<td><p><a href="#cftcatal">cftcatal</a>  </p></td>
<td><p>Utility migrating and/or extending the <span>Transfer CFT</span> catalog
file.  </p></td>
</tr>
<tr class="odd">
<td><p><a href="#xfbadm">xfbadmgrp</a>  </p></td>
<td><p>Group management utility (all users accessing the Transfer CFT Copilot server).  </p></td>
</tr>
<tr class="even">
<td><p><a href="#xfbadmusr1">xfbadmusr</a>  </p></td>
<td><p>Utility managing users accessing the Transfer CFT Copilot server.  </p></td>
</tr>
<tr class="odd">
<td><p><a href="#xvi">xvi</a>  </p></td>
<td><p>Utility processing the conversion tables.  </p></td>
</tr>
<tr class="even">
<td><p><a href="#conversion_tables">atoe</a>  </p></td>
<td><p>ISO 8859-1 ASCII to EBCDIC conversion table.  </p></td>
</tr>
<tr class="odd">
<td><p><a href="#conversion_tables">etoa</a>  </p></td>
<td><p>EBCDIC to ISO 8859-1 ASCII conversion table.  </p></td>
</tr>
</tbody>
</table>

## <span id="cftinit"></span>cftinit

*cftinit* is a general Transfer CFT
initialization utility.

**Syntax**

cftinit \[&lt;filename> \[&lt;filename>...\]\]

**Standard use**

*cftinit* is normally used with a single
parameter, which is the name of the Transfer CFT configuration file.

cftinit my\_config.cft

**Advanced use**

You can include several file names in the command line. Normally, all
Transfer CFT parameters are declared in a single file. However, for organizational
reasons, you may wish to separate the configuration into several files
(for example, a file describing the CFTPART cards and another file containing
the CFTPARM, CFTLOG cards, and so on).

cftinit partners.cft the\_rest.cft

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top"> </td>
</tr>
</tbody>
</table>

-   If no file name
    is passed as a parameter, the program requests one or more file names.
-   If no name is supplied,
    the program stops.
-   When you run cftinit, it creates the catalog and communication files. You can modify the default sizes of these files to suit your requirements by updating the uconf values for cft.cftcat.default\_size and cft.cftcom.default\_size (these values are expressed as a number of records).

## <span id="cftupdate"></span>cftupdate

The *cftupdate* utility is used to update the configuration.

**Syntax**

cftupdate &lt;filename> \[&lt;filename> ...\]

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top"> </td>
</tr>
</tbody>
</table>

-   You can only update
    the CFTPART, CFTxxx (for the networks), CFTSEND cards, and so on
-   This command should
    be considered to be an alias of CFTUTIL @&lt;filename> for each file
    name passed as a parameter in the command line

## <span id="cftutil"></span>cftutil

The *cftutil* command submits a standard CFTUTIL instruction, but
displays the results without a banner. In addition, if the command return
code is non-null, a message is displayed.

**Syntax**

cftutil &lt;command>

**Use**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>% cftutil listcat type=z<br />
CFTU26E LISTCAT _ Error (TYPE Bad value for parameter)<br />
cftutil code 115<br />
%</td>
</tr>
</tbody>
</table>

## <span id="cftcatal"></span>cftcatal

You can use the *cftcatal* utility to increase
the size of the Transfer CFT catalog file without losing information. In a multi-node environment, this action resizes all nodes.

**Syntax**

cftcatal

## <span id="xfbadm"></span>xfbadmgrp

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

## <span id="xfbadmusr1"></span>xfbadmusr

You can use the xfbadmusr
utility to create, delete, check, and modify a user with access rights
to the Transfer CFT Copilot server. It can be used in interactive mode associated with
a command (add, delete, and so on) or in batch mode, specifying each of
the required commands (-G group -p passwd, and so on).

Syntax

Add a user. If the group does not exist, it is automatically created with the user
login name.

xfbadmusr add \[-l &lt;login>\] \[-p &lt;passwd>\] \[-u
&lt;UID>\] \[-g &lt;GID>\]

Delete a user. Users in the group file are automatically deleted from all the groups
with which they are associated.

xfbadmusr delete \[-l &lt;login>\]

Modify a user. If necessary, modifications are applied automatically to the group file.

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

-   -l
    &lt; login >: Login name
-   -p
    &lt; passwd >: Password
-   -u
    &lt; UID >: User identifier - When set to AUTO, a UID is generated
    automatically
-   -g
    &lt; GID >: Group identifier - When set to AUTO, the GID is
    generated automatically

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>xfbadmusr add -l user1 -p thepassword -u AUTO -g AUTO</p></td>
</tr>
</tbody>
</table>

To check that the user1 is created, run:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>xfbadmusr print</p></td>
</tr>
</tbody>
</table>

The output should resemble the following:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>user1:$6$2clPU2CY..2clPU2$g0cm8rHz8X0Fvu1lz7TUVa2YfpPMkbs03wQWhd5f0IMEWDbCQHK9IumSObNF4voLEM/BlsSdNMlw1k01iPOdv0:106:106:::</p></td>
</tr>
</tbody>
</table>

## <span id="xvi"></span>xvi

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

## <span id="Conversion_tables"></span>Conversion tables

By default, Transfer CFT uses internal tables to convert ASCII characters
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
