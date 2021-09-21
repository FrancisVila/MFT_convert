{
    "title": "Silent installation",
    "linkTitle": "Silent installation",
    "weight": "200"
}1.  Log in with the **CFTINST** user (with \*ALLOBJ special authority).
2.  Select 1.
3.  Install Transfer CFT. The following example installs Transfer CFT with the Central Governance option:

## Register with Central Governance

1.  Log in with the Transfer CFT user **CFT**.
2.  Start Copilot.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFT Update (UPDATE)</p>
            <p>Type choices, press Enter.</p>
            <p>Install on an independent ASP .  &gt; 2        1:Yes/2:No</p>
            <p>Silent Installation . . . . . .  &gt;   1        1:Yes/2:No</p>
            <p>CFT Program library  . . . . . .    &gt; CFTPGM   Name</p>
            <p>CFT Production library . . . . . &gt;    CFTPROD  Name</p>
            <p>User for who CFT is installed .  &gt; CFT      Character value</p>
            <p>CFT JOBD  .......................     &gt; CFTJOBD  Name</p>
            <p>CFT JOBQ  .......................     &gt; CFTJOBQ  Name</p>
            <p>CFT Subsystem ..................     &gt; CFTSBS   Name</p>
            <p>CFT Class ......................     &gt; CFTCLS   Name</p>
            <p>CFT Outq .......................     &gt; CFTOUTQ  Name</p>
            <p>Encryption Password</p>
            <p> </p>
            <p>Confirm Encryption password</p>
            <p> </p>
            <p>Key file name ........... &gt; CRYPTKEY     Character value</p>
            <p>Salt file name .......... &gt; CRYPTSALT    Character value</p>
         </td>
      </tr>
   </tbody>
</table>

1.  Check that the Transfer CFT instance appears in Central Governance.

You can now operate your Transfer CFT instance with the **CFT** user.

After executing the installation, the following objects are created in the CFTPROD library:

-   Files: CAT, COM, LOG, ALOG, ACCNT, AACCNT
-   System objects: CFTJOBQ, CFTJOBD, CFTSBS, CFTCLS, CFTOUTQ
