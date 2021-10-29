{
    "title": "Partners - CFTPART ",
    "linkTitle": "CFTPART - Defining partners",
    "weight": "420"
}This page describes how to define the Partners object (CFTPART ) to set partner
characteristics. Use this command to describe partner characteristics.

See also:

-   Command syntax
    [CFTPART](../../command_summary)
-   Object concepts
    Defining partners

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/comment.htm">COMMENT</a> </p>         </td>
         <td>            <p>Local comment associated with the partner.</p>
            <p>Not used during transfers. May be queried, for example
by the LISTPART command. It can consequently be used to locally associate
a long text (description in plain language) with the partner.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/commut.htm">COMMUT</a> </p>
            <p>Only
applicable for a store and forward site</p>         </td>
         <td>            <p>Type of switching supported for this partner.</p>
            <p>The following types are possible:</p>
            <ul>
               <li>YES:
corresponds to "store and forward" switching               </li>
               <li>SERVER:
corresponds to "VAN server switching"               </li>
               <li>NO: switching
is refused for this partner               </li>
               <li>PART: store
and forward mode is forced in server mode if the recipient specified in
the IPART parameter is not the final receiver               </li>
            </ul>
            <p>Processing according to the switching type
is described in Transfer with routing
- Store and forward.</p>         </td>
      </tr>
      <tr class="odd">
         <td>COS         </td>
         <td>Class of service parameter as it relates to bandwidth control.         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/ctrlpart.htm">CTRLPART</a></p>         </td>
         <td>Optional parameter that is relevant only in server mode. When a transfer is initiated by a remote partner, Transfer CFT always controls its identity. If the remote sender is not the initial sender, store and forward mode, the Transfer CFT can choose to control the initial sender identity according to CTRLPART parameter.         </td>
      </tr>
      <tr class="odd">
         <td><a href="../Parameter_index/fcharset.htm">FCHARSET</a>         </td>
         <td>Defines the local file encoding. See also <a href="../Parameter_index/ncharset.htm">ncharset.</a>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/fprefix.htm">FPREFIX</a></p>         </td>
         <td>            <p>File name.</p>
            <p>This parameter is used to associate a
file name with a partner. During a send or receive operation (CFTSEND
or SEND, CFTRECV or RECV), this file name is concatenated with the name
specified in the FNAME parameter.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/group.htm">GROUP</a> </p>         </td>
         <td>            <p>Group the partner belongs to.</p>
            <p>This parameter is used to locally define the symbolic variable
&amp;GROUP.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/id.htm">ID</a> </p>         </td>
         <td>            <p>Local partner identifier.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/idf.htm">IDF</a> </p>         </td>
         <td>            <p>Default identifier of the file for the partner.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/imaxtime.htm">IMAXTIME</a></p>         </td>
         <td>            <p>Maximum time after which the partner cannot call.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>IMINTIME </p>         </td>
         <td>            <p>Minimum time before which the partner cannot call.</p>
            <p>IMINTIME and IMAXTIME define the time slot during which
the partner calls the Transfer CFT monitor (incoming calls).</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/ipart.htm">IPART</a></p>         </td>
         <td>            <p>Local identifier of an intermediate partner.</p>         </td>
      </tr>
      <tr class="odd">
         <td><a href="../NACK.htm">NACK</a>         </td>
         <td>            <p>PeSIT</p>
            <p>Enables or disables the negative acknowledgement feature.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/npart.htm">NRPART</a></p>         </td>
         <td>            <p>Partner network identifier identifying the partner for
incoming calls.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/nrpassw.htm">NRPASSW</a> </p>         </td>
         <td>            <p>Partner sign-on password, authorizing a local site access
right check.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/nspart.htm">NSPART</a> </p>         </td>
         <td>            <p>Network identifier by which the local Transfer CFT monitor
identifies itself to its partner.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/nspassw.htm">NSPASSW</a></p>         </td>
         <td>            <p>Password by which the Transfer CFT monitor identifies itself
to the partner.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/omaxtime.htm">OMAXTIME</a></p>         </td>
         <td>            <p>Maximum time after which the partner can no longer
be called.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/omintime.htm">OMINTIME</a> </p>         </td>
         <td>            <p>Minimum time before which the partner may not be called.</p>
            <p>OMINTIME and OMAXTIME define the time slot during which
the Transfer CFT can call this partner (outgoing calls).</p>
            <p>A time slot of zero means that the Transfer CFT monitor
cannot call the partner directly; it then implements the store and forward
mechanism by calling the intermediate site (IPART parameter).</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/prot.htm">PROT</a> </p>         </td>
         <td>            <p>List of communication protocols (CFTPROT ID identifiers)
authorized to communicate with this partner.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/rauth.htm">RAUTH</a> </p>         </td>
         <td>            <p>Identifier (ID parameter) of the CFTAUTH command designating
a list of IDFs authorized for the receive transfers with this partner.</p>
            <p>RAUTH=* means that all the model files (all the IDFs) may
be received.</p>
            <p>The identifier values beginning with the characters
‘NOT’ designate lists of unauthorized IDFs (see the CFTAUTH command).</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/sap.htm">SAP</a> </p>         </td>
         <td>            <p>Values of the remote SAPs, service access points, associated
with each of the protocols defined by the PROT parameter.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/sauth.htm">SAUTH</a> </p>         </td>
         <td>            <p>Identifier (ID parameter) of the CFTAUTH command designating
a list of IDFs authorized for send transfers to this partner.</p>
            <p>SAUTH =* means that all model files (all IDFs) may be sent.</p>
            <p>The identifier values beginning with the characters ‘NOT’
designate lists of unauthorized IDFs (see CFTAUTH ).</p>         </td>
      </tr>
      <tr class="even">
         <td>SSH         </td>
         <td>Associates a security profile with a partner definition.         </td>
      </tr>
      <tr class="odd">
         <td><a href="../Parameter_index/ssl.htm">SSL</a>         </td>
         <td>The parameter used to associate a security profile with a partner definition.         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/state.htm">STATE</a> </p>         </td>
         <td>            <p>Partner state.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/syst.htm">SYST</a> </p>         </td>
         <td>            <p>Type of operating system supporting the partner.</p>
            <p>If this parameter is not defined, the partner is considered
to have the same operating system as the local computer.</p>
            <p>This parameter allows the monitor:</p>
            <ul>
               <li>To find
the data code on the partner computer (see the comment for the FCODE parameter
of the <a href="../../GUI/Concepts/Translation_table_concepts.htm">CFTXLATE</a>
command)               </li>
               <li>To declare
the file type, in this profile and when the partner is the receiver, in terms of its operating system,
to the partner Transfer CFT (NTYPE parameter)               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>            <p><a href="../Parameter_index/trk.htm">TRK</a></p>         </td>
         <td>            <p>Specification of how much detail Transfer CFT provides
Sentinel about transfers. Transfer CFT sends detail about the transfers
in the form of tracked instances.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p><a href="../Parameter_index/xlate.htm">XLATE</a> </p>         </td>
         <td>            <p>Identifier of the translation table used for transfers
with this partner.</p>
            <p>The translation table is defined by the CFTXLATE ID= &lt;xlate&gt;
object.</p>
            <p>If this parameter is not defined, the translation tables
may also be specified in the SEND/CFTSEND (or RECV/CFTRECV) commands.
If these tables are not defined in these commands, the CFTXLATE command
ID=&lt;default&gt; specifies them by default. If this command is not included
for messages as well as for files, the translation tables that are internal
to the monitor are used.</p>
            <p>See also <a href="../../GUI/Concepts/Translation_table_concepts.htm">Conversion tables: Translation</a>.  </p>         </td>
      </tr>
   </tbody>
</table>

## CFTUTIL example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTPART     MODE =    
CREATE,<br />
     ID =     PARIS5,    
/* Partner identifier      */<br />
     PROT =     PSITCFT,    
/* Only one communication protocol<br />
                                   
-&gt; see CFTPROT      */<br />
     SAP =     13,          
/*      */<br />
     RAUTH =     RECPAR5,    
/* The files authorized to be received<br />
                                     
--&gt; see CFTAUTH      */<br />
     NRPART =     BULLDPS,    
/* Name and password that the     */<br />
     NRPASSW =     44NTS,    
/* partner submits at connection time  */<br />
     NSPART =     LOCALCFT,/*
Name and password that CFT     */<br />
     NSPASSW =     75P015,   
/* submits to the partner on connection */<br />
     IMINTIME =     0700,      /*
Only able to call between     */<br />
     IMAXTIME =     0900,        /*
7:00 and 9:00     */<br />
     OMINTIME =     1000,          /*
May only be called between      */<br />
     OMAXTIME =     1200    
,          /* 10:00
and midday      */         </td>
      </tr>
   </tbody>
</table>

The SAUTH parameter is omitted. The partner can then send any IDF to
the local Transfer CFT, while it is only authorized to receive
the files which have been assigned an IDF included in the RECPAR5 list
defined by a CFTAUTH object.

As the SYST parameter is not specified, Transfer CFT considers that its
partner is the same computer. The data code is consequently not converted
and the file types sent are not translated.
