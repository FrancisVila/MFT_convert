{
    "title": "class",
    "linkTitle": "class",
    "weight": "400"
}<span id="class"></span>

### class

#### CFTNET

**\[CLASS = n\]  **{<span style="text-decoration: underline;">1</span>..32}

Class of the local resource used to establish a connection with a partner. Class associated with this network resource.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>You cannot define two CFTNETs that have the same CLASS value.         </td>
      </tr>
   </tbody>
</table>

#### CFTTCP

**\[CLASS = {<span style="text-decoration: underline;">1</span>
| n}\]    ** {1 .. 32}

Logical class of the physical link. The maximum is operating system dependent
and equal to NM\_MAX\_CLASS.

Recommended maximum values are:

-   Windows NT - 64
-   UNIX - 8
-   MVS - 32

[Return to Command index](../../)