{
    "title": "System requirements",
    "linkTitle": "System requirements",
    "weight": "150"
}The following are the system requirements for <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

## About the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> environment

### Unix/Linux system prerequisites

Transfer CFT requires that you install the appropriate library for your operating system:

-   Linux requires the ncurses version 5 library
-   Unix systems, except Linux, require the curses library

### Supported operating systems and browsers

Refer to the <span class="mc-variable axway_variables.Platform_or_Suite_Long_Name variable">AMPLIFY</span> Supported Platforms guide available on <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Support at <a href="https://support.axway.com/" class="hyperlink">https://support.axway.com</a>.

## Disk space and RAM requirements

<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> has the following hardware requirements:

-   Disk space requirement
    -   1.5 to 5 Gigabyte: minimum disk space to allow for future updates, SPs, and continued performance
-   RAM Requirement
    -   128 Megabyte: minimum dedicated per host

## Java

If you intend to implement Secure Relay you require Java 8, which is not delivered with Transfer CFT (except on HP PARISC and WIN IA64 where only Java 6 is delivered).

When using Secure Relay, Java must be installed in the same environment as the Transfer CFT installation. The Master Agent is managed, but the Router Agent can be in another environment.
