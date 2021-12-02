{
    "title": "Troubleshoot user control (USERCTRL)",
    "linkTitle": "Troubleshoot user control (USERCTRL)",
    "weight": "340"
}Homogeneous transfers fail on UNIX systems

If a USERID is set for a CFTRECV during a homogeneous transfer, the transfer fails if the user does not have rights on the log folder.

**Fix**

Grant the user the right to execute $CFTDIRLOG to access the directory.
