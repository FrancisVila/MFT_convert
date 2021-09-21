{
    "title": "fout",
    "linkTitle": "fout",
    "weight": "1300"
}### <span id="fout"></span>fout

#### DISPLAY

\[ FOUT = file\_name \]

Defines the file that the
command output is sent to. The file name represent the file where the
DISPLAY command redirects the message.

PeSIT

You can extract Transfer CFT messages from the catalog file, and forward these messages to a specified file using the DISPLAY fout parameter.

The message length for PeSIT ANY profile, when forwarding a message from oneTransfer CFT to another, is 4096 bytes. The S/RRUSIZE must be greater than the maximum message length and message information combined (for example, 4127).

LISTUCONF CONTENT=EXTRACT, [FOUT](#)=out extracts the UCONF (unified configuration).

#### EXTAMCACHE

**\[ FOUT = file\_name \]
  **

Defines the file where the
command output is sent.

[Return to Command index](../../)