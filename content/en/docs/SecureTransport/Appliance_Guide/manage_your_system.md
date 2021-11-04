{
    "title": "Manage your system",
    "linkTitle": "Manage your system",
    "weight": "110"
}In this topic you will learn how to:

-   <a href="#_Toc331683661" class="MCXref xref">Set the clock and time zone</a>
-   <a href="#_Toc331683667" class="MCXref xref">Switch between consoles</a>
-   <a href="#Work" class="MCXref xref">Work with system log files</a>

<span id="_Toc331683661"></span>

## Set the clock and time zone

You can use the Clock and Time Zone menu for clustered machines. The time server should be set so that the clustered machines are always in sync.

1.  On the Appliance Management menu, type **T**, Clock/Timezone.
2.  In the Clock and Time Zone panel, select a region. If you select **Global**, the Time Zone panel displays all possible time zones. If you select a different region, the Time Zone panel displays only time zones for that region.
3.  In the Time Zone panel, select your time zone. Use the tab key to navigate between panels.
4.  (optional) Display the correct local time. Type **Alt+H** to set the appliance hardware clock to UTC (Coordinated Universal Time.)
5.  In the Date and Time panel, you can select <span class="span_4" style="font-weight: bold;">Change</span> to manually manage the date and time or to synchronize the date and time with the NTP Server.
6.  From the Clock and Time Zone menu, select **OK**.

<span id="_Toc331683667"></span>

## Switch between consoles

Console 1 is the Appliance Console Menu (blue); it is the first screen you seen when you power up the appliance. Consoles 2-6 allow you to log in directly to the operating system.

To switch from one virtual console to another, use the **Alt+Fn** keyboard combination, where Fn is a value between 1 and 6. For example:

-   From console 6 (Linux kernel) to go to console 1, use the key combination **Alt+F1**.
-   From console 1 to go to console 6, use the key combination **Alt+F6**.

> **Note:**
>
> Using Alt+F4 might close the currently opened window of most browsers.

<span id="Work"></span>

## Work with system log files

The Appliance Console Menu provides you with access to system log files.

1.  Connect to the console. See <a href="../appliancestartup_reboot_shutdown#_Ref331672216" class="MCXref xref">Reboot or shut down the appliance</a> for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **A**, Appliance Management.
3.  On the Appliance Management menu, type **L**, System Log Files.
4.  Use the up and down arrow keys to choose a log file to view and then the left and right arrow keys to choose one the following:
    -   **Live View** — displays a read-only view of the latest log entries
    -   **Full View** — displays a read-only view of the entire selected log file.
