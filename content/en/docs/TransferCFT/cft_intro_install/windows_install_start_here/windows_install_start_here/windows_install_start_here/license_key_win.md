{
    "title": "Applying a\u00a0license key",
    "linkTitle": "Applying a\u00a0license key",
    "weight": "230"
}**Windows**

You need to apply a valid license key to Transfer CFT in the following situations:

-   You perform an initial Transfer CFT installation.
-   To replace an expired license key (typically after a year).

## Obtain a license key

1.  Install Transfer CFT. You can install Transfer CFT without a license key, and enter the key afterward.
2.  After completing the installation, or for an existing installation, use the command cftutil about to retrieve your system information. For details see [ABOUT: Displaying product and host information](../../../../../c_intro_userinterfaces/about_cftutil/about_command).
3.  Contact the Axway Fulfillment team at the appropriate email address, and provide the hostname and system information.
    -   For a US key, contact: fulfillment@us.axway.com
    -   For an EMEA or APAC key, contact: product.key@axway.com

## Apply a license key

Normally you enter the key that you received from the Axway Fulfillment team during the installation process. However, to apply the license key at a later date, enter the key(s) in the indirection file, which is referred to in the CFTPARM KEY parameter. See the [KEY](../../../../../c_intro_userinterfaces/command_summary/parameter_intro/key) parameter for an example and details.

-   The file can contain one or multiple license keys, but it must have one key per line.
-   On start up the first valid key is used.

### Multi-node keys

Transfer CFT 3.3.2 SP2 and higher

Transfer CFT allows you to use a single key for a multi-node installation. To use a single key for multiple hosts, either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

For example, if you have 2 hosts and 4 nodes, you only need one key that matches one hostname (or no defined hostname).

Transfer CFT prior to 3.3.2 SP2

If you are using a Transfer CFT 3.3.2 prior to SP2, multi-node architecture requires:

-   One key per node, and if there is more than one host you require at least one valid key per host
-   Each key must have the cluster option

For example, if you have 2 hosts and 4 nodes, you require 4 keys with at least one key per host. Possible key combinations could be:

-   2 keys that are configured to reference the first host, and the 2 other keys configured to reference to the second host
-   3 keys that are configured to reference the first host, and 1 that is configured to reference to the second host

## About command

Use the CFTUTIL utility to execute the about command to display key and general system information as demonstrated in this example.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL about</p>
<p>…</p>
<p>Host information :</p>
<p>* model =</p>
<p>* hostname = ITEM-AX31614</p>
<p>* sysname = Windows</p>
<p>* machine = AMD_X8664</p>
<p>* version = 6.2.9200</p>
<p>* release =</p>
<p>* distrib =</p></td>
</tr>
</tbody>
</table>
