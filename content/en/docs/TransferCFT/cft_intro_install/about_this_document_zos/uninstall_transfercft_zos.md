{
    "title": "Uninstall Transfer CFT ",
    "linkTitle": "Uninstall",
    "weight": "190"
}This section describes how to uninstall Transfer CFT in a z/OS environment.

If you uninstall a Transfer CFT, you will lose the entire Transfer CFT
configuration. To avoid this, you must save your environment prior removing the Transfer CFT.

### Procedure

Before uninstalling, you must stop the servers you want to uninstall (including Copilot).

Run the UNINSTAL JCL, which:

1.  Removes all files from the INSTANCE, including multi-node, except for the JCL library (target.INSTALL).
2.  Removes sub-USS directories, Copilot, and Secure Relay.
3.  Removes the distribution environment.

> **Note:**
>
> You must manually modify the JCL, by default the distribution environment is not removed (see lines 000018, 000081, and 000082 in the example).

Example
