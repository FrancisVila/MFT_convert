{
    "title": "Catalog querying services ",
    "linkTitle": "Catalog querying services",
    "weight": "240"
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
