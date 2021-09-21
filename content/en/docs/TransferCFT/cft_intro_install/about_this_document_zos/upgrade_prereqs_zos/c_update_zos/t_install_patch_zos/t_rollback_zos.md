{
    "title": "Rollback a service pack or patch (non-SMP/E)",
    "linkTitle": "Rollback a service pack or patch (non-SMP/E)",
    "weight": "260"
}The following procedure enables you to rollback after applying a SP or patch to its previous state. This is useful in the case of an incident during the application of a PTF, or when testing the patch validation.

## Use the A13RBACK

Use the A13RBACK to restore the executable file library, USS Copilot and USS Secure Relay environment. This JCL executes the following three JCLs:

-   A13RSTOR: Restores the Transfer CFT Load library.
-   A13UCOPR: Restores the Transfer CFT USS Copilot environment.
-   A13UXSRR: Restores the Transfer CFT USS Secure Relay environment.

Before submitting the JOB configure the following JCL in automatic mode:

..INSTALL(A13RSTOR) &gt;&gt; ID='AUTO'

..INSTALL(A13SDEL) &gt;&gt; ID='AUTO'

..INSTALL(A13UCOPR) &gt;&gt; ID='AUTO'

..INSTALL(A13UCOPD) &gt;&gt; ID='AUTO'

..INSTALL(A13UXSRR) &gt;&gt; ID='AUTO'

..INSTALL(A13UXSRD) &gt;&gt; ID='AUTO'

-   Stop Transfer CFT and Copilot.
-   Set the parameter 'ID' with the last six characters of the patch id. For example, 0E0500 for the patch id CF0E0500.
-   Submit the JCL.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This operation is displayed in the distlib.LOG file.         </td>
      </tr>
</table>