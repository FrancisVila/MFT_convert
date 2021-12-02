{
    "title": "Send  a message",
    "linkTitle": "Sending a MESSAGE",
    "weight": "240"
}You can use the SEND MESSAGE command to send a message to a designated partner, for example small amounts of content that are not considered sensitive content.

-   The message length in the PeSIT protocol has a maximum value of 4096 bytes
-   The message can be extracted from the Catalog file, and redirected to a specified file (fout parameter), using the DISPLAY command:

**Example**

**Result**

The resulting msgfile will contain the message 'hello'.

> **Note:**
>
> The &lt;TransferCFTinstallation>\\runtime\\conf folder contains the dspcnf.xml file, a DISPLAY command template, which includes a specific filter templatel id='msg' that enables message extraction.

### Sending messages

#### Example

A message using the identifier ANDREW.
