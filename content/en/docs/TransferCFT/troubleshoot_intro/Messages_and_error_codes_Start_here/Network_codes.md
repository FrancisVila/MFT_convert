{
    "title": "Network codes",
    "linkTitle": "Network codes",
    "weight": "490"
}# <span id="title"></span>Network codes

## NCR Common return code - Network interface

The NCR code corresponds to the "cr" code returned by the
network interface Transfer CFT functions, using
the formula: ncr = -(cr+20)

Supply this value to Product Support for troubleshooting operations.

## <span id="NCS"></span>NCS System return code - Network interface

The value of this code depends on the type of network
and operating system. It corresponds to the "cs" code returned
by the network interface functions.

### <span id="NCS___TCP_IP_System_Return_Codes"></span>NCS - TCP/IP System Return Codes

If the value of the code is less than 500 (decimal), that is 1F4 (hexadecimal),
it concerns the "errno" variable provided by the TCP/IP resource.
In this case, refer to the manufacturer's documentation for the meaning
of this code.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Hexadecimal Code</th>
<th>Decimal Code</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td><p>23a</p></td>
<td width="21.039%"><p>570</p></td>
<td width="52.347%"><p>Reception of a Define Resource request concerning an already
registered resource</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>23b</p></td>
<td width="21.039%"><p>571</p></td>
<td width="52.347%"><p>Reception of an Undefined Resource request for a resource
with registered users</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>23c</p></td>
<td width="21.039%"><p>572</p></td>
<td width="52.347%"><p>Reception of an Undefined Resource request for a resource
with active connections</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>23d</p></td>
<td width="21.039%"><p>573</p></td>
<td width="52.347%"><p>Maximum number of connections to a resource reached during
a Connect Request</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>244</p></td>
<td width="21.039%"><p>580</p></td>
<td width="52.347%"><p>Cannot find an available port for the CFTTPRO polling socket</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>245</p></td>
<td width="21.039%"><p>581</p></td>
<td width="52.347%"><p>Reply to a synchronous request of incorrect length</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>246</p></td>
<td width="21.039%"><p>582</p></td>
<td width="52.347%"><p>CFTTPRO polling socket closed remotely during the TCP/IP
server activation confirmation phase</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>247</p></td>
<td width="21.039%"><p>583</p></td>
<td width="52.347%"><p>Time-out while waiting for TCP/IP server activation confirmation
message</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>248</p></td>
<td width="21.039%"><p>584</p></td>
<td width="52.347%"><p>Time-out while waiting for a synchronous request reply</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>249</p></td>
<td width="21.039%"><p>585</p></td>
<td width="52.347%"><p>CFTTPRO polling socket closed by remote end during the
synchronous request reply wait phase</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>26d</p></td>
<td width="21.039%"><p>621</p></td>
<td width="52.347%"><p>Invalid parameter received in response to a synchronous
request (socket-based communication between CFTTCP and CFTTPRO)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>26e</p></td>
<td width="21.039%"><p>622</p></td>
<td width="52.347%"><p>Invalid parameter received in response to a synchronous
request (queue-based communication between CFTTCP and CFTTPRO)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>26f</p></td>
<td width="21.039%"><p>623</p></td>
<td width="52.347%"><p>Flow control is active when it should not be</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>270</p></td>
<td width="21.039%"><p>624</p></td>
<td width="52.347%"><p>Host identifier invalid in a Define Resource request</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>271</p></td>
<td width="21.039%"><p>625</p></td>
<td width="52.347%"><p>Host identifier invalid in an Undefine Resource request</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>272</p></td>
<td width="21.039%"><p>626</p></td>
<td width="52.347%"><p>Invalid parameter to be sent in response to a synchronous
request (Define Resource, Undefine Resource, Register Request or Deregister
Request)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>273</p></td>
<td width="21.039%"><p>627</p></td>
<td width="52.347%"><p>Invalid parameter to be sent in response to a synchronous
request (Define Resource, Undefine Resource, Register Request or Deregister
Request)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>274</p></td>
<td width="21.039%"><p>628</p></td>
<td width="52.347%"><p>Host identifier invalid in a Register Request</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>275</p></td>
<td width="21.039%"><p>629</p></td>
<td width="52.347%"><p>Unknown request type provided by CFTTPRO</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>276</p></td>
<td width="21.039%"><p>630</p></td>
<td width="52.347%"><p>Define Resource request denied because maximum number of
resources reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>280</p></td>
<td width="21.039%"><p>640</p></td>
<td width="52.347%"><p>Time-out when establishing the outgoing connection</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2b2</p></td>
<td width="21.039%"><p>690</p></td>
<td width="52.347%"><p>Remote polling closed during datagram transmission</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2ef</p></td>
<td width="21.039%"><p>751</p></td>
<td width="52.347%"><p>Link socket between CFTTPRO and CFTTCPS closed (in the
case of a socket connection)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2f0</p></td>
<td width="21.039%"><p>752</p></td>
<td width="52.347%"><p>Socket closed by remote end (L1 byte write phase)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2f1</p></td>
<td width="21.039%"><p>753</p></td>
<td width="52.347%"><p>Socket closed by remote end (L2 byte write phase)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2f2</p></td>
<td width="21.039%"><p>754</p></td>
<td width="52.347%"><p>Socket closed by remote end (data write phase)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2f3</p></td>
<td width="21.039%"><p>755</p></td>
<td width="52.347%"><p>Socket closed by remote end (L1 byte read phase)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2f4</p></td>
<td width="21.039%"><p>756</p></td>
<td width="52.347%"><p>Socket closed by remote end (L2 byte read phase)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2f5</p></td>
<td width="21.039%"><p>757</p></td>
<td width="52.347%"><p>Socket closed by remote end (data read phase)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2f6</p></td>
<td width="21.039%"><p>758</p></td>
<td width="52.347%"><p>Socket closed unexpectedly by remote end (L1 byte write
phase)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2f7</p></td>
<td width="21.039%"><p>759</p></td>
<td width="52.347%"><p>Socket closed unexpectedly by remote end (L2 byte write
phase)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2f8</p></td>
<td width="21.039%"><p>760</p></td>
<td width="52.347%"><p>Socket closed unexpectedly by remote end (data write phase)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2f9</p></td>
<td width="21.039%"><p>761</p></td>
<td width="52.347%"><p>Invalid status for read automaton (rdstate)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2fa</p></td>
<td width="21.039%"><p>762</p></td>
<td width="52.347%"><p>Read error (L1 read phase)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>2fb</p></td>
<td width="21.039%"><p>763</p></td>
<td width="52.347%"><p>Read error (L2 read phase)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>2fc</p></td>
<td width="21.039%"><p>764</p></td>
<td width="52.347%"><p>Link socket closed by CFTTPRO</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>3c0</p></td>
<td width="21.039%"><p>960</p></td>
<td width="52.347%"><p>Register Request request for an unknown resource</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>3c1</p></td>
<td width="21.039%"><p>961</p></td>
<td width="52.347%"><p>Symbolic name unknown for a polling port</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>3c2</p></td>
<td width="21.039%"><p>962</p></td>
<td width="52.347%"><p>Use of a symbolic name for a polling port but this feature
is not supported by the system</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>3c3</p></td>
<td width="21.039%"><p>963</p></td>
<td width="52.347%"><p>Host Internet address unknown</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>3c4</p></td>
<td width="21.039%"><p>964</p></td>
<td width="52.347%"><p>Host symbolic name unknown</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>3c5</p></td>
<td width="21.039%"><p>965</p></td>
<td width="52.347%"><p>Error in gethostbyname(): local host specification</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>3c6</p></td>
<td width="21.039%"><p>966</p></td>
<td width="52.347%"><p>Error in gethostbyname(): remote host specification</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>3d6</p></td>
<td width="21.039%"><p>982</p></td>
<td width="52.347%"><p>Undefine Resource request for an unknown resource</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>3de</p></td>
<td width="21.039%"><p>990</p></td>
<td width="52.347%"><p>Register Request request for an unknown polling port name</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>44e</p></td>
<td width="21.039%"><p>00001102</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: dynamic
table allocation</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>44f</p></td>
<td width="21.039%"><p>00001103</p></td>
<td width="52.347%"><p>De-register Request request for an unknown reference: dynamic
allocation of the data area</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>450</p></td>
<td width="21.039%"><p>00001104</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: attribute
string incorrect</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>451</p></td>
<td width="21.039%"><p>00001105</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: call
parameter</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>452</p></td>
<td width="21.039%"><p>00001106</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: manager
not running</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>453</p></td>
<td width="21.039%"><p>00001107</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: contexts
still active</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>454</p></td>
<td width="21.039%"><p>00001108</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: table
access denied</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>455</p></td>
<td width="21.039%"><p>00001109</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: no
more available managers</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>456</p></td>
<td width="21.039%"><p>00001110</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: context
does not exist</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>457</p></td>
<td width="21.039%"><p>00001111</p></td>
<td width="52.347%"><p>Deregister Request request for an unknown reference: end
of table reached</p></td>
</tr>
<tr class="even" data-valign="top">
<td>468</td>
<td width="21.039%">00001128</td>
<td width="52.347%">ECONNREFUSED: The attempt to connect was rejected</td>
</tr>
<tr class="odd" data-valign="top">
<td><p>4b2</p></td>
<td width="21.039%"><p>00001202</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: dynamic
table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>4b3</p></td>
<td width="21.039%"><p>00001203</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: dynamic
allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>4b4</p></td>
<td width="21.039%"><p>00001204</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: incorrect
attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>4b5</p></td>
<td width="21.039%"><p>00001205</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: call
parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>4b6</p></td>
<td width="21.039%"><p>00001206</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: manager
not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>4b7</p></td>
<td width="21.039%"><p>00001207</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: contexts
still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>4b8</p></td>
<td width="21.039%"><p>00001208</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: table
access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>4b9</p></td>
<td width="21.039%"><p>00001209</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: no
more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>4ba</p></td>
<td width="21.039%"><p>00001210</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: context
does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>4bb</p></td>
<td width="21.039%"><p>00001211</p></td>
<td width="52.347%"><p>Context release problem during a Deregister Request: end
of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>516</p></td>
<td width="21.039%"><p>00001302</p></td>
<td width="52.347%"><p>Register context table scan error: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>517</p></td>
<td width="21.039%"><p>00001303</p></td>
<td width="52.347%"><p>Register context table scan error: dynamic allocation of
the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>518</p></td>
<td width="21.039%"><p>00001304</p></td>
<td width="52.347%"><p>Register context table scan error: incorrect attribute
string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>519</p></td>
<td width="21.039%"><p>00001305</p></td>
<td width="52.347%"><p>Register context table scan error: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>51a</p></td>
<td width="21.039%"><p>00001306</p></td>
<td width="52.347%"><p>Register context table scan error: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>51b</p></td>
<td width="21.039%"><p>00001307</p></td>
<td width="52.347%"><p>Register context table scan error: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>51c</p></td>
<td width="21.039%"><p>00001308</p></td>
<td width="52.347%"><p>Register context table scan error: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>51d</p></td>
<td width="21.039%"><p>00001309</p></td>
<td width="52.347%"><p>Register context table scan error: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>51e</p></td>
<td width="21.039%"><p>00001310</p></td>
<td width="52.347%"><p>Register context table scan error: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>51f</p></td>
<td width="21.039%"><p>00001311</p></td>
<td width="52.347%"><p>Register context table scan error: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>57a</p></td>
<td width="21.039%"><p>00001402</p></td>
<td width="52.347%"><p>Connection context table scan error: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>57b</p></td>
<td width="21.039%"><p>00001403</p></td>
<td width="52.347%"><p>Connection context table scan error: dynamic data area
allocation</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>57c</p></td>
<td width="21.039%"><p>00001404</p></td>
<td width="52.347%"><p>Connection context table scan error: incorrect attribute
string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>57d</p></td>
<td width="21.039%"><p>00001405</p></td>
<td width="52.347%"><p>Connection context table scan error: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>57e</p></td>
<td width="21.039%"><p>00001406</p></td>
<td width="52.347%"><p>Connection context table scan error: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>57f</p></td>
<td width="21.039%"><p>00001407</p></td>
<td width="52.347%"><p>Connection context table scan error: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>580</p></td>
<td width="21.039%"><p>00001408</p></td>
<td width="52.347%"><p>Connection context table scan error: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>581</p></td>
<td width="21.039%"><p>00001409</p></td>
<td width="52.347%"><p>Connection context table scan error: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>582</p></td>
<td width="21.039%"><p>00001410</p></td>
<td width="52.347%"><p>Connection context table scan error: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>583</p></td>
<td width="21.039%"><p>00001411</p></td>
<td width="52.347%"><p>Connection context table scan error: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>5de</p></td>
<td width="21.039%"><p>00001502</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>5df</p></td>
<td width="21.039%"><p>00001503</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: dynamic allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>5e0</p></td>
<td width="21.039%"><p>00001504</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>5e1</p></td>
<td width="21.039%"><p>00001505</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>5e2</p></td>
<td width="21.039%"><p>00001506</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>5e3</p></td>
<td width="21.039%"><p>00001507</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>5e4</p></td>
<td width="21.039%"><p>00001508</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>5e5</p></td>
<td width="21.039%"><p>00001509</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>5e6</p></td>
<td width="21.039%"><p>00001510</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>5e7</p></td>
<td width="21.039%"><p>00001511</p></td>
<td width="52.347%"><p>Error in the search for an entry in the Register context
table: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>642</p></td>
<td width="21.039%"><p>00001602</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>643</p></td>
<td width="21.039%"><p>00001603</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: dynamic data area allocation</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>644</p></td>
<td width="21.039%"><p>00001604</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>645</p></td>
<td width="21.039%"><p>00001605</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>646</p></td>
<td width="21.039%"><p>00001606</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>647</p></td>
<td width="21.039%"><p>00001607</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>648</p></td>
<td width="21.039%"><p>00001608</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>649</p></td>
<td width="21.039%"><p>00001609</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>64a</p></td>
<td width="21.039%"><p>00001610</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>64b</p></td>
<td width="21.039%"><p>00001611</p></td>
<td width="52.347%"><p>Error in the search for an entry in the connection context
table: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>6a6</p></td>
<td width="21.039%"><p>00001702</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>6a7</p></td>
<td width="21.039%"><p>00001703</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: dynamic allocation
of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>6a8</p></td>
<td width="21.039%"><p>00001704</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: incorrect attribute
string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>6a9</p></td>
<td width="21.039%"><p>00001705</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>6aa</p></td>
<td width="21.039%"><p>00001706</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>6ab</p></td>
<td width="21.039%"><p>00001707</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>6ac</p></td>
<td width="21.039%"><p>00001708</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>6ad</p></td>
<td width="21.039%"><p>00001709</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: no more managers
available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>6ae</p></td>
<td width="21.039%"><p>00001710</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: context does not
exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>6af</p></td>
<td width="21.039%"><p>00001711</p></td>
<td width="52.347%"><p>Provider context (reference) invalid: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>70a</p></td>
<td width="21.039%"><p>00001802</p></td>
<td width="52.347%"><p>Socket reference invalid: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>70b</p></td>
<td width="21.039%"><p>00001803</p></td>
<td width="52.347%"><p>Socket reference invalid: dynamic allocation of the data
area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>70c</p></td>
<td width="21.039%"><p>00001804</p></td>
<td width="52.347%"><p>Socket reference invalid: incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>70d</p></td>
<td width="21.039%"><p>00001805</p></td>
<td width="52.347%"><p>Socket reference invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>70e</p></td>
<td width="21.039%"><p>00001806</p></td>
<td width="52.347%"><p>Socket reference invalid: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>70f</p></td>
<td width="21.039%"><p>00001807</p></td>
<td width="52.347%"><p>Socket reference invalid: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>710</p></td>
<td width="21.039%"><p>00001808</p></td>
<td width="52.347%"><p>Socket reference invalid: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>711</p></td>
<td width="21.039%"><p>00001809</p></td>
<td width="52.347%"><p>Socket reference invalid: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>712</p></td>
<td width="21.039%"><p>00001810</p></td>
<td width="52.347%"><p>Socket reference invalid: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>713</p></td>
<td width="21.039%"><p>00001811</p></td>
<td width="52.347%"><p>Socket reference invalid: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>76e</p></td>
<td width="21.039%"><p>00001902</p></td>
<td width="52.347%"><p>Provider context (index) invalid: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>76f</p></td>
<td width="21.039%"><p>00001903</p></td>
<td width="52.347%"><p>Provider context (index) invalid: dynamic allocation of
the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>770</p></td>
<td width="21.039%"><p>00001904</p></td>
<td width="52.347%"><p>Provider context (index) invalid: incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>771</p></td>
<td width="21.039%"><p>00001905</p></td>
<td width="52.347%"><p>Provider context (index) invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>772</p></td>
<td width="21.039%"><p>00001906</p></td>
<td width="52.347%"><p>Provider context (index) invalid: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>773</p></td>
<td width="21.039%"><p>00001907</p></td>
<td width="52.347%"><p>Provider context (index) invalid: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>774</p></td>
<td width="21.039%"><p>00001908</p></td>
<td width="52.347%"><p>Provider context (index) invalid: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>775</p></td>
<td width="21.039%"><p>00001909</p></td>
<td width="52.347%"><p>Provider context (index) invalid: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>776</p></td>
<td width="21.039%"><p>00001910</p></td>
<td width="52.347%"><p>Provider context (index) invalid: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>777</p></td>
<td width="21.039%"><p>00001911</p></td>
<td width="52.347%"><p>Provider context (index) invalid: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>7d2</p></td>
<td width="21.039%"><p>00002002</p></td>
<td width="52.347%"><p>Provider context (update) invalid: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>7d3</p></td>
<td width="21.039%"><p>00002003</p></td>
<td width="52.347%"><p>Provider context (update) invalid: dynamic allocation of
the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>7d4</p></td>
<td width="21.039%"><p>00002004</p></td>
<td width="52.347%"><p>Provider context (update) invalid: incorrect attribute
string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>7d5</p></td>
<td width="21.039%"><p>00002005</p></td>
<td width="52.347%"><p>Provider context (update) invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>7d6</p></td>
<td width="21.039%"><p>00002006</p></td>
<td width="52.347%"><p>Provider context (update) invalid: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>7d7</p></td>
<td width="21.039%"><p>00002007</p></td>
<td width="52.347%"><p>Provider context (update) invalid: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>7d8</p></td>
<td width="21.039%"><p>00002008</p></td>
<td width="52.347%"><p>Provider context (update) invalid: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>7d9</p></td>
<td width="21.039%"><p>00002009</p></td>
<td width="52.347%"><p>Provider context (update) invalid: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>7da</p></td>
<td width="21.039%"><p>00002010</p></td>
<td width="52.347%"><p>Provider context (update) invalid: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>7db</p></td>
<td width="21.039%"><p>00002011</p></td>
<td width="52.347%"><p>Provider context (update) invalid: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>836</p></td>
<td width="21.039%"><p>00002102</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>837</p></td>
<td width="21.039%"><p>00002103</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: dynamic allocation of
the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>838</p></td>
<td width="21.039%"><p>00002104</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: incorrect attribute
string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>839</p></td>
<td width="21.039%"><p>00002105</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>83a</p></td>
<td width="21.039%"><p>00002106</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>83b</p></td>
<td width="21.039%"><p>00002107</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>83c</p></td>
<td width="21.039%"><p>00002108</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>83d</p></td>
<td width="21.039%"><p>00002109</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>83e</p></td>
<td width="21.039%"><p>00002110</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>83f</p></td>
<td width="21.039%"><p>00002111</p></td>
<td width="52.347%"><p>Provider context (delete) invalid: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>89a</p></td>
<td width="21.039%"><p>00002202</p></td>
<td width="52.347%"><p>Context release problem: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>89b</p></td>
<td width="21.039%"><p>00002203</p></td>
<td width="52.347%"><p>Context release problem: dynamic allocation of the data
area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>89c</p></td>
<td width="21.039%"><p>00002204</p></td>
<td width="52.347%"><p>Context release problem: incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>89d</p></td>
<td width="21.039%"><p>00002205</p></td>
<td width="52.347%"><p>Context release problem: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>89e</p></td>
<td width="21.039%"><p>00002206</p></td>
<td width="52.347%"><p>Context release problem: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>89f</p></td>
<td width="21.039%"><p>00002207</p></td>
<td width="52.347%"><p>Context release problem: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>8a0</p></td>
<td width="21.039%"><p>00002208</p></td>
<td width="52.347%"><p>Context release problem: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>8a1</p></td>
<td width="21.039%"><p>00002209</p></td>
<td width="52.347%"><p>Context release problem: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>8a2</p></td>
<td width="21.039%"><p>00002210</p></td>
<td width="52.347%"><p>Context release problem: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>8a3</p></td>
<td width="21.039%"><p>00002211</p></td>
<td width="52.347%"><p>Context release problem: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>8fe</p></td>
<td width="21.039%"><p>00002302</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>8ff</p></td>
<td width="21.039%"><p>00002303</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
dynamic allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>900</p></td>
<td width="21.039%"><p>00002304</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>901</p></td>
<td width="21.039%"><p>00002305</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>902</p></td>
<td width="21.039%"><p>00002306</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>903</p></td>
<td width="21.039%"><p>00002307</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>904</p></td>
<td width="21.039%"><p>00002308</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>905</p></td>
<td width="21.039%"><p>00002309</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>906</p></td>
<td width="21.039%"><p>00002310</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>907</p></td>
<td width="21.039%"><p>00002311</p></td>
<td width="52.347%"><p>Provider context invalid for a Ready To Receive Request:
end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>962</p></td>
<td width="21.039%"><p>00002402</p></td>
<td width="52.347%"><p>Socket reference invalid: dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>963</p></td>
<td width="21.039%"><p>00002403</p></td>
<td width="52.347%"><p>Socket reference invalid: dynamic allocation of the data
area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>964</p></td>
<td width="21.039%"><p>00002404</p></td>
<td width="52.347%"><p>Socket reference invalid: incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>965</p></td>
<td width="21.039%"><p>00002405</p></td>
<td width="52.347%"><p>Socket reference invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>966</p></td>
<td width="21.039%"><p>00002406</p></td>
<td width="52.347%"><p>Socket reference invalid: manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>967</p></td>
<td width="21.039%"><p>00002407</p></td>
<td width="52.347%"><p>Socket reference invalid: contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>968</p></td>
<td width="21.039%"><p>00002408</p></td>
<td width="52.347%"><p>Socket reference invalid: table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>969</p></td>
<td width="21.039%"><p>00002409</p></td>
<td width="52.347%"><p>Socket reference invalid: no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>96a</p></td>
<td width="21.039%"><p>00002410</p></td>
<td width="52.347%"><p>Socket reference invalid: context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>96b</p></td>
<td width="21.039%"><p>00002411</p></td>
<td width="52.347%"><p>Socket reference invalid: end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>9c6</p></td>
<td width="21.039%"><p>00002502</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: dynamic
table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>9c7</p></td>
<td width="21.039%"><p>00002503</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: dynamic
allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>9c8</p></td>
<td width="21.039%"><p>00002504</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: incorrect
attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>9c9</p></td>
<td width="21.039%"><p>00002505</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>9ca</p></td>
<td width="21.039%"><p>00002506</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: manager
not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>9cb</p></td>
<td width="21.039%"><p>00002507</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: contexts
still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>9cc</p></td>
<td width="21.039%"><p>00002508</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: table access
denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>9cd</p></td>
<td width="21.039%"><p>00002509</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: no more
managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>9ce</p></td>
<td width="21.039%"><p>00002510</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: context
does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>9cf</p></td>
<td width="21.039%"><p>00002511</p></td>
<td width="52.347%"><p>Provider context (asynchronous return) invalid: end of
table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a2a</p></td>
<td width="21.039%"><p>00002602</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: dynamic
table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a2b</p></td>
<td width="21.039%"><p>00002603</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: dynamic
allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a2c</p></td>
<td width="21.039%"><p>00002604</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: incorrect
attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a2d</p></td>
<td width="21.039%"><p>00002605</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: call
parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a2e</p></td>
<td width="21.039%"><p>00002606</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: manager
not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a2f</p></td>
<td width="21.039%"><p>00002607</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: contexts
still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a30</p></td>
<td width="21.039%"><p>00002608</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: table
access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a31</p></td>
<td width="21.039%"><p>00002609</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: no
more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a32</p></td>
<td width="21.039%"><p>00002610</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: context
does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a33</p></td>
<td width="21.039%"><p>00002611</p></td>
<td width="52.347%"><p>Socket reference invalid for an Indication Datagram: end
of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a8e</p></td>
<td width="21.039%"><p>00002702</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: dynamic
table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a8f</p></td>
<td width="21.039%"><p>00002703</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: dynamic
allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a90</p></td>
<td width="21.039%"><p>00002704</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: incorrect
attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a91</p></td>
<td width="21.039%"><p>00002705</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: call
parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a92</p></td>
<td width="21.039%"><p>00002706</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: manager
not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a93</p></td>
<td width="21.039%"><p>00002707</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: contexts
still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a94</p></td>
<td width="21.039%"><p>00002708</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: table
access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a95</p></td>
<td width="21.039%"><p>00002709</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: no more
managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>a96</p></td>
<td width="21.039%"><p>00002710</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: context
does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>a97</p></td>
<td width="21.039%"><p>00002711</p></td>
<td width="52.347%"><p>Search for a free context in the connection table: end
of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>af2</p></td>
<td width="21.039%"><p>00002802</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
dynamic table allocation</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>af3</p></td>
<td width="21.039%"><p>00002803</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
dynamic allocation of the data area</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>af4</p></td>
<td width="21.039%"><p>00002804</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
incorrect attribute string</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>af5</p></td>
<td width="21.039%"><p>00002805</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
call parameter</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>af6</p></td>
<td width="21.039%"><p>00002806</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
manager not running</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>af7</p></td>
<td width="21.039%"><p>00002807</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
contexts still active</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>af8</p></td>
<td width="21.039%"><p>00002808</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
table access denied</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>af9</p></td>
<td width="21.039%"><p>00002809</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
no more managers available</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>afa</p></td>
<td width="21.039%"><p>00002810</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
context does not exist</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>afb</p></td>
<td width="21.039%"><p>00002811</p></td>
<td width="52.347%"><p>Search for a free context in the Register context table:
end of table reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>bb9</p></td>
<td width="21.039%"><p>00003001</p></td>
<td width="52.347%"><p>Error during TCP/IP process creation: incorrect task name</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>bba</p></td>
<td width="21.039%"><p>00003002</p></td>
<td width="52.347%"><p>Error during TCP/IP process creation: definition error</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>bbb</p></td>
<td width="21.039%"><p>00003003</p></td>
<td width="52.347%"><p>Error during TCP/IP process creation: insufficient memory</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>bc1</p></td>
<td width="21.039%"><p>00003009</p></td>
<td width="52.347%"><p>Error during TCP/IP process creation: general problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>c1d</p></td>
<td width="21.039%"><p>00003101</p></td>
<td width="52.347%"><p>Queue acquisition error (queue-based communication between
CFTTCP and CFTTPRO): invalid queue</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>c1e</p></td>
<td width="21.039%"><p>00003102</p></td>
<td width="52.347%"><p>Queue acquisition error (queue-based communication between
CFTTCP and CFTTPRO): time-out</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>c1f</p></td>
<td width="21.039%"><p>00003103</p></td>
<td width="52.347%"><p>Queue acquisition error (queue-based communication between
CFTTCP and CFTTPRO): queue deleted</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>c25</p></td>
<td width="21.039%"><p>00003109</p></td>
<td width="52.347%"><p>Queue acquisition error (queue-based communication between
CFTTCP and CFTTPRO): general problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>c80</p></td>
<td width="21.039%"><p>00003200</p></td>
<td width="52.347%"><p>CFTTCP initialization error (tmbeg)</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>ce5</p></td>
<td width="21.039%"><p>00003301</p></td>
<td width="52.347%"><p>CFTTCP initialization error (tmstat): incorrect task</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>ced</p></td>
<td width="21.039%"><p>00003309</p></td>
<td width="52.347%"><p>CFTTCP initialization error (tmstat): general problem</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dad</p></td>
<td width="21.039%"><p>00003501</p></td>
<td width="52.347%"><p>Queue error in Data Indication: invalid queue reference</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dae</p></td>
<td width="21.039%"><p>00003502</p></td>
<td width="52.347%"><p>Queue error in Data Indication: counter capacity exceeded</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>daf</p></td>
<td width="21.039%"><p>00003503</p></td>
<td width="52.347%"><p>Queue error in Data Indication: control message or data
too large</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>db0</p></td>
<td width="21.039%"><p>00003504</p></td>
<td width="52.347%"><p>Queue error in Data Indication: invalid mode</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>db5</p></td>
<td width="21.039%"><p>00003509</p></td>
<td width="52.347%"><p>Queue error in Data Indication: general problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>db7</p></td>
<td width="21.039%"><p>00003511</p></td>
<td width="52.347%"><p>Queue error in Connect Reject Indication: invalid queue
reference</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>db8</p></td>
<td width="21.039%"><p>00003512</p></td>
<td width="52.347%"><p>Queue error in Connect Reject Indication: counter capacity
exceeded</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>db9</p></td>
<td width="21.039%"><p>00003513</p></td>
<td width="52.347%"><p>Queue error in Connect Reject Indication: control message
or data too large</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dba</p></td>
<td width="21.039%"><p>00003514</p></td>
<td width="52.347%"><p>Queue error in Connect Reject Indication: invalid mode</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dbf</p></td>
<td width="21.039%"><p>00003519</p></td>
<td width="52.347%"><p>Queue error in Connect Reject Indication: general problem</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dc1</p></td>
<td width="21.039%"><p>00003521</p></td>
<td width="52.347%"><p>Queue error in Release Indication: invalid queue reference</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dc2</p></td>
<td width="21.039%"><p>00003522</p></td>
<td width="52.347%"><p>Queue error in Release Indication: counter capacity exceeded</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dc3</p></td>
<td width="21.039%"><p>00003523</p></td>
<td width="52.347%"><p>Queue error in Release Indication: control message or data
too large</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dc4</p></td>
<td width="21.039%"><p>00003524</p></td>
<td width="52.347%"><p>Queue error in Release Indication: invalid mode</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dc9</p></td>
<td width="21.039%"><p>00003529</p></td>
<td width="52.347%"><p>Queue error in Release Indication: general problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dcb</p></td>
<td width="21.039%"><p>00003531</p></td>
<td width="52.347%"><p>Queue error in Connect Accept Indication: invalid queue
reference</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dcc</p></td>
<td width="21.039%"><p>00003532</p></td>
<td width="52.347%"><p>Queue error in Connect Accept Indication: counter capacity
exceeded</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dcd</p></td>
<td width="21.039%"><p>00003533</p></td>
<td width="52.347%"><p>Queue error in Connect Accept Indication: control message
or data too large</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dce</p></td>
<td width="21.039%"><p>00003534</p></td>
<td width="52.347%"><p>Queue error in Connect Accept Indication: invalid mode</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dd3</p></td>
<td width="21.039%"><p>00003539</p></td>
<td width="52.347%"><p>Queue error in Connect Accept Indication: general problem</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dd5</p></td>
<td width="21.039%"><p>00003541</p></td>
<td width="52.347%"><p>Queue error in Indication Datagram: invalid queue reference</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dd6</p></td>
<td width="21.039%"><p>00003542</p></td>
<td width="52.347%"><p>Queue error in Indication Datagram: counter capacity exceeded</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>dd7</p></td>
<td width="21.039%"><p>00003543</p></td>
<td width="52.347%"><p>Queue error in Indication Datagram: control message or
data too large</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dd8</p></td>
<td width="21.039%"><p>00003544</p></td>
<td width="52.347%"><p>Queue error in Indication Datagram: invalid mode</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>ddd</p></td>
<td width="21.039%"><p>00003549</p></td>
<td width="52.347%"><p>Queue error in Indication Datagram: general problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>ddf</p></td>
<td width="21.039%"><p>00003551</p></td>
<td width="52.347%"><p>Queue error in Connect Indication: invalid queue reference</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>de0</p></td>
<td width="21.039%"><p>00003552</p></td>
<td width="52.347%"><p>Queue error in Connect Indication: counter capacity exceeded</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>de1</p></td>
<td width="21.039%"><p>00003553</p></td>
<td width="52.347%"><p>Queue error in Connect Indication: control message or data
too large</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>de2</p></td>
<td width="21.039%"><p>00003554</p></td>
<td width="52.347%"><p>Queue error in Connect Indication: invalid mode</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>de7</p></td>
<td width="21.039%"><p>00003559</p></td>
<td width="52.347%"><p>Queue error in Connect Indication: general problem</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>de9</p></td>
<td width="21.039%"><p>00003561</p></td>
<td width="52.347%"><p>Queue error in Ready To Receive Indication: invalid queue
reference</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dea</p></td>
<td width="21.039%"><p>00003562</p></td>
<td width="52.347%"><p>Queue error in Ready To Receive Indication: counter capacity
exceeded</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>deb</p></td>
<td width="21.039%"><p>00003563</p></td>
<td width="52.347%"><p>Queue error in Ready To Receive Indication: control message
or data too large</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>dec</p></td>
<td width="21.039%"><p>00003564</p></td>
<td width="52.347%"><p>Queue error in Ready To Receive Indication: invalid mode</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>df1</p></td>
<td width="21.039%"><p>00003569</p></td>
<td width="52.347%"><p>Queue error in Ready To Receive Indication: general problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td>0000eb68</td>
<td width="21.039%">00060264</td>
<td width="52.347%">ECONNREFUSED: The attempt to connect was rejected</td>
</tr>
</tbody>
</table>
