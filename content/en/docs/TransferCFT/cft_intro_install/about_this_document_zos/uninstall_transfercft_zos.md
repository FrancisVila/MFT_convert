{
    "title": "Uninstall Transfer CFT ",
    "linkTitle": "Uninstall",
    "weight": "190"
}This section describes how to uninstall Transfer CFT in a z/OS environment.

If you uninstall a Transfer CFT, you will lose the entire Transfer CFT
configuration. To avoid this, you must save your environment prior removing the Transfer CFT.

### Procedure

Before uninstalling, you must stop the servers you want to uninstall (including Copilot).

Run the UNINSTAL JCL, which:

1.  Removes all files from the INSTANCE, including multi-node, except for the JCL library (target.INSTALL).
2.  Removes sub-USS directories, Copilot, and Secure Relay.
3.  Removes the distribution environment.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You must manually modify the JCL, by default the distribution environment is not removed (see lines 000018, 000081, and 000082 in the example).         </td>
      </tr>
   </tbody>
</table>

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>000014 //* 2 phases in this JCL:</p>
            <p>000015 //* --------------------</p>
            <p>000016 //* Phase 1 - Delete Transfer CFT instance env.</p>
            <p>000017 //* Phase 2 - Delete Transfer CFT distribution env.</p>
            <p>000018 //</p>
            <p>000019 //</p>
            <p>000020 //* Phase 1 - Delete Transfer CFT instance env.</p>
            <p>000021 //* ------------------------------------------</p>
            <p>000022 //* INSTALL library is not deleted.</p>
            <p>000023 //IN01 EXEC PREXX,PARM='%RXDEL &amp;CFTENV..USER.OBJ 0'</p>
            <p>000024 //IN02 EXEC PREXX,PARM='%RXDEL &amp;CFTENV..SAMPLE 0'</p>
            <p>…[continued]…</p>
            <p>000085 //</p>
            <p>000086 //</p>
            <p>000087 //* --------------------------------------------------</p>
            <p>000088 //* Phase 2 - Delete Transfer CFT distribution env.</p>
            <p>000089 //* --------------------------------------------------</p>
            <p>000090 //DI03 EXEC PREXX,PARM='%RXDEL &amp;DISTLIB..CNTL 0'</p>
            <p>000091 //DI04 EXEC PREXX,PARM='%RXDEL &amp;DISTLIB..DOC 0'</p>
            <p>000092 //DI05 EXEC PREXX,PARM='%RXDEL &amp;DISTLIB..SAMPLE 0'</p>
            <p>000093 //DI06 EXEC PREXX,PARM='%RXDEL &amp;DISTLIB..LOG 0'</p>
            <p>000094 //DI07 EXEC PREXX,PARM='%RXDEL &amp;DISTLIB..MAC 0'</p>
            <p>…[continued]…</p>         </td>
      </tr>
   </tbody>
</table>
