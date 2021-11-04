{
    "title": "Uninstall product",
    "linkTitle": "Uninstall product",
    "weight": "130"
}This section describes how to uninstall a product.

## Windows installations

The same user (or at least the same type of user) who performed the initial installation must start the installer.

## Services modification

Some products support an installation in service mode with a user other than the default (local system account).

If the domain field is not shown in the product's service configuration dialog, then it must be introduced in the user name field, using this format:

`<domain>\<user name>`

If it is a local user (a user that was created on the local machine) the `<domain>` field can be . or the `<hostname>`.

### Example

`Local user: user1`

`.\user1`

`<hostname>\user1`

`Network user: user2`

`<domain_name>\user2`

## Use the Uninstall function

Before you begin uninstalling, you must stop the servers you want to uninstall.

You can uninstall products in GUI or console mode. The command to use depends on your operating system.

If products were installed on Windows in service mode, the installer removes the service.

### GUI mode

-   UNIX/Linux: `uninstall.sh –m gui`
-   Windows:In the Windows **Start** menu, select  
    Axway Software > Axway \[installation name\] > Uninstall

### Console mode

-   UNIX/Linux: `uninstall.sh –m console`
-   Windows: `uninstall32.exe –m console` or `uninstall64.exe –m console`
