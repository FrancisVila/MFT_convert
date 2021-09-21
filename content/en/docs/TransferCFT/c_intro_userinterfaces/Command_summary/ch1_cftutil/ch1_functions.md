{
    "title": "Functions",
    "linkTitle": "Functions",
    "weight": "230"
}The function expression syntax is modeled on the following, while still respecting basic command rules:

-   A unique keyword that identifies the function (id\_func). This keyword is always preceded by the character \_ (underscore).
-   Two invariable identifier parameters: PARM and RC. The PARM parameter specifies the function call, and RC provides an execution report.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;id_func&gt; PARM = ([&lt;value&gt;,] * &lt;value&gt;), RC = &lt;value&gt;</p>
            <p>The expression in square brackets is repeated.</p>
         </td>
      </tr>
   </tbody>
</table>

The report must be the name of a variable of the type long integer.

## Using the print function

#### Syntax

The PRINT function displays a string to standard output, or to a file if the output is redirected by the CAPTURE command.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PRINT MSG = CHAIN​​,</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   STR: Character string to be displayed. If the string contains blanks it must be enclosed in quotes. The string may contain a variable reference between two % characters (percent sign).

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = CHAINE, size = 16, init = 'ABCDEF'</p>
            <p>   PRINT	MSG = 'displays the string %CHAINE2%'</p>
         </td>
      </tr>
   </tbody>
</table>

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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_RAND PARM = (VAR, Valmin, ValMax)</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   VAR: The name of a variable of type LONG which will be stored in the random number.
-   ValMin: The lower limit for the generated random number.
-   ValMax: The upper limit of the generated random number.

#### Examples

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>LONG	name = DRAW</p>
            <p>_RAND	parm = (DRAW, 1, 49)</p>
            <p>_PRINT	msg = 'The drawing for the first number for the LOTTERY is %DRAW%'</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_MEMSET

#### Syntax

The \_MEMSET function fills a string with a character.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_MEMSET PARM = (VAR, CODE, LG)</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

Enter the parameter value in upper case.

-   VAR: The name of the CHAR type variable that is filled.
-   CODE: ASCII code of the fill character
-   LG: Fill length.

#### Examples

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = BUFFER , size=16</p>
            <p>_MEMSET	parm = (BUFFER, 32,16)</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_MEMCPY

#### Syntax

The \_MEMCPY function copies a string to a source destination string.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_MEMCPY PARM = (VAR, STR, LG)</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

Enter the parameter value in upper case.

-   VAR: The name of the CHAR variable destination.
-   STR: The name of a variable of type CHAR source.
-   LG: The number of characters that are recopied.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = BUFFER , size=16</p>
            <p>CHAR	name = STR , size=16, init = 'Line of 16 CAR'</p>
            <p>_MEMCPY	parm = (BUFFER, STR,16)</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_STRCPY

#### Syntax

The \_Strcpy function copies a string to a CHAR variable.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_STRCPY NAME = VAR,</p>
            <p>STR = CHAIN,</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   VAR: The name of the CHAR variable that is copied to the string STR. Check that the length of VAR is greater than the STR.
-   STR: Character string to be copied to the variable VAR.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = STRING1, size = 16</p>
            <p>CHAR	name = STRING2, size = 16, init = 'ABCDEF'</p>
            <p>_STRCPY	name = STRING1, STR = %STRING2%</p>
         </td>
      </tr>
   </tbody>
</table>

### Function \_STRCMP

#### Syntax

The \_STRCMP function compares two strings.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>_STRCMP NAME = VAR1,</p>
            <p>STR = VAR2,</p>
            <p>RC = CMP</p>
         </td>
      </tr>
   </tbody>
</table>

#### Parameters

-   VAR1: The name of the first CHAR variable to compare.
-   VAR2: The name of the second CHAR variable to compare.
-   CMP: Name variable of type LONG which will store the result of the comparison of VAR1 VAR2 with. If the strings are identical CMP = 0 if the strings are different CMP = 1.

#### Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHAR	name = STRING1, size = 16, init = 'CDEFGH'</p>
            <p>CHAR	name = STRING2, size = 16, init = 'ABCDEF'</p>
            <p>LONG	name = CMP</p>
            <p>_STRCMP	name = STRING1, STR = STRING2, RC = CMP</p>
         </td>
      </tr>
   </tbody>
</table>

At the end of this test, variable CMP is 1.
