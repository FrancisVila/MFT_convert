{
    "title": "Customize the email notification templates",
    "linkTitle": "Customize the email notification templates",
    "weight": "340"
}The templates are located in `<FILEDRIVEHOME>/conf/mailer-templates`. You can customize the email notification template with any text or HTML editor. An HTML editor is recommended because you can use it to preview the notification before deploying it in SecureTransport.

There are seven prerequisite fields that must be set in the XHTML email notification template.

-   `$subject` — The subject line for the email
-   `$mailfrom` — Who the email is coming from
-   `$mailto` — Who the email is going to
-   `$mailserver` — The name of the local SMTP mail server that will be used to deliver the email
-   `$mailserverport` — The TCP port on the SMTP server to connect to.
-   `$smtpUser` — A user to be used when authenticating to an SASL-enabled SMTP server.
-   `$smtpPassword` — Authentication password for the user specified in the `smtpUser` field.

The following code example shows an XHTML file with the prerequisites set:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>&lt;?xml version="1.0" encoding="windows-1252"?&gt;<br/>&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN"<br/>   "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd"&gt;</code>
</p>
            <p><code>&lt;!-- #set( $subject = "ST was unable to deliver a file to<br/>   $DXAGENT_SITE_ATTR_HOST") --&gt;<br/>&lt;!-- #set( $mailfrom = "admin@example.com") --&gt;<br/>&lt;!-- #set( $mailto = $DXAGENT_ACCOUNT_EMAIL) --&gt;<br/>&lt;!-- #set( $mailserver = "mail.example.com") --&gt;<br/>&lt;!-- #set( $<code>mailserverport</code> = "25") --&gt;<br/>&lt;!-- #set( $<code>smtpUser</code> = "user") --&gt;<br/>&lt;!-- #set( $<code>smtpPassword</code> = "password") --&gt;</code>
</p>
            <p><code>&lt;html xmlns="http://www.w3.org/1999/xhtml"&gt;<br/>&lt;head&gt;<br/>   &lt;meta http-equiv="Content-Type" content="text/html;<br/>      charset=windows-1252" /&gt;<br/>&lt;/head&gt;</code>
</p>
            <p><code>&lt;body&gt;<br/>   &lt;table border="0" bgcolor="#C0C0C0" width="100%"&gt;<br/>      &lt;tr id="areatop"&gt;<br/>         &lt;td &gt;Axway&lt;/td&gt;<br/>         &lt;td &gt;SecureTransport&lt;/td&gt;<br/>      &lt;/tr&gt;<br/>      &lt;tr id="areatopmain"&gt;<br/>         &lt;td colspan="2" align="center"&gt;<br/>            File Delivery Failure<br/>         &lt;/td&gt;<br/>      &lt;/tr&gt;<br/>      &lt;tr id="areabody" bgcolor="white"&gt;<br/>         &lt;td colspan="2"&gt;<br/>            Delivery of the file &lt;b&gt;$DXAGENT_TARGET&lt;/b&gt; to the host<br/>            &lt;b&gt;$DXAGENT_SITE_ATTR_HOST&lt;/b&gt; failed after<br/>            &lt;b&gt;$DXAGENT_PERSISTED_EVENT_RETRY_COUNT&lt;/b&gt; attempts.<br/>            &lt;p&gt;Inspect the File Tracking Page in the ST Administration Tool<br/>            for more information on the reason for the failure.&lt;/p&gt;<br/>         &lt;/td&gt;<br/>      &lt;/tr&gt;<br/>   &lt;/table&gt;<br/>&lt;/body&gt;<br/>&lt;/html&gt;</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can hard code the values directly into the email notification template or you can use any <span>SecureTransport</span> environment variable. In the previous example the <code>mailfrom</code> address is hard coded into the template, but the <code>mailto</code> address is calculated at runtime from the <code>$DXAGENT_ACCOUNT_EMAIL</code> variable.<br/>Any value set in the Invocation Parameter for the TM rule overrides the value set in the notification template.         </td>
      </tr>
</table>
