{
    "title": "class",
    "linkTitle": "class",
    "weight": "430"
}### <span id="class"></span>class

#### CFTNET

**\[CLASS = n\]  **{1..32}

Class of the local resource used to establish a connection with a partner. Class associated with this network resource.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You cannot define two CFTNETs that have the same CLASS value.         </td>
      </tr>
   </tbody>
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

[Return to Command index](../)
