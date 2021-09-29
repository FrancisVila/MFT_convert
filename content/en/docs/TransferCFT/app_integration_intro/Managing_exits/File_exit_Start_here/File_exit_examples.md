{
    "title": "File exit examples",
    "linkTitle": "File exit examples",
    "weight": "370"
}# File exit examples



This topic provides examples of file exits and the parameter values

for these exits.



### File type exit parameter settings



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>/*--------------------------------------------------------*/<br/>

/* PARAMETER settings for a FILE TYPE EXIT TASK */<br/>

/*--------------------------------------------------------*/<br/>
<br/>

/cftsend     id

      =

exf1     ,</p>
<p>              fcode

   =

BINARY,</p>
<p>                      exit

    =

exfic    ,</p>
<p>                      mode

    =

replace</p>
<p>          cftrecv

    id

      =

exf1     ,</p>
<p>                      fname

   =

'&amp;idtu.rcv',</p>
<p>                      faction

 = delete,</p>
<p>                      fcode

   =

binary,</p>
<p>                      mode

    =

replace</p>
<p>          cftsend

    id

      =

exf2     ,</p>
<p>                      fcode

   =

BINARY,</p>
<p>                      flrecl

  =

80 ,</p>
<p>                      nlrecl

  =

80,</p>
<p>                      frecfm

  =

V,</p>
<p>                      ftype

   =

T,</p>
<p>                      exit

    =

exfic    ,</p>
<p>                      mode

    =

replace</p>
<p>          cftrecv

    id

      =

exf2     ,</p>
<p>                      fname

   =

'&amp;idtu.rcv',</p>
<p>                      faction

 = delete,</p>
<p>                      flrecl

  =

80 ,</p>
<p>                      frecfm

  =

V,</p>
<p>                      ftype

   =

T,</p>
<p>                      mode

    =

replace</p>
<p>          cftexit

    id

      =

exfic,</p>
<p>                      reserv

  =

8192  ,</p>
<p>                      prog

    =

cftexit  ,</p>
<p>                      language

= c,</p>
<p>                      format

  =

v24,</p>
<p>                      waittask

= 5,</p>
<p>                      mode

    =

replace</p></td>
</tr>
</tbody>
</table>



### <span id="User_program"></span>User program



Two user functions are defined in the example below. The IDF is used

to select one of the functions in the exfini initialization function.



The EXFxmp1 user functions:



-   Take charge of

    file-access

-   Take control at

    each step

-   Send 50 records

    ("!!!!! AZERTYUIOP !!!!!...") of 80 bytes

-   Interrupt the

    transfer (ret1 = 9) after 4 consecutive transfers



The EXIT task is deactivated after 5 minutes inactivity (WAITTASK =

5). After de-activation, it is again possible to start a transfer successfully

(the global variable nbsend is reinitialized to 0 on reactivation of the

task).



The EXFxmp2 user function:



-   Does not take charge

    of file access

-   Sends the EXFXMP1.C

    file (in the active directory)

-   Replaces the first

    byte of each non empty record with the ‘?’ character



This sample is delivered with the <span>Transfer CFT</span> product.

Refer to the <span>exfxmp2.c</span> header

in the delivered samples.

