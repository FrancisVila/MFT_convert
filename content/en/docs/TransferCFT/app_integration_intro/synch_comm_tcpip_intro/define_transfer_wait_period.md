{
    "title": "Wait for catalog value to reach a state - SWAITCAT",
    "linkTitle": "Wait for catalog value to reach a state - SWAITCAT",
    "weight": "280"
}# Wait for the catalog value to reach a state - SWAITCAT



The SWAITCAT command enables a client to wait until

a given transfer reaches a particular predefined phase, phasestep, or state before acting.



Command syntax: <span>[SWAITCAT](../Command_summary.htm)</span>



Task examples: [SWAITCAT tasks](../CFTUTIL/Admin/Sync_transfer_request_tasks.htm)



Alternatively, you can use the parameters [WSTATES](../CFTUTIL/Parameter_index/wstates.htm) and [WTIMEOUT](../CFTUTIL/Parameter_index/wtimeout.htm) to replace SWAITCAT functionality.



## Command features



The SWAITCAT command enables you to perform the following functions:



-   Serialize transfers

-   Remotely control

    transfers using synchronous communication

-   Synchronize the

    termination of a collection of simultaneous transfers

-   Enhance script

    functioning



SWAITCAT uses synchronous communication for notification when a predefined

phase, phasestep or state is reached. Or, conversely, it can notify CFTUTIL if the

phase, phasestep, or state

is not reached (K or H phasestep).



If the command fails, CFTUTIL sends the return code 8. The SWAITCAT

command specific errors are:



-   SWAITCAT\_FAILED:

    the transfer reached the K or H phasestep

-   SWAITCAT\_TIMEOUT:

    the defined timeout was reached

-   SWAITCAT\_NFOUND:

    no matching transfer was found

-   SWAITCAT\_DELETED:

    the transfer was deleted

-   SWAITCAT\_PARAM\_ERROR: invalid parameter

-   SWAITCAT\_TOO\_MANY:

    too many transfers were selected (more than 2)



### Parameters



-   [SELECT](../CFTUTIL/Parameter_index/select.htm)

-   [STATES](../CFTUTIL/Parameter_index/states.htm)

-   [PHASES](../CFTUTIL/Parameter_index/phases.htm)

-   [PHASESTEPS](../CFTUTIL/Parameter_index/phasesteps.htm)

-   [TIMEOUT](../CFTUTIL/Parameter_index/timeout.htm)



### Select



Use this parameter allows you to filter on a particular transfer so that you can track its status depending on the other defined parameters. This is a

mandatory argument for which the value must be enclosed in double quotes.



<table data-cellspacing="0">
<tbody>
<tr>
<td>SWAITCAT select="EXPRESSION"</td>
</tr>
</tbody>
</table>



**Expression**



<span>Select </span>is a Boolean expression that identifies one transfer.



**Syntax**



See the value section for a list of possible values.



CAT\_ID OP VALUE



(CAT\_ID OP VALUE)



CAT\_ID OP VALUE &amp;&amp; CAT\_ID OP VALUE



CAT\_ID OP VALUE || CAT\_ID OP VALUE



Possible values for CAT\_ID, which filters on the current state:



-   IDTU

-   IDT

-   PART

-   PHASE (A, T, Y, Z, X)

-   PHASESTEP (D, C, H, K, X)

-   STATE   (D,C,T,X,H,K)

-   DIRECT  (RECV,SEND)

-   TYPE    (FILE,MESSAGE,REPLY)

-   MODE    (REQUESTER,SERVER)

-   IDF     

-   IDA

-   COMMENT



Possible values for OP:



-   == equal

-   != different

-   ~= match pattern

    (value with \*,?)

-   /= doesn't match

    pattern

-   &gt;  greater

-   &lt;  lower

-   &gt;= greater or

    equal

-   &lt;= lower  or

    equal



VALUE can be anything between double " or two single ' ' quotes.



### Phases



The Phases parameter is a string that can be composed of A, T, Y, Z, X and waits on the expected final phase.



-   \(A\) Pre-processing: All pre-transfer script execution occurs here

-   \(T\) Transferring: All transfer execution occurs in this phase

-   \(Y\) Post-processing: All post-transfer script execution occurs here

-   \(Z\) Acknowledgement: Acknowledgement reception/send steps and ack script execution occur here

-   \(X\) Done: End condition when all of the previous phases are completed



### Phasesteps



The Phasesteps parameter is a string that can be composed of D, H, C, K, X, E and waits on the expected final phasestep.



-   \(D\) At disposal: The processing of the Phase is ready to be executed; it is ready to go.

-   \(H\) Hold: The processing of the Phase is on hold and waiting for an action to be executed.

-   \(C\) Processing/Current: The Phase processing is being executed.

-   \(R\) Retry: Retries renaming the file using the <span>FACTION retryrename </span>value.

-   \(X\) Done: This phase step only exists for the Done phase, once all previous phases are complete.

-   \(E\) Exit EOT: This phase step only exists for the Post-processing phase, to signal an [end-of-transfer exit](../Prog/Exits/EOT_exit/about_the_end_of_transfer_type_exit.htm).



### States



The states parameter is a string that can be composed of the T, X, Y, Z, N and A states, and filters on the expected final state. The default is "TX".



Possible values for the states parameter are:



-   T: the transfer

    is completed

-   TX: the transfer is completed or reached the X state

-   A: the

    transfer is acknowledged

-   TA: the transfer is completed and acknowledged

-   TXA: the transfer is completed and acknowledged, or the transfer reached the X state and is acknowledged

-   X: the transfer

    reached the X state

-   XA: the transfer

    reached the X state and is acknowledged

-   Y: the transfer completed the post-processing phase

-   Z: the transfer completed the acknowledged phase

-   N: the transfer completed and received a negative acknowledgment



### Timeout



Timeout is the maximum WAIT time in seconds. The default is approximately

one year (365\*24\*3600 s).



## Example



This example selects the first transfer that has the following IDTU.



<table data-cellspacing="0">
<tbody>
<tr>
<td>SWAITCAT select='IDTU=="A00000A"'</td>
</tr>
</tbody>
</table>



The following example filters on transfers having the D state, but completes as soon as the first transfer reaches the TX state (even though there may be more transfers in the D state).



<table data-cellspacing="0">
<tbody>
<tr>
<td>SWAITCAT select='state=="D"',states=TX</td>
</tr>
</tbody>
</table>
