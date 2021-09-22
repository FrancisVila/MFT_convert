{
    "title": "Symbolic variables",
    "linkTitle": "Symbolic variables",
    "weight": "160"
}<span id="About_symbolic_variables"></span>A symbolic variable represents
a transfer data item whose value is not known at the time Transfer CFT
parameters are set, but only at the time the transfer is executed. Additionally, the symbolic variable is prefaced by a special character, which is the ‘&’ character in this document. However, you should refer to the Transfer CFT *Installation Guide* that corresponds to
your OS, in order to determine the special character &lt;char\_symb>
used on your system.

For example, prior to a transfer the transfer identifier IDT
is not known, so the symbolic variable &IDT
can be used to reference the value. For more information see [Symbolic variable syntax](#symbolic_variable_syntax).

Symbolic variables may be used in defining the values of certain parameters
of the commands and procedure files associated with transfers. This avoids
having to repeat the same basic descriptions a considerable number of
times: a single CFTSEND command can hence be applied to several files
by using the symbolic variables in the FNAME parameter. This also makes
it possible to only have to describe one transfer-related procedure applicable
to several transfers. The real value of the parameter is substituted for
the symbolic variable, at the time the Transfer CFT command or the procedure
is executed.

### <span id="Symbolic_variable_syntax"></span>Symbolic variable syntax

The symbolic variable syntax is as follows:

-   A special character
    in the first position (leftmost)
-   Optionally followed
    by the character(s):

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Character</th>
         <th>Indicates...</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>+         </td>
         <td>That the variable  toggles to upper case         </td>
      </tr>
      <tr>
         <td>-         </td>
         <td>That the variable  toggles to lower case         </td>
      </tr>
      <tr>
         <td>:         </td>
         <td>That the right padding of the variable is suppressed         </td>
      </tr>
      <tr>
         <td>&lt;         </td>
         <td>The left justification of the variable (default value)         </td>
      </tr>
      <tr>
         <td>&gt;         </td>
         <td>The right justification of the variable         </td>
      </tr>
      <tr>
         <td>%         </td>
         <td>Indicates use of the <a href="#separate">separator syntax</a>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>
            <p>These characters can be used in combination, such as <span>+:</span> or  <span>&gt;+:</span>.     </p>
            <p>See the <a alt="" href="#examples" title="">Example using optional characters</a></p>
         </td>
      </tr>
   </tbody>
</table>

-   Optionally followed
    by a character string to be used as a prefix (-string\_prefix)
    and/or a character string to be used as a suffix (+string\_suffix)
    and/or a character string to be used as a substitute/alternate value (=string\_alternate)
-   Optionally followed
    by a numeric formula with a syntax ‘n’ or ‘p.’ or ‘p.n’
-   And then a character
    string representing the identifier of the variable to be substituted

The identifiers, recognized by Transfer CFT, which can be used in the
syntax of a symbolic variable are indicated in the *[List of symbolic variables](#list_of_symbolic_variables)*.
In this section, the ‘VAR’ notation is used to generically designate such
an identifier.

The substitution mechanism, which is used to assign a value to the symbolic
variable using the effective value of the ‘VAR’ identifier,
depends on the numeric formula indicated after the & character.

According to the syntax used:

-   &VAR syntax
    (numeric formula not used)

    The value substituted for the symbolic variable equals
    the effective value of the ‘VAR’ identifier, truncated of the blank characters
    on the right.

-   &+VAR syntax:

    The value substituted for the symbolic variable is
    shifted to upper case.

-   &nVAR syntax:
    -   The value substituted for the symbolic variable corresponds
        to a fixed length string of n characters, equal to the string corresponding
        to the effective value of ‘VAR’, truncated as required, or with blank
        characters added to the right.
    -   The first character in this string corresponds to
        the first character, from the left, of the string corresponding to the
        value of the ‘VAR’ identifier.

-   &p.VAR syntax:

    The value substituted for the symbolic variable corresponds
    to the character substring formed from the effective value of ‘VAR’ such
    that:

    -   The first character
        of this substring corresponds to the p th character (from the left) of
        the string corresponding to the value of ‘VAR’
    -   The length
        corresponds exactly to the length of the effective value of ‘VAR’, the
        character in the i position being equal to the character in the p+i position
        of the value of ‘VAR’. If the length of the value of ‘VAR’ is m characters,
        the length of the substring will consequently be m-p+1 characters

<!-- -->

-   &p.nVAR syntax:
    -   The value substituted for the symbolic variable corresponds
        to the character sub-string formed from the effective value of ‘VAR’ such
        that:

        The first character
        of this substring corresponds to the p th character (from the left) of
        the string corresponding to the value of ‘VAR’

        This substring
        is n characters long (fixed length), the character in the i position being
        equal to the character in the p+i position of the value of ‘VAR’. If the
        length of the effective value of VAR is less than p+n characters, the
        characters completing the substring are blank characters

&(-string\_prefix)
(+string\_suffix) (=string\_alternate)p.nVAR syntax:

After the &p.nVAR symbolic variable has been substituted:

-   The &lt;str\_prefix>character
    string is added before the variable, if the substituted variable is not
    empty
-   The &lt;str\_suffix>
    character string is added after the variable, if the substituted variable
    is not empty
-   The &lt;str\_alternate>
    character string is used if the substituted variable is empty
-   The character
    strings &lt;str\_prefix>, &lt;str\_suffix> and &lt;str\_alternate>
    can contain a symbolic variable

#### <span id="Separate"></span>Separate fields in a symbolic variable

You can use the field extraction syntax as follows:

&%&lt;separator>\[&lt;start\_field>\[.\[&lt;end\_field>\]\]VARIABLE

1.  If start\_field is omitted, the default value is 1.
2.  If end\_field is omitted, the default value is the last field in the variable.
3.  If there are 2 consecutive separators, the extracted field between the 2 separators is empty.
4.  If there is only one number after the separator indicating the value placement, this returns just that token value.

For the following example, see the corresponding syntax:

&&lt;VARIABLE>=S052368\_Z123\_HZUI34\_92\_\_\_TYU

1.  &%\_.2&lt;VARIABLE>: separator=\_, start\_field=1 , end\_field=2 (this returns the value S052368\_Z123)
2.  &%\_3.&lt;VARIABLE>: separator=\_ , start\_field=3, end\_field=last\_field (this returns the value HZUI34\_92\_\_\_TYU)
3.  &%\_5&lt;VARIABLE>: separator=\_, start\_field=5, end\_field=5 (this returns ' ')
4.  &%\_4&lt;VARIABLE>: separator=\_, start\_field=4, end\_field=4 (this returns 92)

You can combine field extraction with the other filtering methods. The full syntax is:

&\[&lt;|>\]\[+|-\]\[:\]\[(-string\_prefix)(+string\_suffix)(=string\_alternate)\]\[&lt;position>.\]\[&lt;length>\]\[%&lt;separator>\]\[&lt;start\_field>\]\[.\[&lt;end\_field>\]\]&lt;VARIABLE>

#### Example symbolic variable usage

If PART=PART1 and IDF=TEST, then FNAME=&IDF&PART.tst is substituted
by FNAME=TESTPART1.tst

In formats in which "n" or "p" are used, the following
remarks are valid:

-   A value of "n"
    equal to 0 is non significant
-   A value of "p"
    equal to 0 is non significant
-   A position "p"
    greater than the length of the "effective" value of ‘VAR’ gives,
    after substitution, a string of zero length

This allows identifiers of length less than p to be selected, for example.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">&amp;.VAR is substituted as &amp;VAR. The &lt;char_symb&gt; concatenated 
 with a point is substituted as &lt;char_symb&gt;. The rule applies even 
 if VAR is not an identifier known to  <span>Transfer CFT</span>. For example, for the 
 formats &amp;.VAR (&amp;0.VAR, &amp;0.0VAR or &amp;.0VAR), the value substituted 
 is not the effective value of the identifier ‘VAR’ but the literal string 
 &amp;VAR.         </td>
      </tr>
</table>

#### Example of possible formats

Given the generic identifier ‘VAR’ of effective value, the character
string: ‘F2345’.

Depending on the format of the associated symbolic variable, the substituted
values are:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&amp;VAR = ’F2345’</p>
            <p>&amp;3VAR = ’F23’<br/>&amp;7VAR = ’F2345 ’</p>
            <p> </p>
            <p>&amp;.VAR = ’&amp;VAR’ (not substituted)<br/>&amp;.4VAR = 'F2345' </p>
            <p>&amp;1.VAR = ’F2345’<br/>&amp;2.VAR = ’2345’<br/>&amp;5.VAR = ’5’<br/>&amp;6.VAR = ’’</p>
            <p> </p>
            <p>&amp;1.1VAR = ’F’<br/>&amp;2.1VAR = ’2’<br/>&amp;5.1VAR = ’5’<br/>&amp;6.1VAR = ’ ’</p>
            <p> </p>
            <p>&amp;1.2VAR = ’F2’<br/>&amp;2.3VAR = ’234’<br/>&amp;5.6VAR = ’5 ’ (5 blank characters)<br/>&amp;6.7VAR = ’ ’ (7 blank characters)</p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Examples"></span>Example using optional characters

Given the generic identifier ‘VAR’ of an effective value, and the character string: ‘SEND'.

Depending on the associated symbolic variable format, the substituted values are:

![](text_froot.png)

#### <span id="Example"></span>Example of rebuilding filenames using symbolic variables

Given the syntax FNAME=&FROOT&(-.)FSUF:

-   If &FSUF is empty, FNAME gets the value &FROOT
-   If &FSUF is not empty, FNAME gets the value &FROOT.&FSUF

For example, if you have a file readme.txt on two different platforms:

![](text_froot.png)

Given the syntax FNAME=&(=DUMMY)PARM,

-   If &PARM is empty, FNAME gets the value DUMMY
-   If &PARM is not empty, FNAME gets the value &PARM

Given the syntax FNAME=&(-PREF)(+SUF)(=DUMMY)PARM,

-   If &PARM is empty, FNAME gets the value DUMMY
-   If &PARM is not empty, FNAME gets the value PREF&PARMSUFF

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To add a closing parenthesis within the str_prefix, str_suffix and str_alternate, it must be preceded by the character ‘&amp;’:         </td>
      </tr>
</table>

-   Given the syntax FNAME=&(+(1234&))PARM
    -   If &PARM is not empty, FNAME gets the value &PARM(1234)

#### Example of breaking down files names

Break down the name of the file to send using the symbolic variables &FUNIT , &FUNITC , &FPATH , &FROOT , &FSUF (applied to

the SFNAME).

Break down the name of the received file using the symbolic variables &UNIT, &UNITC, &PATH , &ROOT, &SUF (applied to the FNAME).

### <span id="List_of_symbolic_variables"></span>List of symbolic variables

The table below indicates all the symbolic variables available, using
the syntax &VAR. The substituted value, corresponding to the effective
value of the identifier ‘VAR’ (truncated of the blank characters on the
right), is also indicated.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The other syntax shown above may also be used, for each of the identifiers 
 listed.         </td>
      </tr>
</table>

List of symbolic variables

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Domain </th>
         <th>Symbolic variable</th>
         <th>Maximum length</th>
         <th>Corresponding substituted 
 value</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td rowspan="8" valign="top" width="21%">PARTNERS          </td>
         <td valign="top" width="26%">
            <p>&amp;PART </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Partner name (ID of CFTPART) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;GROUP </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Group to which the partner belongs </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SPART </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Sending partner name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;RPART </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Receiving partner name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;IPART </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Intermediate partner name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NPART </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Network name of partner sending data (NSPART or NRPART 
 according to the transfer direction) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;NSPART         </td>
         <td>24         </td>
         <td valign="top">Network identifier by which the 
 local  <span>Transfer CFT</span> identifies itself to its partner         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;NRPART         </td>
         <td>24         </td>
         <td valign="top">
            <p>Network identifier by which the 
 remote partner identifies itself to the local <span>Transfer CFT</span></p>
         </td>
      </tr>
      <tr valign="middle">
         <td rowspan="7" valign="top" width="21%">
            <p>USER </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;SUSER </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Sending user name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;RUSER </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Receiving user name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;USERID </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Local user identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;GROUPID</p>
         </td>
         <td>32         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Group identifier linked to the userid</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;COMMENT </p>
         </td>
         <td>160         </td>
         <td valign="top">
            <p>Comment indicated in CFTSEND/SEND or CFTRECV/RECV </p>In listcat content=debug this is attribute is MSG         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NOTIFY </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>User notified on transfer </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;SJOBNAME         </td>
         <td>15         </td>
         <td valign="top"><span>Transfer CFT</span> job name, can be used in exec and cronjob procedures         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="5" valign="top" width="21%">
            <p>APPLICATIONS </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;SAPPL</p>
         </td>
         <td>
            <p> </p>
            <p>8</p>
            <p>48</p>
         </td>
         <td valign="top">
            <p>Sending application name </p>
            <p>PeSIT E</p>
            <p>PeSIT E CFT/CFT</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;RAPPL </p>
         </td>
         <td>
            <p> </p>
            <p>8</p>
            <p>48</p>
         </td>
         <td valign="top">
            <p>Receiving application name</p>PeSIT E            <p>PeSIT E CFT/CFT</p>         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;IDA </p>
         </td>
         <td>64         </td>
         <td valign="top">
            <p>Application identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;PARM </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Parameter </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;PI99 </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>PI99 contents (PeSIT E) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td rowspan="22" valign="top" width="21%">
            <p>TRANSFER </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;IDT</p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Transfer identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NIDT </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Protocol transfer identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;IDTU </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Local transfer counter (unique)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;PIDTU         </td>
         <td>8         </td>
         <td valign="top">Parent idtu of the child transfers         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;PHASE         </td>
         <td>1         </td>
         <td valign="top">Processing phases to help manage transfer flows         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;PHASESTEP         </td>
         <td>1         </td>
         <td valign="top">Step in processing phase         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;APPSTATE         </td>
         <td>32         </td>
         <td valign="top">State step for the processing
 script to restart  if relaunched         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NSUB </p>
         </td>
         <td>4         </td>
         <td valign="top">
            <p>Counter for the submitting of end-of-transfer procedures, 
 error procedures and procedures submitted by SUBMIT.<br/>If 4 characters long, the counter is reset to 1 after 9999 </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;DIAGI </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Internal diagnostic code value </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;DIAGP </p>
         </td>
         <td>64         </td>
         <td valign="top">
            <p>Protocol diagnostic code value </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;DIAGC         </td>
         <td>254         </td>
         <td valign="top">Complimentary diagnostic code value         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;COMP </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Compression negotiated for the transfer</p>
            <p>Compression negotiated for the transfer</p>
            <p>When listcat content=debug this is attribute is FCOMP / COMPNEG</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NBT </p>
         </td>
         <td>20         </td>
         <td valign="top">
            <p>Number of bytes transferred </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;PRI </p>
         </td>
         <td>3         </td>
         <td valign="top">
            <p><span>Transfer CFT</span> priority for the transfer (0 to 255) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;QQ </p>
         </td>
         <td>3         </td>
         <td valign="top">
            <p>Number of the day in the year associated with the transfer 
 identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SELFNAME </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Name of the generic transfer selection file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FCODE </p>
         </td>
         <td>1         </td>
         <td valign="top">
            <p>Code for the data in a file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;TRTYPE </p>
         </td>
         <td>8         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Available at the end of transfer to designate FILE, MESSAGE, 
 REPLY, or NACK</p>
            <p>When using listcat content=debug the attribute is TYPE</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NCODE </p>
         </td>
         <td>1         </td>
         <td valign="top">
            <p>Code for the data sent over the network </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;EXITFREE                </td>
         <td>64         </td>
         <td valign="top">Free communication area between multiple exits          </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;XLATE         </td>
         <td>32         </td>
         <td valign="top">Transcoding table used during transfer         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;MODE         </td>
         <td>1         </td>
         <td valign="top">
<p valign="top" width="52%">Server mode = ‘S’ transfer </p>
<p valign="top" width="52%">Requester mode =     ‘R’ transfer </p>
         </td>
      </tr>
      <tr valign="middle">
         <td rowspan="33" valign="top" width="21%">
            <p>FILE</p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;IDF </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Model file identifier (logical name)  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FNAME </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Physical file local name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FKEYLEN </p>
         </td>
         <td>5         </td>
         <td valign="top">
            <p>Length (received) of the indexed file key at the sender’s 
 site </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FKEYPOS </p>
         </td>
         <td>5         </td>
         <td valign="top">
            <p>Position (received) of the indexed file key at the sender’s 
 site </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NBR </p>
         </td>
         <td>20         </td>
         <td valign="top">
            <p>Number of records in the file</p>
            <p>For listcat=content debug, this attribute is FRECS </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;BLKNUM </p>
         </td>
         <td>6         </td>
         <td valign="top">
            <p>Catalog block number </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;XLATE </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Identifier of the translation table used </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NBC </p>
         </td>
         <td>20         </td>
         <td valign="top">
            <p>Number of bytes in the transferred file</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NIDF </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Model file network identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FDB </p>
         </td>
         <td>64         </td>
         <td valign="top">
            <p>Database name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;FCHARSET         </td>
         <td>32         </td>
         <td valign="top">Local file  encoding         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;NCHARSET         </td>
         <td>32         </td>
         <td valign="top">Destination file encoding for network  data         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;WORKINGDIR         </td>
         <td>512         </td>
         <td valign="top">Specify a directory other than the default directory         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;HOME         </td>
         <td>512         </td>
         <td valign="top">Keyword that allows different users to work with files placed in their home directory         </td>
      </tr>
      <tr valign="middle">
<th colspan="3" valign="top" width="26%">Receiving </th>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;NFNAME </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Physical file network name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FROOT </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Root (file name) </p>
            <p>Based on the SFNAME (remote sending file)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FSUF </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>File name suffix -</p>
            <p>Based on the SFNAME (remote sending file)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FPATH </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Prefix (file path)  -</p>
            <p>Based on the SFNAME (remote sending file)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;FUNITC          </td>
         <td>512         </td>
         <td valign="top">
<p valign="top">Physical file unit (z/OS) - </p>
<p valign="top">Based on the SFNAME (remote sending file)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FUNIT </p>
            <p> </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Physical file volume - </p>
            <p>Based on the SFNAME (remote sending file)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;UNIT </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Physical file volume name for received file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;UNITC          </td>
         <td>512         </td>
         <td valign="top">Physical file unit class for received file (z/OS)         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;PATH</p>
         </td>
         <td>512         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Local file path of the received file</p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;ROOT</p>
         </td>
         <td>512         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Local file root for the received file</p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;SUF</p>
         </td>
         <td>512         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Local file suffix for the received file</p>
         </td>
      </tr>
      <tr valign="middle">
<th colspan="3" valign="top" width="26%">Sending </th>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;SFNAME         </td>
         <td>512         </td>
         <td valign="top">Name of file to send         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FUNIT </p>
            <p> </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Physical file volume name for sending file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;FUNITC          </td>
         <td>512         </td>
         <td valign="top">Physical file unit for sending file (z/OS)          </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FPATH </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Prefix (file path) of the sending file</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FROOT </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Root (actual file name) of the sending file</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FSUF </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Suffix associated with file name of the sending file</p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="2" valign="top" width="21%">
            <p>MESSAGES</p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;IDM</p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Message identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;MSG </p>
         </td>
         <td>
            <p> </p>
            <p>80</p>
            <p>512</p>
         </td>
         <td valign="top">
            <p>Message text </p>
            <p>PeSIT D CFT</p>
            <p>PeSIT E</p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="5" valign="top" width="21%">
            <p>DATE and TIME associated with a FILE </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;FDATE </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Date associated with the file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FTIME </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Time associated with the file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FYEAR </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Year associated with the file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FMONTH </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Month associated with the file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FDAY </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Day associated with the file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="5" valign="top" width="21%">
            <p>DATE and TIME associated with a CATALOG </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;CDATE </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Catalog entry date </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;CTIME </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Catalog entry time </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;CYEAR </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Catalog entry year </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;CMONTH </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Catalog entry month </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;CDAY </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Catalog entry day </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="11" valign="top" width="21%">
            <p>DATE and TIME associated with a TRANSFER </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;BDATE </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Transfer start date </p>
            <p>When listcat content=debug the start date is</p>
            <p>DATEB instead of BDATE</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;BTIME </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Transfer start time </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;BYEAR </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Start year for the transfer</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;BMONTH </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Start month for the transfer </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;BDAY </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Transfer start day </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;EDATE </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Transfer end date </p>
            <p>When listcat content=debug the end date is</p>
            <p>DATEE instead of EDATE</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;ETIME </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>Transfer end time f</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;EYEAR </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Transfer end year</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;EMONTH </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Transfer end month </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;EDAY </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>Transfer end day </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;TT </p>
         </td>
         <td>10         </td>
         <td valign="top">
            <p>Transmission duration in seconds (TIMES attribute in the  <span>Transfer CFT</span> catalog)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td rowspan="3" valign="top" width="21%">CONTROL OUTPUT          </td>
         <td valign="top" width="26%">
            <p>&amp;FLOG </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Name of last log file used by  <span>Transfer CFT</span> </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;FACCNT </p>
         </td>
         <td>512         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Name of last statistics file used by  <span>Transfer CFT</span> </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;FCAT </p>
         </td>
         <td>512         </td>
         <td valign="top">
            <p>Name of catalog used by  <span>Transfer CFT</span></p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="2" valign="top" width="21%">
            <p>TRACKING</p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;XFRCYCID </p>
         </td>
         <td>250         </td>
         <td valign="top">
            <p>Processing cycle identifier (set of tracked instances that 
 concern a single transfer) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;XFROBJID </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>Tracked object name </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="9" valign="top" width="21%">
            <p>SSL (1) </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;SSL</p>
         </td>
         <td>1         </td>
         <td valign="top">
            <p>Indicates if the session the transfer was carried out on 
 was secured (‘1’) or not (‘0’) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLMODE </p>
         </td>
         <td>1         </td>
         <td valign="top">
            <p>SSL session mode on which the transfer was carried out. 
 (C: Client / S: Server) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLAUTH </p>
         </td>
         <td>1         </td>
         <td valign="top">
            <p>Authentication rule<br/>(A: Anonymous /S: Server / B: Both) </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLCIPH </p>
         </td>
         <td>2         </td>
         <td valign="top">
            <p>SSL cipher suite </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLPROF </p>
         </td>
         <td>32         </td>
         <td valign="top">
            <p>SSL profile identifier </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLPARM </p>
         </td>
         <td>64         </td>
         <td valign="top">
            <p>SSL user parameter Parm parameter of the CFTSSL command </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLRMCA </p>
         </td>
         <td>256         </td>
         <td valign="top">
            <p>Certificate identifier of the authority that signed the 
 certificate presented by the remote partner </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLUSER </p>
         </td>
         <td>256         </td>
         <td valign="top">
            <p>Identifier of the user certificate used locally for authentication 
 by the remote partner </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLCFNAM </p>
         </td>
         <td>64         </td>
         <td valign="top">
            <p>Physical name of the file in which the certificate chain 
 presented by the remote partner was recorded </p>
            <p>This is the same as the CFTSSL CERFNAME parameter value</p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="4" valign="top" width="21%">
            <p>SYSTEM </p>
         </td>
         <td valign="top" width="26%">
            <p>&amp;SYSDATE </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>System date </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SYSTIME </p>
         </td>
         <td>8         </td>
         <td valign="top">
            <p>System time </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;SYSQQ </p>
         </td>
         <td>3         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Number of the day in the year associated with the system 
 date </p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;SYSDAY</p>
         </td>
         <td>1         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Day of the week (Sunday = 0, 6 = Saturday)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td rowspan="9" valign="top" width="21%">
            <p>CAT/ ACCOUNT </p>
            <p>ENVIRONMENT </p>
         </td>
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;CFTNAME</p>
         </td>
         <td>32         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>Name of the  <span>Transfer CFT</span> (CFTPARM PART parameter)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td colspan="1" rowspan="1" valign="top" width="26%">
            <p>&amp;CFTEVENT</p>
         </td>
         <td>16         </td>
         <td colspan="1" rowspan="1" valign="top">
            <p>The type of job submitted by  <span>Transfer CFT</span>, see (2) below</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;SJOBNAME         </td>
         <td>15         </td>
         <td valign="top">The  <span>Transfer CFT</span> jobname, which is the name of the job submitting the cronjob or exec procedure (z/OS)         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;CFTVERSION         </td>
         <td>16         </td>
         <td valign="top">The Transfer CFT version         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;CFTSP         </td>
         <td>16         </td>
         <td valign="top">The latest SP applied to the Transfer CFT          </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;CFTPATCH         </td>
         <td>16         </td>
         <td valign="top">The latest patch applied to the Transfer CFT          </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;CFTTARGET         </td>
         <td>16         </td>
         <td valign="top">The  Transfer CFT platform with additional details required for a support ticket, for example         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">&amp;CFTHOSTOS         </td>
         <td>64         </td>
         <td valign="top">The  Transfer CFT hostname         </td>
      </tr>
      <tr valign="middle">
         <td>&amp;CFTHOSTMACHINE         </td>
         <td valign="top" width="26%">64         </td>
         <td>The  machine processor name where Transfer CFT is running         </td>
         <td valign="top">          </td>
      </tr>
</table>

(1): These variables are linked to SSL use. For additional information,
refer to [Managing Transport Security](../../../transport_security_start_here).

(2): EXEC in SEND, EXECSF, EXECSM, EXEC in RECV, EXECRF, EXECRM, EXECE, EXECSE, EXECRE, EXECA, EXECSFA, EXECSMA, PREEXEC, EXITEOT, EXECSUB, EXECSUBA, EXECSUBPRE

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The symbolic variable formats concerning dates and times are:         </td>
      </tr>
</table>

-   Time: HHMMSSCC
     
-   Complete date: YYYYMMDD
-   Year: YY
-   Month: MM
-   Day: DD

Sender

The symbolic variables are
substituted by the values of the local parameters of the commands.

Receiver

The symbolic
variables are substituted:

-   By the sender parameter
    values when these values are conveyed by the protocol
-   By default, by
    the corresponding local parameter values

## <span id="Using_symbolic_variables"></span>Using symbolic variables

Symbolic variables can be used:

-   To assign a value
    to certain parameters of the parameter setting or transfer commands
-   In the processing
    operations defined by the user in the procedures associated with the transfers

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Symbolic variables</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>WFNAME, NFNAME, FNAME for the <madcap:conditionaltext>CFTSEND/</madcap:conditionaltext>SEND and <madcap:conditionaltext>CFTRECV/</madcap:conditionaltext>RECV commands         </td>
         <td>
            <ul>
               <li>&amp;FDATE, &amp;FTIME, &amp;FYEAR, &amp;FMONTH, &amp;FDAY<br/>               </li>
               <li>&amp;BDATE, &amp;BTIME, &amp;BYEAR, &amp;BMONTH, &amp;BDAY<br/>               </li>
               <li>&amp;SPART, &amp;RPART, &amp;PART, &amp;NPART, &amp;GROUP<br/>               </li>
               <li>&amp;SUSER, &amp;RUSER<br/>               </li>
               <li>&amp;SAPPL, &amp;RAPPL<br/>               </li>
               <li>&amp;IDF, &amp;PARM, &amp;IDA<br/>               </li>
               <li>&amp;NIDF<br/>               </li>
               <li>&amp;NFNAME (only for FNAME and WFNAME)<br/>               </li>
               <li>&amp;IDT (only  the FNAME and WFNAME parameters when you receive a file)<br/>               </li>
               <li>&amp;SYSQQ               </li>
               <li>&amp;WORKINGDIR               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>EXEC, EXECE, PREEXEC for the <madcap:conditionaltext>CFTSEND/</madcap:conditionaltext>SEND and <madcap:conditionaltext>CFTRECV/</madcap:conditionaltext>RECV commands</p>
            <p>EXECRE, 
 EXECSE, EXECRF, EXECSF, EXECSFA, EXECSM, EXECRM, EXECSMA for CFTPARM command</p>
         </td>
         <td>
            <ul>
               <li>&amp;SPART, &amp;RPART, &amp;PART, &amp;GROUP, &amp;NRPART, &amp;NSPART, &amp;USERID,&amp;GROUPID               </li>
               <li>&amp;BDATE, &amp;BTIME, &amp;BYEAR, &amp;BMONTH, &amp;BDAY               </li>
               <li>&amp;CDATE, &amp;CTIME, &amp;CYEAR, &amp;CMONTH, &amp;CDAY               </li>
               <li>&amp;FDATE, &amp;FTIME, &amp;FYEAR, &amp;FMONTH, &amp;FDAY               </li>
               <li>&amp;EDATE, &amp;ETIME, &amp;EYEAR, &amp;EMONTH, &amp;EDAY               </li>
               <li>&amp;COMMENT               </li>
               <li>&amp;SUSER, &amp;RUSER<br/>               </li>
               <li>&amp;SAPPL, &amp;RAPPL<br/>               </li>
               <li>&amp;PARM, &amp;MSG, &amp;PI99<br/>               </li>
               <li>&amp;DIAGI, &amp;DIAGP, &amp;DIAGC<br/>               </li>
               <li>&amp;FNAME*, &amp;UNIT*, &amp;UNITC*, &amp;NFNAME*, &amp;NFVER*, &amp;FDB*, &amp;SELFNAME*, &amp;FUNITC*, &amp;FUNIT*, &amp;FPATH*, &amp;FROOT*, &amp;SFNAME*, &amp;WORKINGDIR*, &amp;HOME*<br/>               </li>
               <li>&amp;IDF*, &amp;PIDTU, &amp;IDTU, &amp;IDT, &amp;NIDT, &amp;NIDF*, &amp;IDA, &amp;IDM, &amp;NSUB, &amp;PATH*, &amp;ROOT*, &amp;SUF* <br/>               </li>
               <li>&amp;FCODE, &amp;NCODE, &amp;fcharset, &amp;ncharset<br/>               </li>
               <li>&amp;BLKNUM<br/>               </li>
               <li>&amp;CFTEVENT, &amp;CFTNAME               </li>
               <li>&amp;FMCL, &amp;MODE, &amp;TRTYPE               </li>
               <li>&amp;FBLKSIZE*, &amp;FKEYLEN*, &amp;FKEYPOS*, &amp;NKEYLEN*, &amp;NKEYPOS*, &amp;FLRECL*, &amp;FORG*, &amp;FRECFM*, &amp;FSPACE*, &amp;FTYPE*               </li>
               <li>&amp;NBR*, &amp;NBC*, &amp;NBT*, &amp;TT, &amp;QQ, &amp;COMP, &amp;NOTIFY, &amp;SYSQQ               </li>
               <li>&amp;SSLAUTH, &amp;SSLCIPH, &amp;SSLMODE, &amp;SSLPROF, &amp;SSLPARM, &amp;SSLRMCN, &amp;SSLRMCA, &amp;SSLUSER, &amp;SSLCFNA, &amp;SSL (See <a href="#transport_security_symbolic_variables">Transport 
 security symbolic variables</a>)               </li>
               <li>&amp;XLATE               </li>
               <li>&amp;SYSDATE, &amp;SYSTIME, &amp;SYSDAY               </li>
               <li>&amp;PRI               </li>
               <li>&amp;XFRCYCID, &amp;XFROBJID               </li>
               <li>&amp;EXITFREE               </li>
               <li>&amp;JOBNAME, &amp;NCHARSET               </li>
               <li>&amp;APPSTATE, &amp;PHASESTEP, &amp;PHASE               </li>
               <li>&amp;<a href="../parameter_intro/sourceappl">SOURCEAPPL</a>, &amp;<a href="../parameter_intro/targetappl">TARGETAPPL</a>               </li>
            </ul>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot use the variables designated by asterisk (*) in procedures 
 associated with the EXEC* parameters relative to message transfers.         </td>
      </tr>
</table></p>
         </td>
      </tr>
      <tr>
         <td>EXEC for CFTACCNT or CFTLOG         </td>
         <td>
               <li>&amp;FACCNT, &amp;FLOG               </li>
         </td>
      </tr>
      <tr>
         <td>TLVCEXEC, TLVWEXEC for CFTCAT         </td>
         <td>&amp;FCAT         </td>
      </tr>
      <tr>
         <td>USERID 
 parameter of the CFTSEND and CFTRECV commands         </td>
         <td>&amp;RUSER, 
 &amp;SUSER, &amp;PART         </td>
      </tr>
      <tr>
         <td>EXIT 
 of the  <span>Transfer CFT</span> CFTSEND/SEND and CFTRECV/RECV commands         </td>
         <td>&amp;IDF         </td>
      </tr>
      <tr>
         <td>FNAME parameter 
 of CFTDEST         </td>
         <td>
            <ul>
               <li>&amp;FDATE, &amp;FTIME, &amp;FYEAR, &amp;FMONTH, &amp;FDAY<br/>               </li>
               <li>&amp;PART, &amp;RPART, &amp;SPART, &amp;NPART, &amp;GROUP<br/>               </li>
               <li>&amp;SUSER, &amp;RUSER<br/>               </li>
               <li>&amp;SAPPL, &amp;RAPPL<br/>               </li>
               <li>&amp;IDF, &amp;PARM, &amp;IDA<br/>               </li>
               <li>&amp;NIDF<br/>               </li>
               <li>&amp;NFNAME, &amp;NFVER               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>The name of the 
 identifier of the IDF parameter of the CFTPROT command         </td>
         <td>
            <ul>
               <li>&amp;NIDF               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>The IDA parameter of SEND and CFTSEND         </td>
         <td>
            <ul>
               <li>&amp;FNAME, &amp;FUNITC, &amp;FUNIT, &amp;FPATH, &amp;FROOT, &amp;FSUF, &amp;NFNAME, &amp;PART, &amp;IDF, &amp;IDTU, &amp;IDT, &amp;IDM, &amp;COMMENT, &amp;SYSDATE, &amp;SYSTIME               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td> SUSER and RUSER parameters of SEND and CFTSEND         </td>
         <td>
            <ul>
               <li>&amp;USERID, &amp;FNAME, &amp;FUNITC, &amp;FUNIT, &amp;FPATH, &amp;FROOT, &amp;FSUF, &amp;NFNAME, &amp;PART, &amp;IDA, &amp;IDF, &amp;IDTU, &amp;IDT, &amp;IDM, &amp;COMMENT, &amp;SYSDATE, &amp;SYSTIME, &amp;FCHARSET, &amp;NCHARSET               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>PARM, SAPPL, RAPPL parameters of SEND and CFTSEND         </td>
         <td>
            <ul>
               <li>&amp;FNAME, &amp;FUNITC, &amp;FUNIT, &amp;FPATH, &amp;FROOT, &amp;FSUF, &amp;NFNAME, &amp;PART, &amp;IDA, &amp;IDF, &amp;IDTU, &amp;IDT, &amp;IDM, &amp;COMMENT, &amp;SYSDATE, &amp;SYSTIME, &amp;FCHARSET, &amp;NCHARSET               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

**Example**

A file name can consist of the day’s date and the partner’s name:  the
description command for the PAY file in reception.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RECV IDF = PAY, FNAME = PAY&amp;4PART.&amp;FDAY         </td>
      </tr>
   </tbody>
</table>

When a file of this type is received from the ALPHSITE partner on July
14 13:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RECV PART = ALPHSITE, IDF = PAY         </td>
      </tr>
   </tbody>
</table>

Transfer CFT creates and writes to a file: PAYALPH.14

See the end-of-transfer examples in [Transfer-related
procedure examples](../../../concepts/about_transfer_processing/procedure_examples).

## Defining symbolic variable blacklists for processing scripts

UNIX and Windows only

You can use blacklist characters as a POSIX Regular Extended expression to define forbidden characters in a processing script. To prevent unauthorized actions, do not use these characters in symbolic variables.

Defining the blacklist

Use the uconf cft.server.processing\_scripts\_variables\_blacklist parameter to define the character sequence to forbid. We recommend setting this parameter to **\`|\\$\\(|;|&|\\|** for UNIX, and **"&"** for Windows.

UNIX

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>uconfset id=cft.server.processing_scripts_variables_blacklist , value= "`|\$\(|;|&amp;|\|"         </td>
      </tr>
   </tbody>
</table>

When setting the blacklist values shown above, the forbidden characters are: **\`** and **$(** and **;** and **&** and **|**  
For example, if &PARM="$(ls)"or if `` &PARM="`ls`" ``, then the EXEC is not executed because of the **$(** or the **\`** characters, respectively.

Windows

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>uconfset id=cft.server.processing_scripts_variables_blacklist , value="&amp;"         </td>
      </tr>
   </tbody>
</table>

DIAGI 158

This DIAGI indicates that there was an error while replacing the Transfer CFT variables.

Log messages

-   CFTS67E: Error replacing variable &lt;var> &lt;error message>
-   CFTS68E: PART=&part \[IDF=&idf | IDM=&idm\]IDT=&idt \_ &fname not executed

## <span id="Transport_security_symbolic_variables"></span>Transport security symbolic variables

This section describes additional
symbolic variables relating to transport security. These symbolic variables
can be used in end-of-transfer procedures EXECRF, EXECSF, EXECRM, and
so on. These variables indicate whether transport security is used, and if
so, the session parameters such as the authentication mode, suite negotiated
and certificates used.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Symbolic variable</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSL </p>
         </td>
         <td valign="top" width="74%">
            <p>Indicates whether security was implemented (1 = 
 yes, 0 = no) for the session in which the transfer was performed. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLMODE </p>
         </td>
         <td valign="top" width="74%">
            <p>Direction of the SSL session in which the transfer was 
 performed.</p>
            <p>C signifies client and 
 S signifies server. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLAUTH </p>
         </td>
         <td valign="top" width="74%">
            <p>Authentication mode of the SSL session in which the transfer 
 was performed.</p>
            <ul>
               <li>S 
 signifies that only the server was authenticated.               </li>
               <li>B 
 signifies that the client and server were authenticated.               </li>
               <li>A 
 signifies that the anonymous mode  has 
 been implemented.                </li>
            </ul>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLCIPH </p>
         </td>
         <td valign="top" width="74%">
            <p>Suite negotiated for the SSL session.</p>
            <p>This suite is set to one of the values from the suites 
 supported by Transfer CFT (1, 2, 4, 5, 9, 10 or 47). </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLPROF </p>
         </td>
         <td valign="top" width="74%">
            <p>Identifier of the CFTSSL command used to negotiate the 
 session parameters. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLPARM </p>
         </td>
         <td valign="top" width="74%">
            <p>Value of the PARM parameter in the CFTSSL command used 
 to negotiate the session parameters. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLRMCA </p>
         </td>
         <td valign="top" width="74%">
            <p>Certificate identifier of the authority that signed the 
 certificate presented by the remote partner. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLRMCN </p>
         </td>
         <td valign="top" width="74%">
            <p>Remote user certificate CN field. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLUSER </p>
         </td>
         <td valign="top" width="74%">
            <p>Identifier of the user certificate used locally for authentication 
 by the remote partner. </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="26%">
            <p>&amp;SSLCFNAM </p>
         </td>
         <td valign="top" width="74%">
            <p>Physical name of the file in which the certificate chain 
 presented by the remote partner was recorded. This is the same as the CFTSSL CERFNAME parameter value.</p>
         </td>
      </tr>
</table>
