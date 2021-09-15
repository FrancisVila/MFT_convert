{
    "title": "Location of the transferred file",
    "linkTitle": "Location of the transferred file",
    "weight": "250"
}For files pushed to SecureTransport from a remote system, use `SourceFileLocation` and optionally `RemoteSharePath` and `LocalSharePath` to specify the location of the transferred file:

-   If `RemoteSharePath` or `LocalSharePath` is not specified, `SourceFileLocation` is the location of the transferred file on the SecureTransport system.
-   If `RemoteSharePath` and `LocalSharePath` are specified and `SourceFileLocation` starts with `RemoteSharePath`, then SecureTransport replaces `RemoteSharePath` with `LocalSharePath` to determine the location of the transferred file on the SecureTransport system.
-   If `RemoteSharePath` and `LocalSharePath` are specified and `SourceFileLocation` does not start with `RemoteSharePath`, then SecureTransport concatenates `LocalSharePath` and `SourceFileLocation` to determine the location of the transferred file on the SecureTransport system.

For files pushed to a remote system from SecureTransport, `LocalSharePath` must be specified. Use `SourceFileLocation` and optionally `RemoteSharePath` to specify the location of the transferred file:

If `RemoteSharePath` is specified, SecureTransport concatenates `LocalSharePath`, a unique directory name, `RemoteSharePath`, a unique file prefix, and `SourceFileLocation` to determine the location of the transferred file on the SecureTransport system.

If `RemoteSharePath` is not specified, SecureTransport concatenates `LocalSharePath`, a unique directory name, a unique file prefix, and `SourceFileLocation` to determine the location of the transferred file on the SecureTransport system.

**Related topic:**

-   [Metadata file](../r_st_metadata_file)
