{
    "title": "About transport security and PKIUTIL commands",
    "linkTitle": "Transport security and PKIUTIL commands",
    "weight": "260"
}This section describes SSL security parameters. For more information on transport security concepts, refer to the sub-book in the *Transfer* documentation.

## Certificates

Refer to the [Transfer CFT {{< TransferCFT/doctypeuser  >}}](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/AxwayStartPage.htm) for more information on certificates.

## Configuration changes

You must define certain elements in the product configuration if you want to use transfer security. See the delivered samples in CFTPGM/CFTSRC(TCPPARAM).

# Using the PKIUTIL utility

To use the PKIUTIL utility:

1.  Access the Transfer CFT screen. In the Main Menu enter the command `cft` and press **Enter** to open the .
2.  Select **option** **2. Security commands**. Then select option **2. Interpret Security configuration** and enter the member you want to interpret. By default this is the PKIBASE member in the UTIN file in CFTPROD library.
3.  To edit the security configuration file selection option 2. Security commands then option 1. Edit Security configuration file and enter the member you want to edit. By default it is the PKIBASE member in the UTIN file in CFTPROD library.

## Submitting PKIUTIL commands

**Select option** ****2. Security commands****, and then ****3. PKIUTIL operation**** in the Operations screen to start the **PKUTIL session**.

This option allows you to use the keyboard to enter and execute PKIUTIL commands.

## Create a database

Use the following commands, in order, to create a database:

 

 

### List PKI Internal datafiles contents

1.  To list the PKI internal datafiles  contents, enter the command: ` LISTPKI`
2.  Press ENTER to execute the command.

A correct execution displays the following messages:
