{
    "title": "Synchronous transfer request examples",
    "linkTitle": "Request examples",
    "weight": "280"
}This topic presents synchronous transfer request examples using the WSTATES or WPHASES/WPHASESTEPS parameters with the SEND/RECV command, or the SWAITCAT command.

## WPHASES and WPHASESTEPS

The WPHASES and WPHASESTEPS parameters allow for more precision and possibilities than using WSTATES alone.

Example of a transfer request where the wphases is used in conjunction with wphasesteps

Example of a simple transfer request using only wphases

## WSTATES and WTIMEOUT examples

-   Example 1: Transfer request using WSTATES
-   Example 2: Use a SEND with WSTATES and WTIMEOUT

**Example 1: Transfer request using WSTATES**

Trigger a command pending that a transfer has reached a certain defined state. See also WSTATES. This task resembles an FTP transfer.

**Example 2: Use a SEND with WSTATES and WTIMEOUT**

In this example, the transfer fails because it did not complete prior to the timeout, which leads to an error code of 81.

**Example 3: Serialization using WSTATES**

In this example the transfers are executed sequentially depending on the defined WSTATES.

## SWAITCAT example

The examples describe how to use SWAITCAT to perform the following task, wstates is the best way to wait (or wphases).

<span id="SWAITCAT ex 1"></span>**Example: Execute a command once all transfers have completed**

The following example is a way to execute a batch processing task using SWAITCAT, which is a task that you cannot perform using the SEND command with WSTATES.
