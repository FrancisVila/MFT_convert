{
    "title": " Suspend or quit CFTUTIL",
    "linkTitle": "Suspend CFTUTIL",
    "weight": "280"
}## WAIT

<span id="About_the_WAIT_Command"></span>Use this command to suspend the execution of CFTUTIL for
the time indicated.

Command syntax: [WAIT](../)

**Parameters**

**\[DURING = {<u>0</u> | n}\]**

{0..65535}

Time in seconds that CFTUTIL is deactivated.

## EXIT

The command EXIT quits the CFTUTIL program.

Command syntax: EXIT

**Parameters**

**\[exitcode = {<u>0</u> | n}\]**

By default there is a code that displays when you use the EXIT command to quit CFTUTIL. However, you can use the exitcode parameter to define a specific exit code, which replaces the default value.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>&gt;CFTUTIL EXIT EXITCODE=3</p>
            <p> </p>
            <p>EXIT EXITCODE=3</p>
            <p>CFTU00I EXIT _ Correct (EXITCODE=3)</p>         </td>
      </tr>
   </tbody>
</table>
