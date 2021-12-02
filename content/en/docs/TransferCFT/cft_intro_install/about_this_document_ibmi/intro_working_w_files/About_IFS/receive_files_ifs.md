{
    "title": "Configure receive mode for files (IFS)",
    "linkTitle": "Configure receive mode (IFS)",
    "weight": "230"
}## File types

The following table lists the different types of files that can be received on an IBM i system when using IFS.

> **Note:**
>
> The FRECFM possibilities for all FTYPE are: ‘V’, ‘F’, and ‘ ’ .

Key

If your partner sends a PF-SRC file to be received on IFS, the content is slightly different depending on if you use the FTYPE ‘S’ or ‘E’. With the FTYPE ‘E‘, the content of the file is only the original content of the PF-SRC file. When the FTYPE is ‘S’, the content is the original content of the PF-SRC file along with the record character in the header line.

When sending a file from the part of an IBM i machine in text mode, the file is expected to be a standard text file. This means that every line of the file to transfer is finished either by a LF, either by a CR/LF. If not, the file is considered to be binary and Transfer CFT cannot read it. Use the binary mode to allow it to be transferred.
