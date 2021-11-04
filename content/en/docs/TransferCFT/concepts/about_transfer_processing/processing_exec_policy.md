{
    "title": "Processing execution policy ",
    "linkTitle": "Processing execution policy ",
    "weight": "190"
}This topic describes the processing execution policy as follows:

-   [Broadcast request: processing execution policy](#Broadcas)
-   [Group of files request: processing execution policy](#Group)
-   [Both broadcast and group of files request: processing execution policy](#Broadcas2)

<span id="Broadcas"></span>

## Broadcast request

The EXECPRE, EXEC and EXECA parameters of the CFTDEST object define the execution policy for pre-processing, post-processing and acknowledgement processing procedures, respectively, for a broadcast request.

-   EXECPRE: execution policy for a PREEXEC script
-   EXEC: execution policy for EXEC and EXECE scripts
-   EXECA: execution policy for ACKEXEC script to execute at acknowledgment phase

These parameters can have the values:

-   PART: the procedure is executed on all requests, the generic request and its children
-   DEST: the procedure is executed on the generic request
-   CHILDREN: the procedure is executed on children

<span id="Group"></span>

## Group of files request

The EXECSUBPRE, EXECSUB and EXECSUBA parameters of the CFTSEND/CFTRECV object define, respectively, the execution policy for pre-processing, post-processing and acknowledgement processing procedures for a group of files request.

-   EXECSUBPRE: execution policy for PREEXEC script
-   EXECSUB: execution policy for EXEC and EXECE scripts
-   EXECSUBA: execution policy for ACKEXEC script to execute at acknowledgment phase

These parameters can have the values:

-   FILE: the procedure is executed on all requests, the generic request and its children
-   LIST: the procedure is executed on the generic request
-   SUBF: the procedure is executed on children

<span id="Broadcas2"></span>

## Broadcast and group of files request

When mixing both features, a broadcast and group of files, you can specifically define on which request you want to execute the processing procedures.

The result of mixing a broadcast with a group of files creates 3 levels of requests:

-   L1: generic request of broadcast
-   L2: child of generic request of broadcast (L2) and generic request of group of files
-   L3: child of generic request of group of files (L3)

The processing level that is executed when you mix EXEXPRE/EXEC/EXECA and EXESUBPRE/EXECSUB/EXECSUBA parameters is shown in the following table.

<table>
   <tbody>
      <tr>
         <td>          </td>
         <td><p>EXECPRE/EXEC/EXECA for a CFTDEST broadcast request</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>PART         </td>
         <td>DEST         </td>
         <td>CHILDREN         </td>
      </tr>
      <tr>
         <td>EXECSUBPRE/EXECSUB/EXECSUBA<br />
for
<p>CFTSEND/SEND/CFTRECV/RECV</p>
<p>Group of files request</p>         </td>
         <td>FILE         </td>
         <td>L1 + L2 + L3         </td>
         <td>L1         </td>
         <td>L2 + L3         </td>
      </tr>
      <tr>
         <td>LIST         </td>
         <td>L1 + L2         </td>
         <td>L1         </td>
         <td>L2         </td>
      </tr>
      <tr>
         <td>SUBF         </td>
         <td>L1 + L3         </td>
         <td>L1         </td>
         <td>L3         </td>
      </tr>
   </tbody>
</table>

## Improve the file layer service reliability

Setting the uconf c<span class="code">ft.server.transfer.raise\_error\_when\_exec\_not\_found </span>parameter to <span class="code">Yes </span>(default) raises an error if the defined procedure script is not found, which improves the file layer service reliability.

This parameter is applicable to both post-processing (EXEC and EXECE) and ack-processing (ACKEXEC) procedures.
