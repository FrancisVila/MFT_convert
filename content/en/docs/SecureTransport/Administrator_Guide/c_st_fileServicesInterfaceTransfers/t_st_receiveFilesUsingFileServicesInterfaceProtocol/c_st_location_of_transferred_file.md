{
    "title": "Location of the transferred file",
    "linkTitle": "Location of the transferred file",
    "weight": "240"
}For files pushed to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> from a remote system, use `SourceFileLocation` and optionally `RemoteSharePath` and `LocalSharePath` to specify the location of the transferred file:

-   If `RemoteSharePath` or `LocalSharePath` is not specified, `SourceFileLocation` is the location of the transferred file on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system.
-   If `RemoteSharePath` and `LocalSharePath` are specified and `SourceFileLocation` starts with `RemoteSharePath`, then <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> replaces `RemoteSharePath` with `LocalSharePath` to determine the location of the transferred file on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system.
-   If `RemoteSharePath` and `LocalSharePath` are specified and `SourceFileLocation` does not start with `RemoteSharePath`, then <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> concatenates `LocalSharePath` and `SourceFileLocation` to determine the location of the transferred file on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system.

For files pushed to a remote system from <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, `LocalSharePath` must be specified. Use `SourceFileLocation` and optionally `RemoteSharePath` to specify the location of the transferred file:

If `RemoteSharePath` is specified, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> concatenates `LocalSharePath`, a unique directory name, `RemoteSharePath`, a unique file prefix, and `SourceFileLocation` to determine the location of the transferred file on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system.

If `RemoteSharePath` is not specified, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> concatenates `LocalSharePath`, a unique directory name, a unique file prefix, and `SourceFileLocation` to determine the location of the transferred file on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system.

**Related topic:**

-   <a href="../r_st_metadata_file" class="MCXref xref">Metadata file</a>
