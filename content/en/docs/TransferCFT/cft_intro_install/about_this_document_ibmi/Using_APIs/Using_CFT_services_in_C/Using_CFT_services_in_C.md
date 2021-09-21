{
    "title": "About services in C",
    "linkTitle": "About services in C",
    "weight": "310"
}# <span id="Using_CFT_services_in_C__Start_here"></span>About Transfer CFT services in C

This section begins with this topic which provides information about using
the Transfer CFT services in C language. It also contains topics
that describe how to use the following services in
C language.

This page describes the Transfer
CFT programming interface. The programming interface is implemented by
the calling application module link, with the Transfer CFT interface function
modules.

The library of object modules supplied provides everything the programmer
can requires. This library also contains the file cftapi.h
to be included in the application using the Transfer CFT programming interfaces.

## <span id="Call_Syntax"></span>Call syntax

<table cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td width="22.133%">
            <p>Syntax</p>
         </td>
         <td width="77.867%">
            <p>rc = cftxx (verb,&amp;ptr,param)</p>
         </td>
      </tr>
      <tr valign="top">
         <td bgcolor="#C0C0C0" width="22.133%">
            <p>Element</p>
         </td>
         <td bgcolor="#C0C0C0" width="77.867%">
            <p>Definition</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="22.133%">
            <p>cftxx</p>
         </td>
         <td width="77.867%">
            <p><span>cftai</span>: simple Transfer 
 CFT catalog querying services</p>
            <p><span>cftaix</span>: extended 
  <span>Transfer CFT</span> catalog querying services</p>
            <p><span>cftau</span>:  transfer 
 services with syntax analysis</p>
            <p><span>cftac</span>: transfer 
 services without syntax analysis</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="22.133%">
            <p><b><span>verb</span></b>
</p>
         </td>
         <td colspan="1" rowspan="1" width="77.867%">
            <p>Service requested</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="22.133%">
            <p>ptr</p>
         </td>
         <td colspan="1" rowspan="1" width="77.867%">
            <p>Address of the internal control block</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="22.133%">
            <p>param</p>
         </td>
         <td colspan="1" rowspan="1" width="77.867%">
            <p>Parameters specific to the requested service</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>rc</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Return code</p>
         </td>
      </tr>
</table>

### Return codes

The return codes are returned by the programming interfaces in the form
of mnemonics.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">It is strongly recommended that you test the return codes of services 
 provided by the  <span>Transfer CFT</span> programming interfaces through mnemonics. 
 The corresponding values may change without notice.         </td>
      </tr>
</table>

The return codes are listed in the cftapi.h source file.
