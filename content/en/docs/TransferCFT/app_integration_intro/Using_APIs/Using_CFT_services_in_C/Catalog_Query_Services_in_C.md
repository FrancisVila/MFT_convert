{
    "title": " Transfer CFT  catalog query services",
    "linkTitle": "Catalog query services in C",
    "weight": "340"
}This service provides access to the  {{< TransferCFT/componentshortname  >}} catalog entries, for
querying and modification, and enables you to sort the selected catalog
entries. Additionally, you can sort the current selection in memory.

> **Note**
>
> The communication structure
> in Transfer CFT enables you to recuperate catalog fields, such
> as an identifier, that exceed 8 to 32 characters.

```

Function

Use

OPEN
Open catalog file
This function:

-   Allocates
    the catalog file
-   Opens
    the file
-   Reserves
    an internal control block
-   Initializes
    the internal block parameter

SELECT
Specify the selection criteria
This function:

-   Checks
    the syntax used
-   Stores
    the selection criteria in the internal control block

SELECT240
Specify the selection criteria
This function:

-   Is available
    in CFT v2.4 and higher
-   Retrieves
    identifiers that are longer than 8 to 32 characters
-   Checks
    the syntax used
-   Stores
    the selection criteria in the internal control block

NEXT
Read next entry in the catalog
This function:

-   Reads
    the next entry
-   Sets
    the "catalog entry data" area

The first call to this function must be preceded by a SELECT.
NEXT240
Read next entry in the catalog
This function:

-   Is available
    in CFT v2.4 and higher
-   Retrieves
    identifiers that are longer than 8 to 32 characters
-   Reads
    the next entry
-   Sets
    the "catalog entry data" area

MODIFY
Modify the state of the current catalog entry or delete
this entry from the catalog
This function:

-   Retrieves
    the last entry read from the internal control block
-   Checks
    the state of this entry
-   Sends
    the modification request to  {{< TransferCFT/componentshortname >}}

SORT
Sort the selected catalog entries
This function:

-   Close
    the catalog file
-   De-allocates
    the file
-   Frees
    the internal control block
-   Resets
    the internal control block parameter

DO
Execute the current selection and the requested sort in
memory
CLOSE
Close catalog file
```
<span id="Call_Syntax"></span>

## Call syntax

These services enable you to query the catalog either with or without
specific criteria.

`rc = cftai (verb,&ptr,param)`

`rc = cftaix (verb,&ptr,param)`

Where:

-   rc is the return
    code (int)
-   verb is the command
    that you want to process (char \*)
-   ptr contains the
    address of an internal control block (char \*) completed on return of an
    OPEN service call. It must be provided and defined to call other functions
-   param points to
    the parameters specific to each function

The available verbs are listed in the following table.

```

<verb>

Service

OPEN
Open catalog
SELECT
Define selection criteria
NEXT
Read next entry
MODIFY
Modify catalog entry state
SORT
cftaix only
DO
cftaix only
Do the current selection and the requested
sort in memory
CLOSE
Close catalog
```

The available &lt;param> are listed in the following table.

```
<verb>
<param>
Explanation
OPEN
cat
Path name or logical name of the catalog file. If the name
is blank, Transfer CFT uses a default name.
SELECT
and SELECT240
&cftsel
Selection criteria according to the format described in
the "*Selection data description*"
in the **cftapi.h** file.

-   cftsel230T for SELECT service
-   cftsel240T for SELECT240 service

All the
fields must be defined by left-aligned character strings. If a field is
equal to binary zeros, it is considered not selective.
This structure can contain:

-   The size
    of the selection criteria field (slength) and the size of the field supporting
    the catalog entry (clength) in order to avoid recompiling the application
    program if these two fields are extended.
-   The transfer
    start and end date (BDATE and EDATE) to select transfers performed between
    these two dates.
-   A field
    can be composed of a mask with the special characters "?" and
    \*". The "?" character replaces any character. The "\*"
    character replaces a character string of any length.
    Examples:
    A\*D replaces ABCD, ABCED or AID
    A??D replaces ABCD, AXYD or AQZD
    \*CD replaces ABECD, YXZCDor TYUICD
    ?CD replaces ACD, XCD or ZCD
    ?B\* replaces ABCDEF, XBZWEO or \*KBWXCV
    ???? replaces ABCD, XYZW or HGFD

You should initialize the following:

-   The param
    field to binary zero before defining it
-   The slength
    and clength by  "itoa()"

cftaix only
The selection is only taken into account at the time the
DO service is called.
NEXT
and
NEXT240
&cftcat
Next catalog entry according to the format described in
the "<span style="font-style: italic;">Selection data description</span>"
in the <span style="font-weight: bold;">cftapi.h</span> file.

-   cftcatT for NEXT service
-   cftcat240T for NEXT240 service

MODIFY
&nstate
New state of a transfer to be placed in the catalog entry
previously read:

-   ‘D’ at
    Disposal: only valid if the former state is H or K
-   ‘H’ Hold:
    only valid if the former state is D, C
    or K
-   ‘K’ Keep:
    only valid if the former state is D, C or H
-   ‘X’ eXecuted:
    only valid if the former state is T
-   ‘P’ Purge:
     deletes
    the catalog entry\*. It is only valid if the current state is D, H, K,
    T or X

SORT
param
cftaix only
Sort options as described in the "<span style="font-style: italic;">Sort structure of the selected catalog entries</span>"
in the <span style="font-weight: bold;">cftapi.h</span> file.
The function is only taken into account at
the time the DO service is called.
DO
" "
 
CLOSE
" "
 
```

## Return codes

The following return codes apply to all services.

```
Mnemonic
Description
CAPI_NOERR
No error
CAPI_FUNC_UNDEF
Command not valid or service refused by the operating security
system
CAPI_INT_PTR
<ptr> parameter invalid
OPEN code only
CAPI_MEM_GET
Memory allocation error
CAPI_CAT_ALLOC
cftai only
Catalog file allocation error
CAPI_CAT_OPEN
Catalog file opening problem
SELECT code only
CAPI_SEL_DIRECT
DIRECTION criterion incorrect
CAPI_SEL_TYPE
TYPE criterion incorrect
CAPI_SEL_STATE
STATE criterion incorrect
CAPI_CAT_EMPTY
Catalog empty
CAPI_CAT_SELECT
cftaix only
Selection incorrect
CAPI_SEL_DATE
EDATE value < BDATE value
CAPI_SEL_FDATE
FDATE criterion incorrect
CAPI_SEL_CDATE
CDATE criterion incorrect
CAPI_SEL_BDATE
BDATE criterion incorrect
CAPI_SEL_DATE
<span style="font-weight: normal;">EDATE
criterion incorrect</span>
NEXT code only
CAPI_CAT_EOF
End of catalog file
CAPI_CAT_READ
Catalog file read error
MODIFY code only
CAPI_CAT_MODIFY
cftaix only
Modification error
CAPI_MOD_OSTATE
State invalid
CAPI_MOD_NSTATE
Requested new state incorrect
CAPI_INT_ERR2
Internal error
CAPIO_COM_OPEN
Communication medium opening error
CAPI_COM_WRITE
Communication medium write error
CAPI_COM_CLOSE
Communication medium closing problem
SORT code only (cftaix only)
CAPI_CATSORT
sort incorrect
DO code only (cftaix only)
CAPI_CAT_CLOSE
Error on closing the catalog
CAPI_CAT_OPEN
Error on opening the catalog
CAPI_CAT_EMPTY
Catalog empty or no record selected
CAPI_ERREXEC
Execution error
CLOSE code only
CAPI_MEM_FREE
Memory de-allocation error
CAPI_CAT_FREE
Catalog file de-allocation error
CAPI_CAT_CLOSE
Catalog file closing error
```