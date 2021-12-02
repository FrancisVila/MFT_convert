{
    "title": "Functions",
    "linkTitle": "Functions",
    "weight": "210"
}The function expression syntax is modeled on the following, while still respecting basic command rules:

-   A unique keyword that identifies the function (id\_func). This keyword is always preceded by the character \_ (underscore).
-   Two invariable identifier parameters: PARM and RC. The PARM parameter specifies the function call, and RC provides an execution report.

The report must be the name of a variable of the type long integer.

## Using the print function

#### Syntax

The PRINT function displays a string to standard output, or to a file if the output is redirected by the CAPTURE command.

#### Parameters

-   STR: Character string to be displayed. If the string contains blanks it must be enclosed in quotes. The string may contain a variable reference between two % characters (percent sign).

#### Example

## Using general functions

General functions include:

-   \_Rand: Returns a random number
-   \_MemSet: Initializes data
-   \_MemCpy: Copies data
-   \_StrCpy: Recopies the CHAR variable
-   \_StrCmp: Compares the CHAR variables

### Function \_RAND

#### Syntax

The \_RAND function generates a random number between a lower limit and an upper limit.

#### Parameters

-   VAR: The name of a variable of type LONG which will be stored in the random number.
-   ValMin: The lower limit for the generated random number.
-   ValMax: The upper limit of the generated random number.

#### Examples

### Function \_MEMSET

#### Syntax

The \_MEMSET function fills a string with a character.

#### Parameters

Enter the parameter value in upper case.

-   VAR: The name of the CHAR type variable that is filled.
-   CODE: ASCII code of the fill character
-   LG: Fill length.

#### Examples

### Function \_MEMCPY

#### Syntax

The \_MEMCPY function copies a string to a source destination string.

#### Parameters

Enter the parameter value in upper case.

-   VAR: The name of the CHAR variable destination.
-   STR: The name of a variable of type CHAR source.
-   LG: The number of characters that are recopied.

#### Example

### Function \_STRCPY

#### Syntax

The \_Strcpy function copies a string to a CHAR variable.

#### Parameters

-   VAR: The name of the CHAR variable that is copied to the string STR. Check that the length of VAR is greater than the STR.
-   STR: Character string to be copied to the variable VAR.

#### Example

### Function \_STRCMP

#### Syntax

The \_STRCMP function compares two strings.

#### Parameters

-   VAR1: The name of the first CHAR variable to compare.
-   VAR2: The name of the second CHAR variable to compare.
-   CMP: Name variable of type LONG which will store the result of the comparison of VAR1 VAR2 with. If the strings are identical CMP = 0 if the strings are different CMP = 1.

#### Example

At the end of this test, variable CMP is 1.
