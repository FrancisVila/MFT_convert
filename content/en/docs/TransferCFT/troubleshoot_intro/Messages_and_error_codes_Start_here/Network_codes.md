{
    "title": "Network  codes",
    "linkTitle": "Network codes",
    "weight": "470"
}## NCR Common return code - Network interface

The NCR code corresponds to the "cr" code returned by the
network interface {{< TransferCFT/componentshortname  >}} functions, using
the formula: **ncr = -(cr+20)**

Supply this value to Product Support for troubleshooting operations.

<span id="NCS"></span>

## NCS System return code - Network interface

The value of this code depends on the type of network
and operating system. It corresponds to the "cs" code returned
by the network interface functions.

<span id="NCS___TCP_IP_System_Return_Codes"></span>

### NCS - TCP/IP System Return Codes

If the value of the code is less than 500 (decimal), that is 1F4 (hexadecimal),
it concerns the "errno" variable provided by the TCP/IP resource.
In this case, refer to the manufacturer's documentation for the meaning
of this code.
