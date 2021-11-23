{
    "title": "Transaction Manager",
    "linkTitle": "Transaction Manager",
    "weight": "260"
}The Transaction Manager is an event-based rules engine that provides {{< SecureTransport/componentlongname  >}} Server with extensible server-side functionality used for process automation and real-time delivery of data. This topic describes how to use the Transaction Manager to create and manage rules.

> **Note:**
>
> SecureTransport does not automatically copy changes made under the TM Settings menu to other servers in your Enterprise Cluster (EC), so you must deploy a new or changed rules package and enable or disable a rules package on all servers in the cluster. Typically you modify rules and develop applications on a development server and use export and import to deploy them after you test them.

> **Note:**
>
> Transaction Manager Administration Tool edit function is deprecated and removed for SecureTransport 5.5.

Select **Setup &gt; TM Settings** to display *TM Settings* page.

The following topics describe managing Transaction Manager rules, rules packages, and agents:

-   [Rules](c_st_rules)
-   [Built-in rules packages](r_st_builtinrulespackages)
-   [Manage rules packages](t_st_rulespackages)
-   [Create a rules package](t_st_rulespackages#CreateRulesPackage)
-   [Export a rules package](t_st_rulespackages#ExportRulesPackage)
-   [Import a rules package](t_st_rulespackages#ImportRulesPackage)
-   [Install agents or functions](t_st_installagent)
