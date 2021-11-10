{
    "title": "rpasswd",
    "linkTitle": "rpasswd",
    "weight": "2970"
}### rpasswd

#### CFTSEND/CFTRECV

\[ RPASSWD = *string*, \_AUTH\_\]

Password for the user who is receiving the file. You can provide this directly, or through an external flat file using the following format:

part1 user1 passwd1

part2 user2 passwd2

\* user1 passwd3

\* \* passwd4

Or you can use \_AUTH\_ to indicate authentication method as defined in the uconf <span class="code">cft.server.authentication\_method</span> parameter.

Example

<span class="code">/home/&USERID/cft\_passw</span>

> **Note:**
>
> If you begin a password with an indirection character (Unix @, Windows #), it is considered a reference to a file and not part of the password.

[Return to Command index](../../)
