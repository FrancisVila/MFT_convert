{
    "title": "Start and stop the Copilot server",
    "linkTitle": "Start and stop the Transfer CFT UI (Copilot) server",
    "weight": "190"
}When  `am.type=passport` or `am.type=cg`, the user that connects to the Transfer CFT Copilot server  must be defined in the system as well as in PassPort/.

## Start the Copilot server

This section describes how to start the Transfer CFT Copilot server via either a menu or command. For more information on calling menus, see <a href="../#Transfer" class="MCXref xref">Transfer CFT menu usage</a>.

Menu

1.  Access the *Transfer CFT* .  
    In the Main Menu enter the command `cft` and press **Enter** to open the Transfer CFT menu.
2.  Enter **1** to access **Common CFT commands**.
3.  Select option . The *Copilot server* menu is displayed.  

Command

Execute: `COPSTART `

## Stop the Copilot server

This section describes how to stop the Transfer CFT Copilot server via either a menu or command.

Menu

1.  Access the *Transfer CFT* .  
    In the Main Menu enter the command `cft` and press **Enter** to open the Transfer CFT menu.
2.  Enter **1** to access **Common CFT commands**.
3.  Select option .  
    Only the server waiting for a connection is stopped. Other servers that users have logged onto are shut down when the user logs off, or after a network timeout.

Command

Execute: `COPSTOP `

## Configure the Copilot server

Use the UCONFSET commands to modify the configuration if you need to modify the Transfer CFT Copilot server.
