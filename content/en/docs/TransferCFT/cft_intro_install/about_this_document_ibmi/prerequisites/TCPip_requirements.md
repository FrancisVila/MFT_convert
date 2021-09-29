{
    "title": "TCP/IP requirements",
    "linkTitle": "TCP/IP requirements",
    "weight": "190"
}This section describes the specific requirements for TCP/IP in a Transfer CFT Transfer CFT IBM i environment.

## Interface level used

The interface is a SOCKET type.

## Execution environment

A TCP/IP network must be installed and configured before the Transfer CFT Transfer CFT IBM i product is installed. Use the STRTCP command to start the TCP/IP environment. The configured servers are then started.

## Network environment

### Local domain and host name

1.  To configure the domain and host names, enter **GO CFGTCP**.
2.  In the *CFGTCP menu*, select the Changes local domain and host names option and modify the local domain and host names for your IBM i. The host name is used in the CFTNET command HOST parameter when the Transfer CFT/400 monitor is configured.

### Host table

Each host with which you wish to transfer files must be declared in this table.

To do so, select the WORK WITH TCP/IP HOST TABLE ENTRIES option in the *CFGTCP menu*.

### TCP/IP interface

Each domain with which you wish to transfer files must be declared in an interface.

To do so, select the **WORK WITH TCP/IP INTERFACE** option in the *CFGTCP menu* and add an interface.

A partner address of 192.1.1.1 and the 255.255.255.0 mask are used to separate the network identifier part (192.1.1) from the host identifier part (1). For a site with the same network identifier, you do not need to configure another network interface.

### TCP/IP port restrictions

The SAPs used in the Transfer CFT configuration commands must be declared as ports for the TCP/IP protocol. They must also be associated with the Transfer CFT user profile.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Ports 1 to 1023 are reserved and must not be used by Transfer CFT.</td>
</tr>
</tbody>
</table>

### Checking the network configuration

The PING command is used to test the connection with your partner.

To do so, enter the PING command on an Transfer CFT IBM i command line, followed by the name of the host to be tested. The test results are displayed on the message line.

## Precautions

Any incidents detected impact the following:

-   Security  
    To start TCP, you do not need to have a user profile set to \*IOSYSCFG, but it may be required for some Transfer CFT configuration commands in the TCP/IP environment: the Transfer CFT IBM i messages are explanatory.

Network interface is not started after the ENDTCPIFC command:

You can start the network interface via the WORK WITH TCP/IP INTERFACE option in the CFGTCP menu, or the STRTCPIFC or NESTAT command if the STRTCP command has already been called.
