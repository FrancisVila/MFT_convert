{
    "title": "Synchronous communication return codes",
    "linkTitle": "Synchronous communication return codes",
    "weight": "530"
}This section describes diagnosing the return code when using synchronous communication with Transfer CFT.

## How to find the return code

You can retrieve synchronous communication return codes using either a programming interface, such as CAPI, or CFTUTIL.

### Using a programming interface

In this method the cftau function locates the return code, as shown in the following example:

<table data-cellspacing="0" data-summary="Reference code example of return code">
   <tbody>
      <tr class="odd">
         <td>            <p>…</p>
            <p>rc = <span>cftau </span>(“SWAITCAT”,” SELECT='IDTU==A000001’”)</p>
            <p>if rc != 0 {</p>
            <p>printf("SWAITCAT NOK RC=%d\n", rc);</p>
            <p>…</p>
            <p>}</p>         </td>
      </tr>
   </tbody>
</table>

### Using CFTUTIL

This method uses the internal variable\_CMDRET in the SEND, RECV, or SWAITCAT commands to retrieve the return code. You can create a script similar to the following example:

<table data-cellspacing="0" data-summary="Reference code example of script to get return code">
   <tbody>
      <tr class="odd">
         <td>            <p>SWAITCAT SELECT='IDTU==”A000001”’</p>
            <p>IF NAME = _CMDRET, VALUE = 0, TYPE = NEQ</p>
            <p>PRINT MSG=”SWAITCAT NOK RC=”</p>
            <p>PRINT MSG=%_CMDRET%</p>
            <p>ENDIF</p>         </td>
      </tr>
   </tbody>
</table>

Note though that the \_CMDRET value is not the same as the CFTUTIL return code, which could be:

-   0: no error
-   4: warning
-   8: error

In the following example the synchronous communication return code is 82, while the CFTUTIL is 8:

<table data-cellspacing="0" data-summary="Reference code example of synchronous communication code">
   <tbody>
      <tr class="odd">
         <td>            <p>5:[CFU] SWAITCAT SELECT='IDTU=="A000001"'</p>
            <p>CFTU25E SWAITCAT _ Error (SWAITCAT_NFOUND: select='IDTU=="A000001"' Not Found)</p>
            <p>CFTU00I (SELECT='IDTU=="A000001"')</p>
            <p>6:[CFU] PRINT MSG=%_CMDRET%</p>
            <p><strong>82</strong></p>
            <p>CFTU00I PRINT _ Correct (MSG=82)</p>
            <p>7:[CFU] /END</p>
            <p>7:[CFU] CFTU00I RETURN _ Correct (<span>CODE=8</span>)</p>
            <p>CFTU20I Number of Command(s) 6</p>
            <p>CFTU20I Number of error(s) 1</p>
            <p>CFTU20I Ending Session on 21/06/2012 Time is 16:06:32</p>
            <p>CFTU20I Session active for 0:01:42</p>         </td>
      </tr>
   </tbody>
</table>

## Send and receive related errors

For the return codes 70 through 79, the error occurred in the SEND or RECV transfer command, and the transfer was not executed.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>RC</th>
         <th>Error</th>
         <th>Description</th>
         <th>Action</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>70         </td>
         <td>APIS_READ_CONF_FILE         </td>
         <td>Media configuration file error.         </td>
         <td>          </td>
      </tr>
      <tr class="even">
         <td>71         </td>
         <td>APIS_PARAM_TIMEOUT         </td>
         <td>TIMEOUT parameter error.         </td>
         <td>See <a href="../../c_intro_userinterfaces/command_summary/parameter_intro/timeout">TIMEOUT</a>.         </td>
      </tr>
      <tr class="odd">
         <td>72         </td>
         <td>APIS_PARAM_LOWPORT         </td>
         <td>LOWPORT parameter error.         </td>
         <td>See <a href="../../c_intro_userinterfaces/command_summary/parameter_intro/lowport">LOWPORT</a>.         </td>
      </tr>
      <tr class="even">
         <td>73         </td>
         <td>APIS_PARAM_HIGHPORT         </td>
         <td>HIGHPOINT parameter error.         </td>
         <td>See <a href="../../c_intro_userinterfaces/command_summary/parameter_intro/highport">HIGHPORT</a>.         </td>
      </tr>
      <tr class="odd">
         <td>74         </td>
         <td>APIS_PARAM_BOTHPORT         </td>
         <td>LOWPORT and HIGHPORT are incompatible or incorrect.         </td>
         <td>See above parameters.         </td>
      </tr>
      <tr class="even">
         <td>75         </td>
         <td>APIS_CREATE_SOCKET         </td>
         <td>Create channel failed.         </td>
         <td>          </td>
      </tr>
      <tr class="odd">
         <td>76         </td>
         <td>APIS_OPEN_SOCKET         </td>
         <td>Open channel failed.         </td>
         <td>          </td>
      </tr>
      <tr class="even">
         <td>77         </td>
         <td>APIS_SOCKET_WRITE         </td>
         <td>Channel write error occurred.         </td>
         <td>          </td>
      </tr>
      <tr class="odd">
         <td>78         </td>
         <td>APIS_SOCKET_READ         </td>
         <td>Channel read error occurred         </td>
         <td>          </td>
      </tr>
      <tr class="even">
         <td>79         </td>
         <td>APIS_CLOSE_SOCKET         </td>
         <td>Close channel failed occurred.         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## SWAITCAT related errors

For the return codes 80 through 87, the error is related to the SWAITCAT command. Refer to the SWAITCAT [Concepts](../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/swaitcat_concepts) or [Examples](../../app_integration_intro/synch_comm_tcpip_intro/sync_transfer_request_tasks) sections for more information.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>RC</th>
         <th>Error</th>
         <th>Description</th>
         <th>Action</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>80         </td>
         <td>APIS_SWAITCAT_FAILED         </td>
         <td>Transfer error.The transfer reached the K or H state.         </td>
         <td>Check the diagnostic,  correct problem if necessary, and restart.         </td>
      </tr>
      <tr class="even">
         <td>81         </td>
         <td>APIS_SWAITCAT_TIMEOUT         </td>
         <td>The transfer was not completed within the time specified by the timeout value. After this timeout error, the transfer can have the status C (current) or D (for example if the network went down), but note that it was not completed.         </td>
         <td>            <p>Check the diagnostic,  correct problem if necessary.</p>
            <p>Repeat SWAITCAT, you may need to repeat several times.</p>         </td>
      </tr>
      <tr class="odd">
         <td>82         </td>
         <td>APIS_SWAITCAT_NFOUND         </td>
         <td>The idtu was not found. The selected criteria provided in the command SWAITCAT cannot find the transfer.         </td>
         <td>Verify the selection parameters in the SWAITCAT command.         </td>
      </tr>
      <tr class="even">
         <td>83         </td>
         <td>APIS_SWAITCAT_DELETED         </td>
         <td>Cannot find the transfer (transfer was deleted).         </td>
         <td>The transfer was created but for some reason it was removed, for example by the DELETE command.         </td>
      </tr>
      <tr class="odd">
         <td>84         </td>
         <td>APIS_SWAITCAT_PARAM_ERROR         </td>
         <td>The command contained an invalid parameter.         </td>
         <td data-mc-conditions="axway_conditions.ScreenOnly">            <p>Error in the command syntax.</p>
            <p>Check the command parameters <a href="../../app_integration_intro/synch_comm_tcpip_intro/sync_transfer_request_tasks">here</a>.</p>         </td>
      </tr>
      <tr class="even">
         <td>87         </td>
         <td>APIS_SWAITCAT_TOO_MANY         </td>
         <td>The number of transfers corresponding to the filter selection for the SWAITCAT command was greater than 1. You cannot select more than 1 transfer.         </td>
         <td>Refine the selection criteria for the command so that it returns a single transfer.         </td>
      </tr>
   </tbody>
</table>
