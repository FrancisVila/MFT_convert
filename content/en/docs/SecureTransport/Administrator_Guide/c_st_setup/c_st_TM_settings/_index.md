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

-   <a href="c_st_rules" class="MCXref xref">Rules</a>
-   <a href="r_st_builtinrulespackages" class="MCXref xref">Built-in rules packages</a>
-   <a href="t_st_rulespackages" class="MCXref xref">Manage rules packages</a>
-   <a href="t_st_rulespackages#CreateRulesPackage" class="MCXref xref">Create a rules package</a>
-   <a href="t_st_rulespackages#ExportRulesPackage" class="MCXref xref">Export a rules package</a>
-   <a href="t_st_rulespackages#ImportRulesPackage" class="MCXref xref">Import a rules package</a>
-   <a href="t_st_installagent" class="MCXref xref">Install agents or functions</a>
