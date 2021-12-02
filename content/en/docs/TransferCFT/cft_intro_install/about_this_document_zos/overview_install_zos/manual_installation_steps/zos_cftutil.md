{
    "title": "CFTUTIL in a z/OS environment",
    "linkTitle": "CFTUTIL in a z/OS environment",
    "weight": "270"
}CFTUTIL is the primary utility for Transfer CFT. This section details some functionally related specifically to z/OS. The CFTUTIL utility is called through two procedures: PCFTUTIL and PCFTUTL.

> **Note:**
>
> There have been updates to this utility in versions 3.2.4 and 3.2.4 SP1.

## CFTIN: Concatenate regular sequential data sets and in-stream data sets

> **Note:**
>
> MY.FB80.PARM -> RECFM=FB , LRECL=80

### Regular data set defined first

### In-stream data set defined first

For data set concatenation on Transfer CFT 3.2.4 and higher:

-   For PDSs concatenation, as specified in the IBM documentation, the data set with the largest block size must appear first in the concatenation.
-   You cannot concatenate PDSs that have different record lengths when RECFM=FB.

## CFTIN: Working with UNIX files

-   File concatenation does not work.
-   cft\_cmd.txt is a EBCDIC text file.

## CFTIN: CFTIN is missing

When no command is specified in the JCL PARM parameter, and if the DD CFTIN is not defined in the JCL:

-   The CFTUTIL return code is: 8
-   The following WTO is performed:

## CFTPARM dummy

When using the PCFTUTIL procedure and there is no data used from CFTPARM, we recommend specifying DUMMY as the DD CFTPARM to decrease EXCP and CPU consumption, for example in END-TRANSFER procedures.
