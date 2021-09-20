{
    "title": "Expression Language overview",
    "linkTitle": "Expression Language overview",
    "weight": "280"
}Many features of SecureTransport use expressions. The expression language SecureTransport uses is based on the Sun JSP Expression Language. Only the syntax listed in this appendix is supported by SecureTransport, any other syntax is not guaranteed to function properly.

The following SecureTransport features can use the expression language:

-   Transfer site post-transmission actions
-   Subscription post-transmission actions
-   PGP
-   Account templates

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If an account template and its transfer site are defined using expressions, you cannot restart failed transfers for that account template using the <strong>Resubmit</strong> button on the <em>File Tracking</em> page.         </td>
      </tr>
</table>

This appendix provides a list of the supported syntax with examples.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When creating expressions that use file paths you must use the forward slash (/) regardless of the platform where the file path is located. For example, instead of writing <code>c:\tmp\${stenv['loginname']</code>, write <code>c:/tmp/${stenv['loginname']</code>.         </td>
      </tr>
</table>
