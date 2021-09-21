{
    "title": "part",
    "linkTitle": "part",
    "weight": "2560"
}### <span id="part"></span>part

Enter the local identifier for the site where Transfer CFT runs. This
parameter is used in the catalog for information purposes only.

#### CFTDEST

**PART = (*identifier, identifier*,
...)**

Explicit list of the identifiers
of the various partners (each corresponding to one value of the ID parameter
of a CFTPART command).

The maximum number of identifiers in this list is limited to 200.

If no partner is defined in CFTPART, no transfer either broadcasting
or collection, is performed.

#### LISTPARM

**\[PART = *identifier*\]**

**F**or TYPE = IDF

Partner identifier.

Used to limit the search to the IDFs defined in the CFTIDF commands,
relative to this partner.

#### LISTCAT

**\[PART = { *identifier | mask }*
\]**

Identifier of the partner(s) for the selected transfers.

The value of this parameter can be:

-   An identifier: the selection only relates
    to the transfers performed with this partner
-   A mask: the selection relates to the
    transfers with the partners whose identifier corresponds to this mask
-   Omitted: the selection relates to all
    partners. This option is the same as the option PART = \*

If the NPART parameter is defined, the PART parameter is ignored.

#### SEND, RECV

**\[PART = *identifier*\]**

**The
id of the partner responsible for the transfer.**

When sending a reply, this identifier designates
the file sender. If the command is used in an end-of-receive procedure,
the user can define this parameter using the symbolic variable PART=&PART.

This identifier designates:

-   either a partner described by the command:
    <table cellspacing="0" width="90%">   <col/>   <col/>   <col/>      <tr>         <td width="12%">            <p>CFTPART</p>         </td>         <td width="49.131%">            <p>ID = &lt;PART parameter value&gt;, ...</p>         </td>         <td width="35.224%">            <p> </p>         </td>      </tr></table>

<!-- -->

-   or a list of partners described by
    the command:
    <table cellspacing="0" width="90%">   <col/>   <col/>   <col/>      <tr>         <td width="12%">            <p>CFTDEST</p>         </td>         <td width="55.61%">            <p>ID = &lt;PART parameter value&gt;,</p>         </td>         <td width="28.746%">            <p> </p>         </td>      </tr>      <tr>         <td width="12%">            <p> </p>         </td>         <td width="55.61%">            <p>PART = (<i>identifier, identifier . . .</i>)</p>         </td>         <td width="28.746%">            <p> </p>         </td>      </tr></table>

#### CFTIDF

**\[PART = *identifier*\]**

**Local
identifier of the partner for which the IDF/NIDF correspondence is valid.
**

**This
parameter is an informational item that appears in the catalog.**

#### **C**FTPARM

**\[PART = *= *string64**\]**

**Local
identifier, identifying the site on which Transfer CFT is executed.  **

**The
same value as the CFTPART ID parameter value.**

#### RESUME, DELETE, HALT, KEEP, START, END, SUBMIT

**PART = { *identifier | mask }***

Partner identifier.

The associated value of this parameter can be:

-   An
    identifier: the command only concerns transfers with this partner site
-   A mask:
    the command concerns transfers with partner sites, for which the identifiers
    correspond to this mask

#### DISPLAY

**\[PART = string\]**

#### KSTATE

**\[PART = partner *identifier*\]**

#### CFTIDF

**\[PART = *identifier*\]**

#### TURN

**\[PART = *identifier*\]**

#### CFTPROT (DMZ)

**\[PART = {*identifier, identifier,...}*\]**

 

[Return to Command index](../../)