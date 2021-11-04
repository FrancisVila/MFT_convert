{
    "title": "Configuring Gateway objects for simulation mode",
    "linkTitle": "Configuring Gateway objects for simulation mode",
    "weight": "330"
}If you have not already done so, import the Remote Sites, Trading Partners, Decision Rules and Models from the TARGET2 package and update the configuration file as described in:

-   [Imported objects](../../c_qt2_configoverview/c_qt2_importedobjects)
-   [Editing TARGET2 files and objects](../../c_qt2_configoverview/t_qt2_editfilesandobjects)

After you import the objects, you must then configure them using either Gateway Navigator or the command line mode.

## Configuring the TARGET2 Trading Partners

To set up the loop configuration, enter values for the parameters name, service, and request type in the following objects:

-   QT2\_TP\_LOCAL
-   QT2\_TP\_REMOTE\_FILE\_SSP
-   QT2\_TP\_REMOTE\_SPP

To make sure that the QT2\_TP\_REMOTE\_SSP Partner is in pull-mode (receipt request and request receipt synchronized), execute the command:

peladm update\_tradepart -a QT2\_TP\_REMOTE\_SSP -rr signed -rrs Y

## Configuring Decision Rules

Modify and configure the imported Decision Rules for routing to the back-end applications. All Decision Rules, if not specified otherwise, must be linked to an active Rule Table.

Attach the following Decision Rules to the default Rule Table. In each Decision Rule, modify the criteria <span class="codeBold_in_para">trade service= trgt.\*</span> to <span class="codeBold_in_para">trade service= \*</span>:

-   INCOMING\_GETFILE\_SSP
-   INCOMING\_GETFILE\_SSP\_KO1
-   INCOMING\_SSP\_IA\_RESPONSE1
-   OUTGOING\_SSP\_IA\_REQ\_KO1

## Updating the configuration file

In the TARGET2 configuration file located at <span class="code">../qt2/config</span>, set the execution mode to simulation (SIM):

set MODE=SIM

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
