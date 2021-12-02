{
    "title": "Upgrade a multi-node architecture",
    "linkTitle": "Upgrade multi-node architecture",
    "weight": "240"
}This section describes the upgrade of an instance of Transfer CFT z/OS configured in multi-node.

## Prerequisite

You must first perform Steps 1 through 5 as described in the [Upgrade](../) section to the target instance.

## Upgrade the CATALOG files (MIGRCAT)

The MIGRCAT procedure migrates one catalog file at a time. The procedure must be modified and executed for each of the nodes.

Customize the PMIGR2 step of the JCL MIGRCAT as follows, where you define RECNB, NODE, OLDFIL, TMPFIL and NEWFIL, replacing with the node number.

Submit the procedure ..INSTALL(MIGRCAT).

## Upgrade the communication media files

The MIGRCOM procedure migrates one media file at a time. The procedure must therefore be modified and executed for each of the nodes and for the main communication medium.

### Upgrade the main communication media file

Customize the PMIGR2 step of the MIGRCOM procedure and set the variables RECNB, OLDFIL, TMPFIL and NEWFIL as follows:

Submit the procedure ..INSTALL(MIGRCOM).

## Upgrade the nodes (node x) communication media file

The following steps must be performed for each of the nodes.

Customize the PMIGR2 parameters in the JCL MIGRCOM:

Define the variables RECNB, OLDFIL, TMPFIL and NEWFIL. Replace with the node number.

Submit the procedure ..INSTALL(MIGRCOM).

## Customize the JCL ..INSTALL(MNRMON)

Set the Transfer CFT submission option, by STC or JCL, as for the source instance.

## Customize the procedure ..INSTALL(PCFTUTIL) and INCLUDE(CFTINC)

Comment the following lines:
