{
    "title": "Defining TCP/IP parameters",
    "linkTitle": "Defining TCP/IP parameters",
    "weight": "250"
}# <span id="Setting_parameters_in_TCP_IP"></span>Defining TCP/IP parameters

This topic describes the parameter settings for Transfer CFT when using
TCP/IP.

## <span id="Specific_parameter_settings_for_TCP_IP"></span>Specific parameter settings for TCP/IP

### Modifying the connection wait timeout period

Environment variable

CFTCONTCP

This timeout period corresponds to a period for Transfer CFT to wait
for a communication to be established. The default timeout period is 120
seconds.

To change this value, set the CFTCONTCP
environment variable to the desired value in seconds.

Example

For a period of 20 seconds:

SET CFTCONTCP=20

### Parameter settings for the initialization phase

Transfer CFT uses TCP/IP for data transfers with defined remote partners.
It also uses this layer for its own internal exchanges. More particularly
for exchanges between the cfttpro.exe and cftn\_005.exe processes.

Certain configurations on the TCP/IP network are incompatible with the
default options set for Transfer CFT internal exchanges. These configurations
are generally associated with the use of the DNS and DHCP services. To
remedy these difficulties, Transfer CFT’s TCP/IP layer can be parameterized
using the method below:

Define the "TCP LOCALHOSTTYPE" parameter in the cftnet.conf
file.

This parameter can take on the following values:

-   LOCALNAME

The HOSTS file or the DNS service is used to obtain the machine’s IP
address. The HOSTS file (the DNS service) must contain the IP address
that corresponds to the name of the machine.  
Default value:

-   LOCALHOST

The standard name "localhost" is used. It is sometimes necessary
for the HOSTS file to contain the IP address of the standard localhost
name. In general the value of this IP address is 127.0.0.1.

-   IPADDRESS

IP address of the local machine, obtained directly. This is stated in
the LOCALHOSTADDR. Parameter.

If "TCP LOCALHOSTTYPE" is the IPADDRESS, the "TCP LOCALHOSTADDR"
parameter can be defined. It must be the same as the machine’s IP address.
Its default value is 127.0.0.1 (the standard IP address of the machine).

Note: These parameters are independent of the value of the HOST field
in the CFTNET command. They are used for internal communication between
Transfer CFT processes when the CFTNET command defines the characteristics
of the local resource used for data exchange with remote partners.

Transfer CFT with RAS example

To use Transfer CFT with RAS, the IP address may be dynamic (DHCP server)
without a predefined host name. You would therefore use the machine’s
standard IP address of 127.0.0.1  
To do this, define the two following lines in the cftnet.conf file:  

TCP LOCALHOSTTYPE=IPADDRESS  
TCP LOCALHOSTADDR=127.0.0.1

### Using the TCP/IP via the RAS layer

You can set the Transfer CFT Windows TCP/IP layer parameters to use
the Windows RAS service. This service allows access to a remote TCP/IP
via a modem using a PSTN line, Public Switched Telephone Network.

These services are always proposed when the two systems are installed.
The system and network administrators for the machine on which Transfer
CFT is installed are responsible for configuring these services.

Before attempting to use Transfer CFT via TCP/IP on RAS, the machine using RAS must integrate with the
remote TCP/IP network. This integration is tested once the RAS connection
has been made. The remote hosts specified
for Transfer CFT can be reached by the standard utilities of the TCP/IP
layer - PING, TELNET, and so on.

Transfer CFT’s management of the RAS layer is performed using the Microsoft
API, the dynamic library rasapi32.dll. When a Transfer CFT partner
is configured to utilize a RAS directory entry, it manages the RAS connection
and disconnection dynamically. The disctd parameter in the CFTPROT command
states the wait time before the RAS disconnects in the absence of another
request to transfer.

Syntax of the CFTTCP HOST parameter:

HOST=PPPxx@host

Where:

-   PPPxx: is the
    name of the section in the cftras.ini file (xx between 00 and 99
    inclusive)
-   host: corresponds
    either to the name of the remote host, or the IP address of the  
    remote partner

The description of the RAS connections used by Transfer CFT is located
in the cftras.ini file, in the Transfer
CFT `runtime\conf` folder. This file has a standard \*.INI file structure.

Structure of the cftras.ini file

Each section has the format:

-   \[PPPxx\]          :
    the name of the section (xx between 00 and 99 inclusive)
-   linkentry=LINK1    
    : the entry defined in the Windows RAS directory
-   phoneno=1234567890
    : the telephone number of the RAS server
-   server=server :
    the NT server on which the user is identified
-   username=user :
    the name of the user connecting to the RAS server
-   password=password    
    : the password of the user connecting to the RAS server

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">          </td>
      </tr>
</table>

-   The link
    entry field, as defined in the RAS directory, is mandatory.
-   All the other fields
    in a section are optional. Their default values are as defined in the
    RAS directory entry. If necessary, these optional parameters can replace
    the parameters defined in the RAS directory entry.

### Security

If a machine possesses several IP addresses, it can receive incoming
calls only on the IP address given in the HOST field of the CFTNET command.

To receive incoming calls without taking account of the machine’s IP
address, you need to set the value INADDR\_ANY in the HOST field of the
CFTNET command.

### Flow performance

To maximize the transfer flow performance in a CFT environment, you
can modify the TCP Windows variable in the Windows registry database.
Access the cftnet.conf file and modify the variable: TCP TCPWINDOWSIZE.
There is no minimum or maximum value. You must run Transfer CFT to test the new
variable performance.

Example  
Define the following line in the cftnet.conf file:

     TCP TCPWINDOWSIZE=64240
