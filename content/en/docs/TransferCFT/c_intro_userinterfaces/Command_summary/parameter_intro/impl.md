{
    "title": "impl",
    "linkTitle": "impl",
    "weight": "1660"
}<span id="impl"></span>

### impl

#### CFTSEND

**\[IMPL  = { NO
| YES}\]**

Implicit send.

When <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> operates in sender server mode and there is no SEND
command (state=HOLD) entered in the catalog for this file identifier,
the IMPL parameter set to "YES" allows the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to make available the corresponding file, by automatically generating
a send request. This makes a file permanently available.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>If the RECV command specifies an IDF in “identifier” form (no mask) and if the corresponding model files, at the server end, are declared in implicit send mode (IMPL = YES), the option FILE = ALL initiates an uninterrupted repetition of the transfer, concerning the first file waiting to be sent.         </td>
      </tr>
   </tbody>
</table>

For the default model file,
set this parameter to NO. You can define two
CFTSEND objects with the same ID, with impl
= NO for one and impl = YES
for the other. Do this when the IDF is going to be used for implicit
send rather than explicit send.

[Return to Command index](../../)