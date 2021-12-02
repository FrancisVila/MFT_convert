{
    "title": "Manage commands",
    "linkTitle": "Manage commands",
    "weight": "180"
}This section describes all of the command available to manage your Transfer CFT product.

## Standard commands

```

Command

Comment

CFTSTART
Start Transfer CFT
CFTSTOP
Stop Transfer CFT
COPSTART
Start the UI server
COPSTOP
Stop the UI server
CFTMN
This is the procedure to manage Transfer CFT and to configure multi-node. Add
the following action(s) to manage your product:

-   START
-   STOP
-   RESTART
-   ADD\_NODE
-   REMOVE\_NODE
-   ADD\_HOST
-   REMOVE\_HOST
-   REMOVE\_NODE
-   ENABLE\_NODE
-   DISABLE\_NODE

> **Note:**
> CFTMN is the equivalent of cft script for UNIX or
> Windows.

```

## Deprecated commands

```

Replace this command...

With the new command...

SHUT
CFTSTOP + COPSTOP
CFTMGSBM
CFTSTART
STARTCOPB
COPSTART
COPSMNG
COPSTART
COPSTOPM
COPSTOP
STOPCOPL
COPSTOP
BACKGROUND\_C
BACKGROUND
SNDCFTF
CFTUTIL (See **Example 1**)
SNDCFTSPLF
CFTUTIL (See **Example 2**)
MAJSECINI
No replacement
MAJSECENVG
No replacement
GENEDICT
No replacement
```

**Example 1**

Send a member:

```
CFTUTIL send PART=<PART>, IDF=<IDF>, FNAME=&LIB/&FILE(&MBR)
```

**Example 2**

Send a spool file:

```
CFTUTIL send PART=<PART>, IDF=<IDF>, FNAME=&FILE/&SPLNBR/&WORK/&JOBNBR
```

 
