{
    "title": "Email notification overview",
    "linkTitle": "Email notification overview",
    "weight": "310"
}There are four benefits of using this package:

-   It generates HTML rather than plain text notifications.
-   It utilizes notification templates that allow SecureTransport variables to be used as substitution tokens.
-   The notification templates also contain meta-data to allow customizations of the email subject line and the SMTP envelope headers
-   It supports attachments making it easy to attach a target file.

The following example shows what an email generated using the Velocity Email Notification package can look like:

![Velocity Email Notification - File delivery failure](emailnotificationmessage%20example.PNG)

There are many scenarios in SecureTransport which might require generating a notification. This package contains examples that show how to generate a notification when:

-   A server upload delivery exhausts its retry count.
-   A sender or recipient needs to be notified when a file upload or download completes

However this package is easy to use in almost any scenario.
