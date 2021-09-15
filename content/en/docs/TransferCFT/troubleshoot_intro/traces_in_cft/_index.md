{
    "title": "Using ATM traces",
    "linkTitle": "Using ATM traces",
    "weight": "270"
}This section describes ATM traces and how to implement them.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">ATM traces are only available when using the <span>Local Administration</span> version of Transfer CFT. We recommend using <span>Central Governance</span> to manage <span>Transfer CFT</span>.         </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Topic</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="33.191%">
            <p><a href="trace_management">Trace management 
 concepts</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="66.809%">
            <p>Describes the concepts behind performing an ATM trace in 
 Transfer CFT.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="33.191%">
            <p><a href="parameter_settings">Defining 
 trace in <span>Transfer CFT</span>  parameters</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="66.809%">
            <p>Describes the Transfer CFT general parameter for a trace.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="33.191%">
            <p><a href="defining_a_trace_file_externally">Defining 
 a trace file externally (CFTTRACE utility)</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="66.809%">
            <p>Describes how to create or remove a trace file,  or 
 to reinitialize it with an empty useable content.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="33.191%">
            <p><a href="defining_the_internal_trace_file">Defining 
 the internal trace file (CFTUTIL command)</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="66.809%">
            <p>Describes how to create a trace when Transfer CFT starts, with the possibility of tracing an initialization sequence, or during 
 Transfer CFT operations.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="33.191%">
            <p><a href="start_stop_the_trace.htm">Using the 
 start trace command</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="66.809%">
            <p>Describes the start trace command, which is associated 
 with a unique identifier, defines and describes the conditions for starting 
 and selecting traced data, and associates a file identifier.</p>
         </td>
      </tr>
</table>

## About Transfer CFT traces

Transfer CFT traces are managed by the Advanced
Trace Manager
(ATM) component.

ATM is a problem resolution assistance tool that is used:

-   To save the information
    exchanged at the Transfer CFT level, in one or more dedicated files

The information traced relates to protocol information
(exchanges between Transfer CFT and its remote partners) and/or Transfer
CFT internal information (exchanges between Transfer CFT internal components
or between Transfer CFT tasks).

-   To retrieve and
    interpret previously saved information, through an off-line analysis program

Users are only concerned by ATM in that they may need to initiate tracing,
at the request of the Transfer CFT Support service. The Transfer CFT Support
service is then responsible for analyzing traces.

The next section introduces the concepts
surrounding the trace mechanism and how this works in Transfer CFT.
