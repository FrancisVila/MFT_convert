{
    "title": "Using services in C",
    "linkTitle": "Using services in C",
    "weight": "320"
}# <span id="Using_CFT_services_in_C__Start_here"></span>About Transfer CFT services in C



This section begins with this topic which provides information about using

the <span>Transfer CFT</span> services in C language. It also contains topics

that describe how to use the following services in

C language.



This page describes the Transfer

CFT programming interface. The programming interface is implemented by

the calling application module link, with the <span>Transfer CFT</span> interface function

modules.



The library of object modules supplied provides everything the programmer

can requires. This library also contains the file cftapi.h

to be included in the application using the <span>Transfer CFT</span> programming interfaces.



## <span id="Call_Syntax"></span>Call syntax



<table data-cellspacing="0" width="90%">
<colgroup>
<col/>
<col/>
</colgroup>
<tbody>
<tr data-valign="top">
<td width="22.133%"><p>Syntax</p></td>
<td width="77.867%"><p>rc = cftxx (verb,&amp;ptr,param)</p></td>
</tr>
<tr data-valign="top">
<td data-bgcolor="#C0C0C0" width="22.133%"><p>Element</p></td>
<td data-bgcolor="#C0C0C0" width="77.867%"><p>Definition</p></td>
</tr>
<tr data-valign="top">
<td width="22.133%"><p>cftxx</p></td>
<td width="77.867%"><p><span>cftai</span>: simple Transfer

CFT catalog querying services</p>
<p><span>cftaix</span>: extended

<span>Transfer CFT</span> catalog querying services</p>
<p><span>cftau</span>:  transfer

services with syntax analysis</p>
<p><span>cftac</span>: transfer

services without syntax analysis</p></td>
</tr>
<tr data-valign="top">
<td width="22.133%"><p><strong><span>verb</span></strong></p></td>
<td width="77.867%"><p>Service requested</p></td>
</tr>
<tr data-valign="top">
<td width="22.133%"><p>ptr</p></td>
<td width="77.867%"><p>Address of the internal control block</p></td>
</tr>
<tr data-valign="top">
<td width="22.133%"><p>param</p></td>
<td width="77.867%"><p>Parameters specific to the requested service</p></td>
</tr>
<tr>
<td><p>rc</p></td>
<td><p>Return code</p></td>
</tr>
</tbody>
</table>



### Return codes



The return codes are returned by the programming interfaces in the form

of mnemonics.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">It is strongly recommended that you test the return codes of services

provided by the <span>Transfer CFT</span> programming interfaces through mnemonics.

The corresponding values may change without notice.</td>
</tr>
</tbody>
</table>



The return codes are listed in the cftapi.h source file.

