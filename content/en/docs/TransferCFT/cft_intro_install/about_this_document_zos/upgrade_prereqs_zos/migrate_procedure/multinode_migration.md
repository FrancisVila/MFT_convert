{
    "title": "Migrate a multi-node architecture",
    "linkTitle": "Multi-node migration",
    "weight": "250"
}This section describes the upgrade of an instance of Transfer CFT z /OS configured in multi-node. Perform the sames steps as in the [non multi-node environment](../), with the only difference being the MIGRCAT, MIGRCOM and PMIGR2 procedures as described in the following sections.

## Migrate the CATALOG files (MIGRCAT)

The MIGRCAT procedure migrates one catalog file at a time. The procedure must be modified and executed for each of the nodes.

Customize the PMIGR2 step of the JCL MIGRCAT as follows, where you define RECNB, NODE, OLDFIL, TMPFIL and NEWFIL, replacing with the node number.

Submit the procedure `..INSTALL(MIGRCAT)`

## Migrate the communication media files

The MIGRCOM procedure migrates one media file at a time. The procedure must therefore be modified and executed for each of the nodes and for the main communication medium.

### Migrate the main communication media file

Customize the PMIGR2 step of the MIGRCOM procedure and set the variables RECNB, OLDFIL, TMPFIL and NEWFIL as follows:

Submit the procedure ..INSTALL(MIGRCOM).

## Migrate the nodes (node x) communication media file

The following steps must be performed for each of the nodes.

Customize the PMIGR2 parameters in the JCL MIGRCOM:

Define the variables RECNB, OLDFIL, TMPFIL and NEWFIL. Replace with the node number.

Submit the procedure ..INSTALL(MIGRCOM).

## Customize the JCL ..INSTALL (MNRMON)

Set the Transfer CFT submission option, by STC or JCL, as for the source instance.

## Customize the procedure ..INSTALL(PCFTUTIL)and INCLUDE(CFTINC)

Comment the following lines:
