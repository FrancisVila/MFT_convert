{
    "title": "Environment variables file",
    "linkTitle": "Environment variables file",
    "weight": "190"
}You must define the environment variables in the ..UPARM (CNFENV) file with the DDname STDENV.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The ENVAR runtime option is: <span>envar("_CEE_ENVFILE_S=DD:STDENV"</span>.         </td>
      </tr>
</table>

This file must contain the following definition: CFTUCONF=dd:UCONF (initialized when creating the instance - do not change this value).

You can modify this file to, for example, obtain traces, set the stack TCP/IP, etc.

When you start Transfer CFT, some parameters are printed in the transfer CFT LOG. For example:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTI18I+Environment variables (platform dependant) (DDname:STDENV)</p>
            <p>CFTI18I+   CFTUCONF=dd:UCONF</p>
            <p>CFTI18I+   _BPXK_SETIBMOPT_TRANSPORT=TCPIP</p>
         </td>
      </tr>
   </tbody>
</table>
