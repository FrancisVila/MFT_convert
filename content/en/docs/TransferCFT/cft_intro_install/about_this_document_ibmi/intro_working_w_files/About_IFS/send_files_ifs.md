{
    "title": "Configure send mode on IFS",
    "linkTitle": "Configure send mode (IFS)",
    "weight": "220"
}## File types

The following table lists the different types of files that can be used according to the type of data to be sent when using IFS.

> **Note:**
>
> The FRECFM possibilities for all FTYPE are: ‘V’, ‘F’, and ‘ ’ .

Key

When sending a file from the part of an IBM i machine in text mode, the file is expected to be a standard text file. This means that every line of the file to transfer is finished either by a LF, either by a CR/LF. If not, the file is considered to be binary and Transfer CFT cannot read it. Use the binary mode to allow it to be transferred.

## Sending a group of IFS files

### Send using a generic name

This section describes how to send a group of files using a send command where there is one transfer per file.

When defining the filename, you must put a &lt;file-symb> character (system-specific) before the FNAME parameter value. environments use the ‘#’ and ‘£’ symbols.

Use one of the following commands to send a group of files using a generic name:

SEND FNAME=#path\_name/wildcards

Or:

CFTSEND FNAME=#path\_name/wildcards

The FNAME parameter is set to a generic name that includes wildcard characters. In this type of send, only the selected files are sent.

A receiving Transfer CFT can specify the name of each file received via the symbolic variables:

-   ?FPATH the file path of the sending file, and
-   ?FROOT the file name of the sending file

Example

-   CFTSEND

FNAME = “#/home/send/FIC\*.\*”, FRECVFM = V

-   CFTRECV

FNAME = “/home/recv/?FROOT”,

FRECVFM = V

### Send using an IFS file that contains a list of files

These rules apply to the structure of the file containing a list of files:

-   A record can contain only one file name
-   Each file name must be listed in the first column
-   The file names must be written in EBCDIC

Example

Enter:

CFTSEND FNAME = “#/home/send/FICLIST”, FRECVFM = V

If the file FICLIST contains the following lists:

-   /home/send/FIC1
-   /home/send/FIC2
-   /home/send/FIC3

Then the files FIC1, FIC2 and FIC3 are sent.
