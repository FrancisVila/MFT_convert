{
    "title": "C API primitives",
    "linkTitle": "Primitives",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

[Error reporting on API primitives](#error_reporting)

[API primitive descriptions](#api_primitive_descriptions)

<span id="error_reporting"></span>

## Error reporting on API primitives

All primitives (except GikErrMsg) return the following:

-   <span style="font-weight: bold;">0</span>   if the call is successful
-   <span style="font-weight: bold;">1</span>   if an error is detected:
    -   the error value is indicated in a global variable, ErrCod
    -   the GikErrMsg function returns the text of the error
    -   the ErrCod variable is declared and automatically set by the GikAPI functions

<span id="api_primitive_descriptions"></span>

## API primitive descriptions

<span id="GikSetTraceLevel"></span>

### GikSetTraceLevel

#### Syntax

int GikSetTraceLevel (short traceLevel)

#### Description

Use the GikSetTraceLevel function to set the desired trace level. The <span class="code">traceLevel</span> parameter can be:

-   <span class="code">GIK\_NO\_TRACE</span>: No trace activated. Only fatal errors are displayed.
-   <span class="code">GIK\_WARNINGS</span>: Warnings are displayed.
-   <span class="code">GIK\_INFOS</span>: Information and warnings are displayed.

Errors and warnings are displayed in the standard error output "stderr".

Information is displayed in the standard output "stdout".

<span style="font-weight: bold;">Note:</span> If you do not call GikSetTraceLevel, the trace level is set to <span class="code">GIK\_NO\_TRACE</span>.

<span id="GikSessionOpen"></span><span id="GikSessionOpenFromNotif"></span>

### GikSessionOpen / GikSessionOpenFromNotif

#### Syntax

int GikSessionOpen (char \*cs\_profile\_name, char \*user, char \*password, char \*new\_password, void \*\*session)

#### Description

The GikSessionOpen function opens the communication session. This function provides access security features, to use the interface in client/server mode. You must call this function before you use any other API primitive.

Use the GikSessionOpenFromNotif function to open the session from external exits.

GikSessionClose() must be called to close the session at the end of the program.

Use the GikSessionCloseFromNotif function to close a session opened with GikSessionOpenFromNotif.

The parameter <span class="code">cs\_profile\_name</span> identifies the section in the client <span class="code">CSCONFIG.INI</span> file that describes the target server. If you open the session locally, this parameter is ignored.

#### Example

The following section in the <span class="code">CONFIG.INI</span> file on the Gateway client station describes the Gateway "Gateway\_1":


    [Gateway_1]
    HostName=193.56.234.29
    Port=23000

If the client station wants to open a session with this Gateway, the <span class="code">cs\_profile\_name</span> must be Gateway\_1.

If not NULL, the parameter <span class="code">new\_password</span> is used to modify the user password.

<span style="font-weight: bold;">Note:</span> The returned session handle must be supplied in calls to other primitives.

<span id="GikSessionClose"></span><span id="GikSessionCloseFromNotif"></span>

### GikSessionClose / GikSessionCloseFromNotif

#### Syntax

int GikSessionClose (void \*session)

#### Description

This function closes the communication session and releases all resources.

The last Transfer Request locked is automatically unlocked.

<span style="font-weight: bold;">Note:</span> No API primitive is available after a call to this function.

Use the function GikSessionCloseFromNotif to close a session opened using GikSessionOpenFromNotif.

<span id="GikErrMsg"></span>

### GikErrMsg

#### Syntax

char \*GikErrMsg()

#### Description

When an error occurs, API primitives return <span style="font-weight: bold;">1</span> and set an error code in the global variable <span class="code">ErrCod</span>. This function returns the error message text that corresponds to the value of ErrCod.

<span style="font-weight: bold;">Note:</span> It is recommended that you copy the contents of the buffer into your program space. A subsequent call to GikErrMsg() overrides the contents of the buffer.

#### Return value

The return value is a pointer to a Gateway internal static buffer containing the text that explains the error.

<span id="GikGetErrCod"></span>

### GikGetErrCod

#### Syntax

int GikGetErrCod ()

#### Description

When an error occurs, API primitives return <span style="font-weight: bold;">1</span> and set an error code in the global variable <span class="code">ErrCod</span>. This function returns the value of ErrCod.

#### Return value

The return value is the error code.

<span id="GikInitParams"></span>

### GikInitParams

#### Syntax

int GikInitParams (short type, void \*\*params)

#### Description

This function retrieves a handle on an empty parameter list.

Parameter types can be:

-   GIK\_TRANSFER Creates parameters list for use in GikXferPut, GikXferGet, GikXferGetNext or GikXferUpdate requests
-   GIK\_SELECTION Creates parameters list for use in GikXferOpenSet request

Calls to GikSetxxx or GikGetxxx primitives fill or read the parameter list.

<span style="font-weight: bold;">Note:</span> You must call GikFreeParams to free the handle on the list.

<span id="GikFreeParams"></span>

### GikFreeParams

#### Syntax

int GikFreeParams (void \*params)

#### Description

This function frees a handle on a parameter list.

<span id="GikSetxxx"></span>

### GikSetxxx

#### Syntax


    int GikSetInt (void *params, int fieldIdent, int value)
    int GikSetUInt (void *params, int fieldIdent, unsigned int value)
    int GikSetShort (void *params, int fieldIdent, short value)
    int GikSetUShort (void *params, int fieldIdent, unsigned short value)
    int GikSetLong (void *params, int fieldIdent, long value)
    int GikSetULong (void *params, int fieldIdent, unsigned long value)
    int GikSetChar (void *params, int fieldIdent, char value)
    int GikSetUChar (void *params, int fieldIdent, unsigned char value)
    int GikSetString (void *params, int fieldIdent, char *value)
    int GikSetUString (void *params, int fieldIdent, unsigned char *value)
    int GikSetBuff (void *params, int fieldIdent, void *ptr, int length)
    int GikSetTime (void *params, int fieldIdent, time_t value)
    int GikSetOffset (void *params, int fieldIdent, Offset_t value)

#### Description

The GikSetxxx series of functions set the value of a field in the parameters list. The <span class="code">fieldIdent</span> parameter specifies the field to set. The function used must be compatible with the type of the field that you specify. Refer to [C API Transfer and Selection parameters](../c_api_trans_and_sel_paras).

GikSetBuff needs a pointer to the buffer and the buffer length (in bytes). You must:

-   Allocate the buffer
-   Free the buffer by calling GikFreeParams

Before you call GikSetxxx functions, you must call GikInitParams to retrieve the handle on the parameter list.

<span id="GikGetxxx"></span>

### GikGetxxx

#### Syntax


    int GikGetInt (void *params, int fieldIdent, int *value)
    int GikGetUInt (void *params, int fieldIdent, unsigned int *value)
    int GikGetShort (void *params, int fieldIdent, short *value)
    int GikGetUShort (void *params, int fieldIdent, unsigned short *value)
    int GikGetLong (void *params, int fieldIdent, long *value)
    int GikGetULong (void *params, int fieldIdent, unsigned long *value)
    int GikGetChar (void *params, int fieldIdent, char *value)
    int GikGetUChar (void *params, int fieldIdent, unsigned char *value)
    int GikGetString (void *params, int fieldIdent, char *value, int length)
    int GikGetUString (void *params, int fieldIdent, unsigned char *value, int length)
    int GikGetBuff (void *params, int fieldIdent, void *ptr, int *length)
    int GikGetBuffSize (void *params, int fieldIdent, int *size)
    int GikGetTime (void *params, int fieldIdent, time_t *value)
    int GikGetOffset (void *params, int fieldIdent, Offset_t *value)

#### Description

The GikGetxxx series of functions retrieve the value of a field from the parameter list. The <span class="code">fieldIdent</span> parameter specifies the field to retrieve. The data type of the field to retrieve determines which GikGetxxx function to use. Refer to [C API Transfer and Selection parameters](../c_api_trans_and_sel_paras).

-   <span style="font-weight: bold;">GikGetBuff</span>
    -   <span style="font-style: italic;">ptr:</span> buffer that the user allocates
    -   <span style="font-style: italic;">length</span>: allocated size in bytes

GikGetBuff completes the *ptr* buffer on condition that the specified *length* is sufficient. On return, it updates *length* with the actual size used. If the given size *length* is not sufficient, it returns an error.

Before calling GikGetBuff with <span class="code">fieldIdent</span> GIK\_T\_MSG\_BUF, you must set the GIK\_T\_MSG\_MAX parameter. To set GIK\_T\_MSG\_MAX, specify the maximum buffer size you can retrieve for the message.

-   <span style="font-weight: bold;">GikGetBuffSize</span> retrieves the buffer size in bytes.
-   <span style="font-weight: bold;">GikGetString</span> and <span style="font-weight: bold;">GikGetUString</span>:
    -   <span style="font-style: italic;">value</span>: buffer that the user allocates
    -   <span style="font-style: italic;">length</span>: allocated size. If this size is not sufficient, an error is returned.

<span id="GikXferPut"></span>

### GikXferPut

#### Syntax

int GikXferPut (void \*session, void \*xferParams, GikXferIdent\_t \*ident)

#### Description

This function submits a Transfer Request.

The Transfer identifier is returned in the parameter <span class="code">ident</span>. This identifier is used for subsequent operations on the Request.

Before calling the function, the user program must create the parameter list xferParams (using the GikInitParams primitive), and complete it (using GikSetxxx primitives). Refer to [C API Transfer and Selection parameters](../c_api_trans_and_sel_paras).

<span id="GikXferGet"></span>

### GikXferGet

#### Syntax

int GikXferGet (void \*session, int options, GikXferIdent\_t \*ident, void \*xferParams)

#### Description

This function reads the Transfer Request that you specify by its identifier <span class="code">ident</span>, and copies the Transfer parameters in the parameter list <span class="code">xferParams</span>.

Before calling this function:

-   The user program must create the parameter list *xferParams* using the GikInitParams primitive
-   You must initialize the arguments <span class="code">ident</span> (Transfer Request identifier) and <span style="font-style: italic;">options</span> (read option)

The <span style="font-style: italic;">options</span> parameter (XFER\_LOCK or 0) indicates whether the <span style="font-weight: bold;">read</span> operation is locked or not. If the "read" operation is followed by an update or delete operation, the lock option is mandatory.

You can only lock one Transfer record at a time. A record is automatically unlocked when:

-   You lock another Transfer record
-   You perform an update or delete operation successfully

<span id="GikXferUpdate"></span>

### GikXferUpdate

#### Syntax

int GikXferUpdate (void \*session, void \*xferParams)

#### Description

This function modifies a Transfer Request.

You can only call this function after a successful call to a read function (using GikXferGet or GikXferGetNext) with the lock option enabled. To enable the lock option for a read operation, set the *option* parameter to XFER\_LOCK.

The XFER\_LOCK option prevents concurrent user access to the Transfer record. If another user initiates a read operation on a locked Transfer record, the error code E\_FLOCKED is returned.

You can only lock one Transfer record at a time. A record is automatically unlocked when:

-   You lock another Transfer record
-   You successfully update the record

After reading the Transfer Request, the user program uses the GikSetxxx primitives to modify the parameter list obtained (xferParams), and calls GikXferUpdate. Refer to [C API Transfer and Selection parameters](../c_api_trans_and_sel_paras).

<span style="font-weight: bold;">Note:</span> If the Transfer state is ITP\_XFER\_ACKED, ITP\_XFER\_ENDED or ITP\_XFER\_CANCELED, you can only modify the GIK\_S\_USER\_STATE parameter.

<span id="GikXferDelete"></span>

### GikXferDelete

#### Syntax

int GikXferDelete (void \*session)

#### Description

This function deletes a Transfer Request.

You can only call this function after a successful call to a read function (using GikXferGet or GikXferGetNext) with the lock option enabled. To enable the lock option for a read operation, set the *option* parameter to XFER\_LOCK.

The XFER\_LOCK option prevents concurrent user access to the Transfer record. If another user initiates a read operation on a locked Transfer record, the error code E\_FLOCKED is returned.

If you delete a Transfer Request during the file transfer, the transfer aborts and the Request is deleted.

<span id="GikXferUnlock"></span>

### GikXferUnlock

#### Syntax

int GikXferUnlock (void \*session)

#### Description

This function unlocks a Transfer Request that was previously locked during a read operation.

<span id="GikXferOpenSet"></span>

### GikXferOpenSet

#### Syntax

int GikXferOpenSet (void \*session, void \*selectParams)

#### Description

This function is used to select a set of Transfer Requests, depending on the criteria specified in the parameter list <span class="code">selectParams</span>. Refer to [C API Transfer and Selection parameters](../c_api_trans_and_sel_paras).

To select all Transfers, call GikInitParams (to initialize the list selectParams ), but do not set any criteria with GikSetxxx primitives.

<span style="font-weight: bold;">Note:</span> After a successful selection, calls to GikXferGetNext sequentially read the selected Transfer Requests.

After a successful call to GikXferGetNext, you can call the following primitives:

-   GikXferGetNext - to get the next record of the selection
-   GikXferDelete - to delete the Transfer Request that was read
-   GikXferUpdate - to update the Transfer Request that was read
-   GikXferCloseSet - to close the selection

<span id="GikXferGetNext"></span>

### GikXferGetNext

#### Syntax

int GikXferGetNext (void \*session, int options, void \*xferParams)

#### Description

This function reads the Transfer Requests previously selected by the GikXferOpenSet primitive. It copies the Transfer parameters to the parameters list <span class="code">xferParams</span>. Refer to [C API Transfer and Selection parameters](../c_api_trans_and_sel_paras).

Before calling this function:

-   The user program must create the parameter list xferParams with the GikInitParams primitive
-   You must declare and specify the <span style="font-style: italic;">options</span> parameter (read option)

The <span style="font-style: italic;">options</span> parameter (XFER\_LOCK or 0) indicates whether the read operation is locked or not. If the read operation is followed by an update or delete operation, the lock option is mandatory.

You can only lock one Transfer record at a time. A record is automatically unlocked when:

-   You lock another Transfer record
-   You successfully update or delete the record

<span style="font-weight: bold;">Note:</span> The error code E\_FEOF means that no more Transfer records are available.

<span id="GikXferCloseSet"></span>

### GikXferCloseSet

#### Syntax

int GikXferCloseSet (void \*session)

#### Description

This function closes the set of Transfer Requests previously selected using the GikXferOpenSet primitive.

<span id="GikXferModifState"></span>

### GikXferModifState

#### Syntax

int GikXferModifState (void \*session, GikXferIdent\_t \*ident, short action);

#### Description

This function modifies the state of the Transfer identified by the <span class="code">ident</span> parameter.

The Transfer Request does not have to be locked for you to perform this operation.

The *action* parameter can be:

-   CANCEL
-   SUSPEND
-   RESUME (to reactivate a suspended Transfer or to repeat a previous Transfer)

If the *action* parameter does not correspond to one of these states, the function returns the error code E\_WRONGSTATE (Invalid Transfer state).

Related topics

[About C API](../)

[C API usage examples](../c_api_usage_examples)

[C API Transfer and Selection parameters](../c_api_trans_and_sel_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
