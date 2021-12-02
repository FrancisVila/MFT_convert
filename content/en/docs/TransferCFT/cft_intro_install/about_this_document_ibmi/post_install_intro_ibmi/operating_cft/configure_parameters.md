{
    "title": "Configuring Transfer CFT parameters",
    "linkTitle": "Configuring Transfer CFT parameters",
    "weight": "310"
}From the , enter the command `cft` and press **Enter** to open the .

1.  Select option 1 Customization and press ENTER.
2.  In the Customization screen, select option 1 CFT parameters and press ENTER.
3.  You can select option **2 Interpret the selected member**.

<span id="Interpreting a parameter source"></span>

## Interpreting a parameter source

The parameter file that you selected in the previous step, option 1 Editing the parameter source member, is interpreted by CFTUTIL. The options are confirmed before being interpreted. To interpret or update a parameter source, select option 2 Interpret selected member in the Customization screen. The following screen is displayed.

The parameter and partner files can be created, re-created, or updated prior to interpretation. If this is the first time that you are interpreting a parameter source, you must first create it.

-   Select 1= Create for each time you interpret a new parameter source.

<!-- -->

-   Select 2 = Update to change existing command parameters. You can modify many of the Transfer CFT parameters while CFT is running, but some configuration command changes cannot be applied dynamically. For more information, refer to the Transfer CFT online documentation.

If you select 1 Configuration interpretation, Transfer CFT displays following messages.

View messages

An interpretation is considered to be valid when all messages are displayed as Correct.

If an interpretation error is detected, modify the invalid parameter or parameter, and select **2 Repeat the interpretation**. When you select 2 Repeat the interpretation, only messages concerning configuration commands are displayed.
