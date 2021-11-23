{
    "title": "Location of the transferred file",
    "linkTitle": "Location of the transferred file",
    "weight": "240"
}For files pushed to {{< SecureTransport/componentshortname  >}} from a remote system, use `SourceFileLocation` and optionally `RemoteSharePath` and `LocalSharePath` to specify the location of the transferred file:

-   If `RemoteSharePath` or `LocalSharePath` is not specified, `SourceFileLocation` is the location of the transferred file on the {{< SecureTransport/componentshortname >}} system.
-   If `RemoteSharePath` and `LocalSharePath` are specified and `SourceFileLocation` starts with `RemoteSharePath`, then {{< SecureTransport/componentshortname >}} replaces `RemoteSharePath` with `LocalSharePath` to determine the location of the transferred file on the {{< SecureTransport/componentshortname >}} system.
-   If `RemoteSharePath` and `LocalSharePath` are specified and `SourceFileLocation` does not start with `RemoteSharePath`, then {{< SecureTransport/componentshortname >}} concatenates `LocalSharePath` and `SourceFileLocation` to determine the location of the transferred file on the {{< SecureTransport/componentshortname >}} system.

For files pushed to a remote system from {{< SecureTransport/componentshortname  >}}, `LocalSharePath` must be specified. Use `SourceFileLocation` and optionally `RemoteSharePath` to specify the location of the transferred file:

If `RemoteSharePath` is specified, {{< SecureTransport/componentshortname  >}} concatenates `LocalSharePath`, a unique directory name, `RemoteSharePath`, a unique file prefix, and `SourceFileLocation` to determine the location of the transferred file on the {{< SecureTransport/componentshortname  >}} system.

If `RemoteSharePath` is not specified, {{< SecureTransport/componentshortname  >}} concatenates `LocalSharePath`, a unique directory name, a unique file prefix, and `SourceFileLocation` to determine the location of the transferred file on the {{< SecureTransport/componentshortname  >}} system.

**Related topic:**

-   [Metadata file](../r_st_metadata_file)
