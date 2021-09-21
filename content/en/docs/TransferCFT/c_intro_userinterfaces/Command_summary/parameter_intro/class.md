{
    "title": "class",
    "linkTitle": "class",
    "weight": "430"
}### <span id="class"></span>class

#### CFTNET

**\[CLASS = n\]  **{1..32}

Class of the local resource used to establish a connection with a partner. Class associated with this network resource.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot define two CFTNETs that have the same CLASS value.         </td>
      </tr>
</table>

#### CFTTCP

**\[CLASS = {1
| n}\]    ** {1 .. 32}

Logical class of the physical link. The maximum is operating system dependent
and equal to NM\_MAX\_CLASS.

Recommended maximum values are:

-   Windows NT - 64
-   UNIX - 8
-   MVS - 32

[Return to Command index](../../)
