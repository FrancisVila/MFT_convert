{
    "title": "Customize the email notification templates",
    "linkTitle": "Customize the email notification templates",
    "weight": "330"
}The templates are located in `<FILEDRIVEHOME>/conf/mailer-templates`. You can customize the email notification template with any text or HTML editor. An HTML editor is recommended because you can use it to preview the notification before deploying it in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

There are seven prerequisite fields that must be set in the XHTML email notification template.

-   `$subject` — The subject line for the email
-   `$mailfrom` — Who the email is coming from
-   `$mailto` — Who the email is going to
-   `$mailserver` — The name of the local SMTP mail server that will be used to deliver the email
-   `$mailserverport` — The TCP port on the SMTP server to connect to.
-   `$smtpUser` — A user to be used when authenticating to an SASL-enabled SMTP server.
-   `$smtpPassword` — Authentication password for the user specified in the `smtpUser` field.

The following code example shows an XHTML file with the prerequisites set:



    <?xml version="1.0" encoding="windows-1252"?>
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN"
       "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">

    <!-- #set( $subject = "ST was unable to deliver a file to
       $DXAGENT_SITE_ATTR_HOST") -->
    <!-- #set( $mailfrom = "admin@example.com") -->
    <!-- #set( $mailto = $DXAGENT_ACCOUNT_EMAIL) -->
    <!-- #set( $mailserver = "mail.example.com") -->
    <!-- #set( $mailserverport = "25") -->
    <!-- #set( $smtpUser = "user") -->
    <!-- #set( $smtpPassword = "password") -->

    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
       <meta http-equiv="Content-Type" content="text/html;
          charset=windows-1252" />
    </head>

    <body>
       <table>
                <tr>
                      <td>Axway         </td>
                      <td>SecureTransport         </td>
                </tr>
                <tr>
                      <td>
                File Delivery Failure
                      </td>
                </tr>
                <tr>
                      <td>
                Delivery of the file <b>$DXAGENT_TARGET</b> to the host
                <b>$DXAGENT_SITE_ATTR_HOST</b> failed after
                <b>$DXAGENT_PERSISTED_EVENT_RETRY_COUNT</b> attempts.
                <p>Inspect the File Tracking Page in the ST Administration Tool
                for more information on the reason for the failure.</p>
                      </td>
                </tr>
       </table>
    </body>
    </html>

> **Note:**
>
> You can hard code the values directly into the email notification template or you can use any SecureTransport environment variable. In the previous example the mailfrom address is hard coded into the template, but the mailto address is calculated at runtime from the $DXAGENT\_ACCOUNT\_EMAIL variable.Any value set in the Invocation Parameter for the TM rule overrides the value set in the notification template.
