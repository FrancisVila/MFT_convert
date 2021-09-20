{
    "title": "Transaction Manager",
    "linkTitle": "Transaction Manager",
    "weight": "270"
}The Transaction Manager is an event-based rules engine that provides Axway SecureTransport Server with extensible server-side functionality used for process automation and real-time delivery of data. This topic describes how to use the Transaction Manager to create and manage rules.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> does not automatically copy changes made under the <strong>TM Settings</strong> menu to other servers in your Enterprise Cluster (EC), so you must deploy a new or changed rules package and enable or disable a rules package on all servers in the cluster. Typically you modify rules and develop applications on a development server and use export and import to deploy them after you test them.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Transaction Manager Administration Tool edit function is deprecated and removed for <span>SecureTransport</span> <span>5.5</span>.         </td>
      </tr>
</table>

Select **Setup &gt; TM Settings** to display *TM Settings* page.

The following topics describe managing Transaction Manager rules, rules packages, and agents:

-   [Rules](c_st_rules)
-   [Built-in rules packages](r_st_builtinrulespackages)
-   [Manage rules packages](t_st_rulespackages)
-   [Create a rules package](t_st_rulespackages)
-   [Export a rules package](t_st_rulespackages)
-   [Import a rules package](t_st_rulespackages)
-   [Install agents or functions](t_st_installagent)
