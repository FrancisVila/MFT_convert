{
    "title": "Remove updates",
    "linkTitle": "Remove updates",
    "weight": "120"
}This section describes uninstalling a patch or service pack. You can uninstall updates in GUI or console mode, depending on your operating system.

## Remove updates in GUI mode

1.  Use the Update function of the installer:
2.  In the Windows **Start** menu, select  
    **Axway Software > Axway \[installation name\] > Update**
3.  On the Updates Management page, select the update you want to uninstall and click **Remove**.
4.  Click **Next** to continue.
5.  Review the updates you want to uninstall. To remove the update, click **Update**.
6.  After the updates have been uninstalled, click **Next** to view the summary. It displays the list of updates that were removed

## Remove updates in console mode

For UNIX/Linux environments:

1.  From the installation root directory, enter the command: `update.sh –m gui`
2.  In the Welcome section, click **Enter** to continue.
3.  In the License agreement section, accept the terms of the license agreement.
4.  In the Updates Management section, select option 2, Remove one or more patches and/or service packs.
5.  A tree of products is displayed that represents all the installed products, each of them with their latest updates.
6.  Select the update you want to uninstall.
7.  When you move to the next section Updates Management is displayed again, where you can perform another update action if you need to. If you do not have any more updates to do, move to the next section.
8.  Start the update execution.
9.  Review the summary and exit.

 

For Windows environments:

1.  From the installation root directory, enter the command: `update32.exe –m gui` or `update64.exe –m gui` if running on a 64-bit executable.
2.  Follow the preceding steps for uninstalling an update.
