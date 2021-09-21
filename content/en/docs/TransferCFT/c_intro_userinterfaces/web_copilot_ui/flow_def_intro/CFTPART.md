{
    "title": "Partners - CFTPART",
    "linkTitle": "Partners - CFTPART",
    "weight": "190"
}# <span id="kanchor24"></span><span id="Defining_partners__command_line_"></span>Partners - CFTPART

This page describes how to define the Partners object (CFTPART ) to set partner
characteristics. Use this command to describe partner characteristics.

See also:

-   Command syntax
    [CFTPART](../../../command_summary)
-   Object concepts
    [Defining partners](defining_partners_concepts.htm)

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/comment">COMMENT</a> </p>
         </td>
         <td>
            <p>Local comment associated with the partner.</p>
            <p>Not used during transfers. May be queried, for example 
 by the LISTPART command. It can consequently be used to locally associate 
 a long text (description in plain language) with the partner.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/commut">COMMUT</a> </p>
            <p>Only 
 applicable for a store and forward site</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Type of switching supported for this partner.</p>
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
 - Store and forward.</p>
         </td>
      </tr>
      <tr>
         <td><a href="cos.htm">COS</a>
         </td>
         <td>Class of service parameter as it relates to bandwidth control.         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/ctrlpart">CTRLPART</a>
</p>
         </td>
         <td colspan="1" rowspan="1">Optional parameter that is relevant only in server mode. When a transfer is initiated by a remote partner, Transfer CFT always controls its identity. If the remote sender is not the initial sender, store and forward mode, the Transfer CFT can choose to control the initial sender identity according to CTRLPART parameter.         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/fcharset">FCHARSET</a>
         </td>
         <td>Defines the local file  encoding. See also <a href="../../../command_summary/parameter_intro/ncharset">ncharset.</a>         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/fprefix">FPREFIX</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File name.</p>
            <p>This parameter is used to associate a 
 file name with a partner. During a send or receive operation (CFTSEND 
 or SEND, CFTRECV or RECV), this file name is concatenated with the name 
 specified in the FNAME parameter.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/group">GROUP</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Group the partner belongs to.</p>
            <p>This parameter is used to locally define the symbolic variable 
 &amp;GROUP.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local partner identifier.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Default identifier of the file for the partner.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/imaxtime">IMAXTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum time after which the partner cannot call.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="imintime.htm">IMINTIME</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Minimum time before which the partner cannot call.</p>
            <p>IMINTIME and IMAXTIME define the time slot during which 
 the partner calls the Transfer CFT monitor (incoming calls).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/ipart">IPART</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local identifier of an intermediate partner.</p>
         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/nack">NACK</a>
         </td>
         <td>
            <p>PeSIT</p>
            <p>Enables or disables the negative acknowledgement feature.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/npart">NRPART</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner network identifier identifying the partner for 
 incoming calls.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/nrpassw">NRPASSW</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner sign-on password, authorizing a local site access 
 right check.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/nspart">NSPART</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Network identifier by which the local Transfer CFT monitor 
 identifies itself to its partner.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/nspassw">NSPASSW</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Password by which the Transfer CFT monitor identifies itself 
 to the partner.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/omaxtime">OMAXTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum time after which the partner can no longer 
 be called.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/omintime">OMINTIME</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Minimum time before which the partner may not be called.</p>
            <p>OMINTIME and OMAXTIME define the time slot during which 
 the Transfer CFT can call this partner (outgoing calls).</p>
            <p>A time slot of zero means that the Transfer CFT monitor 
 cannot call the partner directly; it then implements the store and forward 
 mechanism by calling the intermediate site (IPART parameter).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/prot">PROT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>List of communication protocols (CFTPROT ID identifiers) 
 authorized to communicate with this partner.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/rauth">RAUTH</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier (ID parameter) of the CFTAUTH command designating 
 a list of IDFs authorized for the receive transfers with this partner.</p>
            <p>RAUTH=* means that all the model files (all the IDFs) may 
 be received.</p>
            <p>The identifier values beginning with the characters 
 ‘NOT’ designate lists of unauthorized IDFs (see the CFTAUTH command).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/sap">SAP</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Values of the remote SAPs, service access points, associated 
 with each of the protocols defined by the PROT parameter.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/sauth">SAUTH</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier (ID parameter) of the CFTAUTH command designating 
 a list of IDFs authorized for send transfers to this partner.</p>
            <p>SAUTH =* means that all model files (all IDFs) may be sent.</p>
            <p>The identifier values beginning with the characters ‘NOT’ 
 designate lists of unauthorized IDFs (see CFTAUTH ).</p>
         </td>
      </tr>
      <tr>
         <td><a href="ssh.htm">SSH</a>
         </td>
         <td>Associates a security profile with a partner definition.         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/ssl">SSL</a>
         </td>
         <td>The parameter used to associate a security profile with a partner definition.         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/state">STATE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner state.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/syst">SYST</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Type of operating system supporting the partner.</p>
            <p>If this parameter is not defined, the partner is considered 
 to have the same operating system as the local computer.</p>
            <p>This parameter allows the monitor:</p>
            <ul>
               <li>To find 
 the data code on the partner computer (see the comment for the FCODE parameter 
 of the <a href="../../../../concepts/cft_configuration_concepts_start_here/translation_table_concepts">CFTXLATE</a> 
 command)                </li>
               <li>To declare 
 the file type, in this profile and when the partner is the receiver, in terms of its operating system, 
 to the partner Transfer CFT (NTYPE parameter)               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/trk">TRK</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Specification of how much detail Transfer CFT provides 
 Sentinel about transfers. Transfer CFT sends detail about the transfers 
 in the form of tracked instances.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/xlate">XLATE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier of the translation table used for transfers 
 with this partner.</p>
            <p>The translation table is defined by the CFTXLATE ID= &lt;xlate&gt; 
 object.</p>
            <p>If this parameter is not defined, the translation tables 
 may also be specified in the SEND/CFTSEND (or RECV/CFTRECV) commands. 
 If these tables are not defined in these commands, the CFTXLATE command 
 ID=&lt;default&gt; specifies them by default. If this command is not included 
 for messages as well as for files, the translation tables that are internal 
 to the monitor are used.</p>
            <p>See also   <a href="../../../../concepts/cft_configuration_concepts_start_here/translation_table_concepts">Conversion tables: Translation</a>.  </p>
         </td>
      </tr>
   </tbody>
</table>

## CFTUTIL example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTPART     MODE =     
 CREATE,<br/>     ID =     PARIS5,     
 /* Partner identifier      */<br/>     PROT =     PSITCFT,     
 /* Only one communication protocol<br/>                                    
 -&gt; see CFTPROT      */<br/>     SAP =     13,           
 /*      */<br/>     RAUTH =     RECPAR5,     
 /* The files authorized to be received<br/>                                      
 --&gt; see CFTAUTH      */<br/>     NRPART =     BULLDPS,     
 /* Name and password that the     */<br/>     NRPASSW =     44NTS,     
 /* partner submits at connection time  */<br/>     NSPART =     LOCALCFT,/* 
 Name and password that CFT     */<br/>     NSPASSW =     75P015,    
 /* submits to the partner on connection */<br/>     IMINTIME =     0700,      /* 
 Only able to call between     */<br/>     IMAXTIME =     0900,        /* 
 7:00 and 9:00     */<br/>     OMINTIME =     1000,          /* 
 May only be called between      */<br/>     OMAXTIME =     1200     
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
