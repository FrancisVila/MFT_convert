{
    "title": "Mailbox settings",
    "linkTitle": "Mailbox settings",
    "weight": "120"
}When the sends an e-mail, it checks for a certain period of time whether the message has been sent successfully or it has been blocked because it contained sensitive information. In both scenarios, a message status notification is displayed to the user. If cannot obtain the message status before the allotted time expires, the user needs to refresh the folder to see details.

This behavior is controlled by two configuration options:

-   `sendPollingInterval` (milliseconds) specifies the interval between successive checks

-   `sendPollingRetries` specifies how many times ST should check for the status of the message

The default values are listed below.


    {
      ...
         "mailbox": {
            "sendPollingInterval": 500,
         "sendPollingRetries": 10
          }
      ...
    }
