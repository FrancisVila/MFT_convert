{
    "title": "Uninstall ",
    "linkTitle": "Uninstall",
    "weight": "140"
}This page describes how to uninstall Transfer CFT. When you uninstall a Transfer CFT, you lose the complete Transfer CFT
configuration. To avoid this,  save your environment (samples, exits, etc.) before removing the Transfer CFT.

## Modes

Interactive

./uninstall

Silent

./uninstall --mode unattended

## Procedure

1.  Stop the server you want to uninstall.
2.  Enter the `uninstall `command from the path of the Transfer CFT to uninstall.  
    For example:
3.  A message displays asking if you want to uninstall; click **Yes** to continue.  
    You are reminded to check that all Transfer CFT processes are stopped.
4.  A message displays asking if you want to delete the runtime. Selecting **Yes** removes the runtime folder and all of its contents. If you are in a cluster installation, or want to keep information stored in the runtime, select **No**.
5.  Click **Next** to uninstall, and **Finish** to exit.
