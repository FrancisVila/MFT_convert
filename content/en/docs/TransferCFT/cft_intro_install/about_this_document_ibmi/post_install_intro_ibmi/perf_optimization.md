{
    "title": "Performance optimization",
    "linkTitle": "Performance optimization",
    "weight": "250"
}This section describes how to modify the subsystems in which <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> is running to optimize the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> performance.

The initial subsystem that <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> uses is created with a 2 GB pool size, and a maximum of 64 active threads. However it is not the maximum number of threads that impacts performance, but rather the number of threads that can use the processor. For this reason, we recommend that you modify this value for improved performance.

## Prerequisites

The subsystem must be running to perform the following procedure. If your subsystem is not running, call the <span class="code">STRSBS </span>command to start the subsystem.

## Procedure

Update the subsystem values as follows:

1.  Enter the <span class="code">WRKSYSSTS </span>command to display the existing system configuration for the subsystems that are currently running.
    1.  Press F11 to display the subsystem name and determine your specific <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> subsystem.
2.  Modify the value:
    1.  Place the cursor in the <span class="code">Max Act</span> field (Maximum Active), and enter the new value (*10* in the example below).
    2.  Press **Enter** to confirm.
    3.  Press **F5** to update the screen display.

<img src="/Images/TransferCFT/ibmi_subsystems.png" class="mediumWidth" />

## How to determine the **Max Act** values

To determine the maximum active (Max Act) values, use the following formula:

16 + SSLMTASK + MAXTASK = &lt;Max Act>

Where:

-   16 = any basic <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> task
-   SSLMTASK = maximum number of SSL tasks
-   MAXTASK = maximum number of CFTFIL tasks

If you are using multinode, multiply the sum by the total number of nodes.
