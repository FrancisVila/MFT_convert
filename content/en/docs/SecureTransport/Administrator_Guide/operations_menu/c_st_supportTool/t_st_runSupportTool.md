{
    "title": "Run the support tool",
    "linkTitle": "Run the support tool",
    "weight": "180"
}The support tool is implemented as an executable script. To create the support information file, run `<FILEDRIVEHOME>/bin/collect_support_information`. The script saves the information configured on the *Support Tool Configuration* page in the configured output directory. The file name is `support_<supportAccessCode>_<hostName>_<timestamp>.tar.gz where`:

-   `<supportAccessCode>` is the value of the **Support Access Code** field on the *Support Tool Configuration* page.
-   `<hostName>` is the host name of the system that the support tool is run on.
-   `<timestamp>` is the UNIX time (the number of seconds that have elapsed since midnight Coordinated Universal Time on January 1, 1970).

To write the support information file to a different directory from the one specified in the **Output Directory** field on the *Support Tool Configuration* page, use the following command:

`<FILEDRIVEHOME>/bin/collect_support_information -d <outputDirectory>`

If the output directory does not exist, the support tool creates it.

The support tool can run when the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> database in not available, but it cannot collect the following information that is stored in the database:

-   Server log
-   File tracking
-   Audit log
-   Server configuration

During execution, the support tool outputs status messages and a final message that path name of the support information file. You can use <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to push the file to another location.

> **Note:**
>
> The TM thread dump can slow the operation of the TM and, more significantly, the TM heap dump can prevent the TM from processing events for 30 minutes or more, depending on the configured heap size. It is best to run the support tool when there is no load on SecureTransport.

**Related topics:**

-   <a href="../t_st_configuresupporttool" class="MCXref xref">Configure the support tool</a>
-   <a href="../t_st_customizesupporttool" class="MCXref xref">Add custom information to the support information file</a>

## Run the support tool automatically when the TM runs out of memory

You can configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to run the support tool automatically when the Transaction Manager (TM) fails with an `OutOfMemoryError`. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> runs the support tool before it restarts the TM.

1.  Edit the `<FILEDRIVEHOME>/bin/crash_tm` file and comment out a line so that it is:  
    `# collect_crash_info="false"`
2.  If **Collect TM heap dump** is selected on the *Support Tool Configuration* page, edit the `<FILEDRIVEHOME>/bin/start_tm_console` file and comment out a line so that it is:  
    `# disableHeapDumpOnOutOfMemoryError="true"`
3.  Restart the Transaction Manager on all clustered <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers or all synchronized <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers using the `stop_tm` and `start_tm` commands in `<FILEDRIVEHOME>/bin`.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> runs the support tool using the configuration from the *Support Tool Configuration* page.

> **Note:**
>
> Due to a technical limitation, when the crash\_tm script runs the support tool on any system other than IBM AIX, the support information file does not include the TM thread dump.
