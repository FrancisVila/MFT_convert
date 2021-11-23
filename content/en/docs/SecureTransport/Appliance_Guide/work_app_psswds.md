{
    "title": "Work with appliance passwords",
    "linkTitle": "Manage appliance passwords",
    "weight": "90"
}In addition to setting passwords, the appliance platform allows you to manage your appliance password, including requirements for defining password complexity rules.

<span id="_Toc331683663"></span>

## Set the appliance password

Use this procedure to set your appliance password. Setting a new password requires that you know the current password and that the new password meets complexity rules. See [Manage the appliance password](#_Toc331683665) for information about specifying password complexity rules.

1.  Connect to the console. See [Reboot or shut down the appliance](../appliancestartup_reboot_shutdown#_Ref331672216) for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **H**, Hardening & Security.
3.  On the Hardening & Security menu, type **P**, Password Configuration.
4.  From the Password Configuration menu, type **M**, Modify root/console menu password, to change the appliance console password. The appliance prompts you for your old password. You must enter the correct password to proceed. If you enter an incorrect password, you are returned to the Password Configuration menu.

> **Note:**
>
> Default password after installation: axway

> **Note:**
>
> Whenever you are prompted to type the password, the keys you type are not displayed on the screen. Type the password and press Enter, and the next prompt or menu is displayed.

<span id="_Toc331683665"></span>

## Manage the appliance password

Use the following information to help you manage complexity rules for passwords and Appliance Console Menu password protection.

1.  Connect to the console. See [Reboot or shut down the appliance](../appliancestartup_reboot_shutdown#_Ref331672216) for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **H**, Hardening & Security.
3.  On the Hardening & Security menu, type **P**, Password Configuration.
4.  Set password complexity.
    1.  Change password complexity rules. Type **U**, Update password complexity rules.
    2.  The menu displays a series of prompts where you specify the minimum number of characters, numerical characters, upper case characters, lower case characters and special characters your password should contain to be valid.
    3.  At the end of the prompts, type **y** to save your changes or type **n** to discard them.
5.  (optional) Reset password complexity back to the default. On the Password Configuration menu, type **R**.
6.  (optional) Type **E** to enable or **D** to disable password protection for the Appliance Console Menu. If you enable it, when you connect to the appliance, the log in prompt displays and you must log in to see the Appliance Console Menu. If you disable password protection, when you connect to the appliance, you see the Appliance Console Menu without having to log in.
7.  When the changes are complete, type **B** to return to the Hardening & Security menu.
