{
    "title": "Specific symbols and default files",
    "linkTitle": "Specific symbols and default files",
    "weight": "170"
}This
page describes the symbols, default values, and variables used by Transfer
CFT that are specific to each operating system and comprises:

-   Specific
    symbols
-   Default
    files used by CFTUTIL

## Specific symbols

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Description</th>
         <th>Windows</th>
         <th>Unix</th>
         <th>z/OS</th>
         <th>IBM i</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>Logical name prefix</p>
            <p>If the file name begins with this character, this is a logical name interpreted by Transfer CFT.</p>         </td>
         <td>$         </td>
         <td>$ or _         </td>
         <td>            <p>x'5B'</p>
            <p>285 = £</p>
            <p>297 = $</p>         </td>
         <td>            <p>x'4E'</p>
            <p>285 = +</p>
            <p>297 = +</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Wildcard character</p>
            <p>When using the STRJCMP method, a single character that must be an exact match with a character and is used in masks for groups of files and folder monitoring.</p>         </td>
         <td>?         </td>
         <td>?         </td>
         <td>            <p>x' 6F</p>
            <p>285 = ?</p>
            <p>297 = ?</p>         </td>
         <td>            <p>x'6F'</p>
            <p>285 = ?</p>
            <p>297 = ?</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>Separator character (volume)</p>
            <p>For example, a file name can be represented as follows: &lt;unit&gt;&lt;Separator&gt;&lt;unitc&gt;&lt;Separator&gt;&lt;path&gt;&lt;root&gt;&lt;suf&gt;</p>
            <p>In a z/OS environment: UNIT%UNITC%PATH.ROOT.SUF</p>         </td>
         <td>none         </td>
         <td>none         </td>
         <td>            <p>x' 6C'</p>
            <p>285 = %</p>
            <p>297 = %</p>         </td>
         <td>            <p>x '5E'</p>
            <p>285 = ;</p>
            <p>297 = ;</p>         </td>
      </tr>
      <tr class="even">
         <td>Symbolic variable prefix         </td>
         <td>&amp;         </td>
         <td>&amp;         </td>
         <td>            <p>x'50'</p>
            <p>285 = &amp;</p>
            <p>297 = &amp;</p>         </td>
         <td>            <p>x'6F'</p>
            <p>285 = ?</p>
            <p>297 = ?</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>Indirection file name prefix</p>
            <p>Used in a group of files or for an indirection file.</p>
            <p>For example, FNAME=&lt;Indirection prefix&gt;file name</p>         </td>
         <td>#         </td>
         <td>@         </td>
         <td>            <p>x'7B’</p>
            <p>285 = #</p>
            <p>297 = £</p>         </td>
         <td>            <p>x'B1'</p>
            <p>285 = [</p>
            <p>297 = #</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Character introducing the path name of the FNAME parameter (CFTRECV) from which a tree structure is created.</p>
            <p>On Windows, for example, FNAME=pub\+dir1\dir2\ftest</p>         </td>
         <td>+         </td>
         <td>+         </td>
         <td>            <p>+</p>
            <p>Limited to USS files</p>         </td>
         <td>            <p>+</p>
            <p>Limited to HFS files</p>         </td>
      </tr>
   </tbody>
</table>

## Default files used by CFTUTIL

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>File</p></th>
         <th>            <p>Default</p>
            <p>Windows</p></th>
         <th>            <p>Unix</p></th>
         <th>            <p>z/OS</p></th>
         <th>            <p>IBM i</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>Parameters file </p>         </td>
         <td>            <p>$CFTPARM </p>         </td>
         <td>            <p>$CFTPARM</p>         </td>
         <td>            <p> $CFTPARM</p>         </td>
         <td>            <p> +CFTPARM</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Partners file </p>         </td>
         <td>            <p>$CFTPART </p>         </td>
         <td>            <p> $CFTPART</p>         </td>
         <td>            <p> $CFTPART</p>         </td>
         <td>            <p> +CFTPART</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>Catalog file </p>         </td>
         <td>            <p>$CFTCATA</p>         </td>
         <td>            <p> $CFTCATA</p>         </td>
         <td>            <p> $CFTCAT</p>         </td>
         <td>            <p> +CFTCAT</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Communication file </p>         </td>
         <td>            <p>$CFTCOM  </p>         </td>
         <td>            <p> $CFTCOM</p>         </td>
         <td>            <p> $CFTCOM</p>         </td>
         <td>            <p> +CFTCOM</p>         </td>
      </tr>
   </tbody>
</table>
