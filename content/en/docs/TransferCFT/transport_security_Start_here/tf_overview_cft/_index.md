{
    "title": "About Trusted File for file encryption",
    "linkTitle": "Using TrustedFile for file encryption",
    "weight": "210"
}## Encryption concepts

This topic describes how to implement Axway Trusted File encoding. {{< TransferCFT/componentshortname  >}} in conjunction with TrustedFile enables you to send encrypted files in S/MIME, CMS, and OpenPGP format, for increased security for data exchanges. To initiate this additional security, Transfer CFT delivers a set of samples and certificates to implement TrustedFile in your environment. To get started using TrustedFile with Transfer CFT, read the following sections:

-   [Before you start](#Before)
-   [About the Transfer CFT configuration file](#Transfer)
-   [Defining the unified configuration parameters](#Defining)
-   [Command example (to encode/decode a file)](#Command)

The topic [Delivered files and certificates](tf_delivered_files_certficates) describes the scripts, conversion tables, files and samples delivered with Transfer CFT. And for more information on TrustedFile functionality, please refer to the [TrustedFile Reference Guide]() .

#### Limitations

-   You cannot use or {{< TransferCFT/flowmanager >}} to manage {{< TransferCFT/trustedfilename >}} functionality with {{< TransferCFT/componentshortname >}}.

<span id="Before"></span>

## Before you start

In Transfer CFT you use the CFTTF utility, referred to as XPPTF in TrustedFile, to perform secured exchanges. To use this functionality your Transfer CFT key must include the Trusted File option. The Transfer CFT key is located in the file: `$CFTDIRRUNTIME/conf/cft.key`. If your product key does not include the Trusted File option if you try to execute the CFTTF program, an error will occur and an error message is displayed in the CFTLOG file: `CFTR19E XPPCFG_Error_#20:_Invalid_product_key`.

Transfer CFT delivers useable examples that automatically implement TrustedFile in your preprocessing and post processing flow. The next section describes the delivered samples.

<span id="Transfer"></span>

## Understanding the delivered sample configuration file

The Transfer CFT sample configuration file `runtime/conf/cft-tf-smp.conf` includes the TrustedFile IDF as shown here.

-   The delivered procedures are called during the preprocessing phase to encode the file (tf\_cipher.cmd), and delete the encoded file after sending (tf\_delfile.cmd).
-   The post processing script decodes on the receiving side (tf\_decipher.cmd).

Sending

Receiving

<span id="Defining"></span>

## Defining the unified configuration parameters

The Transfer CFT installation process automatically sets the following Transfer CFT unified configuration parameters to enable {{< TransferCFT/trustedfilename  >}} functioning. For information on uconf, see [About the Unified Configuration](../../admin_intro/uconf).

<span id="Command"></span>

## Command example

Use the SAPPL variable to define the type of security format to use to encode the file. Note that you must
use the same security format as your partner (possible values are CMS, PGP, and S/MIME).

Example

To encode/decode messages using PGP, use the format:

## Not supported

When using {{< TransferCFT/trustedfilename  >}} with Transfer CFT, some {{< TransferCFT/trustedfilename  >}} functionalities are not delivered or available as described in the {{< TransferCFT/trustedfilename  >}} documentation. These include:

-   Overview: Graphical user interface (not delivered in the package)
-   Configuration sample: Encoding and decoding files with Java API
-   C-API

Related topics

-   [SAPPL](../../c_intro_userinterfaces/command_summary/parameter_intro/sappl)
-   [Delivered files and certificates](tf_delivered_files_certficates)
-   [How to generate a certificate for {{< TransferCFT/trustedfilename >}}](tf_generate_cert)
