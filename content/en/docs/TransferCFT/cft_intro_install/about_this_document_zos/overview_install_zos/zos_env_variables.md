{
    "title": "Environment variables file",
    "linkTitle": "Environment variables file",
    "weight": "190"
}You must define the environment variables in the ..UPARM (CNFENV) file with the DDname STDENV.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The ENVAR runtime option is: <span>envar("_CEE_ENVFILE_S=DD:STDENV"</span>.</td>
</tr>
</tbody>
</table>

This file must contain the following definition: CFTUCONF=dd:UCONF (initialized when creating the instance - do not change this value).

You can modify this file to, for example, obtain traces, set the stack TCP/IP, etc.

When you start Transfer CFT, some parameters are printed in the transfer CFT LOG. For example:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTI18I+Environment variables (platform dependant) (DDname:STDENV)</p>
<p>CFTI18I+ CFTUCONF=dd:UCONF</p>
<p>CFTI18I+ _BPXK_SETIBMOPT_TRANSPORT=TCPIP</p></td>
</tr>
</tbody>
</table>
