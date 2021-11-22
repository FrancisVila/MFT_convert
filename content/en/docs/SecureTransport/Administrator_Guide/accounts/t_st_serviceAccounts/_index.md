{
    "title": "Manage service accounts",
    "linkTitle": "Manage service accounts",
    "weight": "190"
}Service accounts are internal accounts used for representing internal systems, as opposed to partner sites that are identified in {{< SecureTransport/componentshortname  >}} by user accounts.

> **Note:**
>
> The Login Threshold Maintenance application does not function with service accounts.

Service accounts are defined and managed in the same way as user accounts, with the following exceptions and distinctions that you must consider when working with user accounts:

-   The account settings, per-account transfer sites definition, and per-partner certificates are defined and managed identically to those of user accounts.
-   Service accounts do not subscribe to applications using subscriptions. The functional connection between a service account and an application is called a *connector* and is defined at the application level. For this reason, the *Service Accounts* page does not contain a **Subscriptions** tab.
-   Service accounts are internal to the system, and user accounts are external to the system.

The following topic describes how to export a single service account:

-   <a href="t_st_export_single_service_account" class="MCXref xref">Export a single service account</a> - Provides how-to instructions for exporting a single service account.
