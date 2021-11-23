{
    "title": "Create inclusion and exclusion filters",
    "linkTitle": "Create inclusion and exclusion filters",
    "weight": "210"
}<span id="Defining"></span>

This topic described some of the more advanced parameter settings for Transfer CFT folder monitoring.

You can use the file\_include\_filter or file\_exclude\_filter parameters to define file name patterns to include or exclude files from folder monitoring.

The filter\_type parameter value indicates how the comparison of file names against the patterns occurs. The possible filter\_type parameter values are **STRJCMP**, **WILDMAT**. and **EREGEX**.

## STRJCMP filter

A STRJCMP pattern-matching filter can contain the asterisk (\*) and/or the question mark (?) characters. The STRJCMP filter characters are interpreted as follows:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Character         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>*         </td>
         <td>Indicates any sequence of zero or more characters.         </td>
         <td>The filter "*.dat" selects any file name that has the extension ".dat".         </td>
      </tr>
      <tr>
         <td>?         </td>
         <td>Indicates any single character.         </td>
         <td>The filter "T*.???" selects any file name starting with a 'T' and having an extension of exactly three characters.         </td>
      </tr>
   </tbody>
</table>

<span id="WILDMAT"></span>

## WILDMAT filter

**Unix/Windows only**

The WILDMAT pattern-matching filter offers more operations than the STRJCMP filter\_type. The WILDMAT filter characters are interpreted as follows, where x and y are used to indicate any character:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Character         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>*         </td>
         <td>Indicates any sequence of zero or more characters.         </td>
         <td>The filter "*.dat" selects any file name that has the extension ".dat".         </td>
      </tr>
      <tr>
         <td>?         </td>
         <td>Indicates any single character.         </td>
         <td>The filter "T*.???" selects any file name starting with a 'T' and having an extension of exactly three characters.         </td>
      </tr>
      <tr>
         <td>\x         </td>
         <td>Indicates that when x is a special character, x is interpreted as a normal character.         </td>
         <td>This is generally used to invalidate the meaning of the * and ? characters.         </td>
      </tr>
      <tr>
         <td>[x...y]         </td>
         <td>Indicates a single character set defined by "x...y".         </td>
         <td><p>The filter [0-9]</p>
<p>indicates any decimal digit.</p>         </td>
      </tr>
      <tr>
         <td>-         </td>
         <td><p>Indicates a range of characters. However, the minus character (or hyphen) has no special meaning if it is either the first or the last character in the set.</p>         </td>
         <td>The filter [0-9a-zA-Z] indicates any alphanumeric character (in English).         </td>
      </tr>
      <tr>
         <td>]         </td>
         <td>Has no special meaning if it is the first character in the set.         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>[^x...y]         </td>
         <td>Indicates any character other than those specified in the set "x...y".         </td>
         <td><p>The  filter [^0-9]</p>
<p>indicates any character that is not a decimal digit.</p>
<p>The filter [^]-] indicates any character other than a closed bracket or minus sign.</p>         </td>
      </tr>
      <tr>
         <td>*.[tT][xX][tT]         </td>
         <td>Indicates any string terminated by .TXT regardless of the case.         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## EREGEX filter

EREGEX (extended regular expressions) is the use of special characters and strings to define a search pattern. In Transfer CFT, you can use these search patterns to create filters.

In POSIX-Extended regular expressions, all characters match themselves meaning they match a sub-string anywhere inside the string to be searched. For example *abc*, matches abc123, 123abc, and 123abcxyz. Some symbols are exceptions though; commonly used symbols and example usages are listed in the following table.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Symbol         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Indicates         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>.         </td>
         <td>Any character except newline (line break)         </td>
         <td><em>a.c</em> matches abc         </td>
      </tr>
      <tr>
         <td>[ ]         </td>
         <td>Or         </td>
         <td><em>[def]</em> means d or e or f         </td>
      </tr>
      <tr>
         <td>{}         </td>
         <td>Exactly         </td>
         <td><em>{3}</em> means exactly three         </td>
      </tr>
      <tr>
         <td>()         </td>
         <td>Capture group         </td>
         <td><em>pand(ora|467)</em> matches pandora OR pand467         </td>
      </tr>
      <tr>
         <td>*         </td>
         <td>0 or more occurrences of the preceding element         </td>
         <td><p><em>ab*c</em> matches ac, abc, abbc, abbbc, and so on</p>         </td>
      </tr>
      <tr>
         <td>+         </td>
         <td>1 or more occurrences of the preceding element         </td>
         <td><em>ab+c</em> matches abc, abbc, abbbc, and so on, but not ac         </td>
      </tr>
      <tr>
         <td>?         </td>
         <td>Zero or one occurrence of the preceding element         </td>
         <td><em>plurals?</em> matches plural         </td>
      </tr>
      <tr>
         <td>|         </td>
         <td>Alternation (matches either the right side or the left) / OR operand         </td>
         <td><em>ab|cd|ef</em> matches ab or cd or ef         </td>
      </tr>
      <tr>
         <td>^         </td>
         <td>Start of a string         </td>
         <td><em>^a</em> matches any file that starts with an a         </td>
      </tr>
      <tr>
         <td>[^ ...]         </td>
         <td>Any single character that is <strong>not</strong> in the class         </td>
         <td><em>[^/]*</em> matches zero or more occurrences of any character that is not a forward-slash, such as http://         </td>
      </tr>
      <tr>
         <td>$         </td>
         <td>End of string         </td>
         <td><em>.*? the end$</em> matches this is the end         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> EREGEX refers to POSIX Extended Regular Expression. There are multiple tutorials available online to aid in creating search patterns; for additional information on expression syntax please refer to Regular expressions.

## Use case

The EREGEX examples describe how to create multiple exclusions using the `INCLUDEFILTER `and `EXCLUDEFILTER `parameters.

### EREGEX example 1

In this example, the following files are not sent from the specified folder – that is, the following files are excluded:

-   out\*.ffs\_lock
-   out\*.jbase\_header
-   out\*.ffs\_db

<!-- -->



    CFTFOLDER    ID          = 'E',
    STATE       = 'ACTIVE',
    METHOD      = 'MOVE',
    RESUBMITCHANGES= 'YES',
    ENABLESUBDIR= 'YES',
    FILEIDLEDELAY= '0',
    IDF         = 'IDFDEF',
    PART        = 'PARIS',
    SCANDIR     = 'e',
    WORKDIR     = 'e_work',
    INTERVAL    = '60',
    FILECOUNT   = '0',
    FILESIZEMIN = '0',
    FILESIZEMAX = '0',
    FILTERTYPE  = 'EREGEX',
    /*           INCLUDEFILTER= '',*/
    EXCLUDEFILTER= '^out.*\.((ffs_lock)|(jbase_header)|(ffs_db))',
    RENAMEMETHOD= 'NONE',
    RENAMESEPARATOR= '.',
    USEFSEVENTS = 'YES',
    MODE        = 'REPLACE'

### EREGEX example 2

Create a filter to include all files that begin with the letter "c" and are followed by any number characters except the ca or cb files.



    CFTFOLDER    ID          = 'F',
    STATE       = 'ACTIVE',
    METHOD      = 'MOVE',
    ....
    FILTERTYPE  = 'EREGEX',
    INCLUDEFILTER='^c+'   #'^c+'
    EXCLUDEFILTER='(^ca$|^cb$)' 
    ...

### EREGEX example 3

Create a filter that includes all .jpg files that are:

-   A word (at least one other word character)
-   Followed by four-digit number

For example, the following filter would include IMGP0122.jpg.



    CFTFOLDER    ID          = 'J',
    STATE       = 'ACTIVE',
    METHOD      = 'MOVE',
    ....
    FILTERTYPE  = 'EREGEX',
    INCLUDEFILTER='^[0-9a-zA-Z]+[0-9]{4}.jpg'
    ...
