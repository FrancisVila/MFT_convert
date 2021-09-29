{
    "title": "About cftapi2",
    "linkTitle": "About cftapi2",
    "weight": "350"
}# About cftapi2



The catalog functions enable you to query and modify the catalog. These functions also include a method to recover information about the <span>Transfer CFT</span> that is using the catalog.



Additionally, the API catalog supports 32 character identifiers and 512 character file names.



## Return code values



The return code values are available in the <span>cftapi2.h</span> header file, located in the <span>Transfer\_CFT/home/inc</span> directory (for UNIX/Windows), in the section *Error code fields*.



## Data structure



The data structures that are used by the API are as follows:



-   Current session in progress: CftApi2Session

-   Catalog: CftApi2Catalog

-   Selection: CftApi2Selection

-   Saved catalog record: CftApi2Record



The programmer can set pointers to these data structures. These are then allocated and initialized by the API.



## API functions



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>CftApi2Session *ipcai2_initialize ()</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Initializes the API.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>None.</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>This function returns a pointer to the CFTApi2Session. If the returned value is NULL, the session cannot be initialized.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_get_errno(CftApi2Session * session)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Recuperates the latest error code.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>session: Pointer to the CftApi2Session is returned by the initialization function ipcai2_initialize()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>The last error code for the API for this session.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>This function can be used after all calls to the API except for ipcai2_initialize() and ipcai2_finalize().</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_get_errno_str(CftApi2Session * session, char *buffer, int bufflen)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Recuperates the error message.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>session: Pointer to the CftApi2Session structure is returned by the initialization function ipcai2_initialize()<br/>

buffer: The buffer that will be informed of the error message.<br/>

bufflen: Length of the buffer sent to the API.</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>If the return code is positive, it contains the last error code for the API for this session.</p>
<p>If the Return code is negative, the buffer is too short. If this happens, and the code is equal to –n where n is equal to the required length.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>This function can be used after all calls to the API except for ipcai2_initialize() and  ipcai2_finalize().</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_finalize(CftApi2Session * session)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Closes the API.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>session: Pointer to the CftApi2Session structure returned by the initialization function ipcai2_initialize()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>None.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td>CftApi2Catalog *ipcai2_catalog_open(CftApi2Session * session, char *catalog_fname)</td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Opens the <span>Transfer CFT</span> catalog file.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>session: Pointer to the CftApi2Session structure returned by the initialization ipcai2_initialize()<br/>

catalog_fname: Name of the catalog file. If the file name is "" the API opens the catalog file by default, for example _CFTCATA for <span>Transfer CFT</span>UNIX.</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>This function returns a pointer to the CftApi2Catalog structure. If the returned value is NULL, the catalog cannot be opened and the error code is returned by calling ipcai2_get_errno().</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_reload_cache(CftApi2Catalog *catalog)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Reloads the catalog cache.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>catalog: Pointer to the catalog returned by ipcai2_catalog_open()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>None.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_close(CftApi2Catalog * catalog</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Closes the catalog.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>catalog: Pointer to the catalog returned by ipcai2_catalog_open()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>Calling  ipcai2_get_errno() ou ipcai2_get_errno_str()  enables you to recuperate the return code for this function.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>CftApi2Selection *ipcai2_catalog_selection_new(CftApi2Catalog *catalog)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>New selection in the catalog.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>catalog: The pointer to the catalog returned by ipcai2_catalog_open()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>This function returns a pointer to a CftApi2Selection structure. If the returned value is NULL the selection cannot be initialized and an error code is returned by calling ipcai2_get_errno().</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_selection_ref(CftApi2Selection *selection)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>References a selection.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>Selection: The pointer for the selected structure returned by calling ipcai2_catalog_selection_new()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>Negative or null: Error, recuperated the error code from ipcai2_get_errno() or ipcai2_get_errno_str().<br/>

Positive: Total number of sessions referenced after this call.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>A selection can be referenced several times, and must be referenced at least one time before it is used.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_selection_set(CftApi2Selection * selection, char *param, char *value)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Initializes a parameter selection.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>selection: Pointer for the selected structure referenced by ipcai2_catalog_selection_ref()<br/>

param: Modify selection parameter. Selection parameter available in cftapi2.h under “Selection parameters” section: CFTAPI2_SELECTION_*<br/>

value: Parameter value in a character string</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>None.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_selection_next(CftApi2Selection *selection)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Executes a selection.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>selection: Pointer for the selection is referenced by ipcai2_catalog_selection_ref()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>A call to ipcai2_get_errno() ou ipcai2_get_errno_str() enables you to recover the return code for this function.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_record_get(CftApi2Selection * selection, char *param, char *buffer, int bufflen)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Recovers a saved field from the selected catalog.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>selection: Pointer for the selection structure is referenced by ipcai2_catalog_selection_ref().<br/>

param: Parameter to be recovered. The parameter to be recovered is available in cftapi2.h in the “Catalog record fields” section: CFTAPI2_RECORD_*<br/>

buffer: Buffer that will be informed with the parameter value<br/>

bufflen: Length of the buffer sent by the API</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>If the Return code is positive it contains the last API error code for this session. If the return code is negative, the buffer is too short and the code is equal to –n where n is the required length for the buffer. </p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_selection_unref(CftApi2Selection *selection)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>De-lists a selection.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>selection: Pointer to a selection structure that references  ipcai2_catalog_selection_ref()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>Negative: Error, recovered the error code by calling ipcai2_get_errno() or ipcai2_get_errno_str()<br/>

Null: Okay, and no other referred sessions.<br/>

Positive: Total number of referred sessions after this call.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_selection_delete(CftApi2Selection *selection)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Deletes a selection.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>selection: Pointer to a selection that is not referred by calling ipcai2_catalog_selection_unref()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>A call to ipcai2_get_errno() or ipcai2_get_errno_str()  enables you to recover the Return code for this function.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_transfert_change_state(CftApi2Selection * selection, char state)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Modifies the transfer state for the selected catalog.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>selection: Pointer to a selection carried out by ipcai2_catalog_selection_next()</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>None.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>The <span>Transfer CFT</span> API must have already opened the communication medium.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_catalog_info_get(CftApi2Catalog *catalog, char *param, char *buffer, int bufflen)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Recovers catalog information.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>catalog: Pointer to the catalog structure returned by ipcai2_catalog_open()<br/>

param: Recover parameter is available in cftapi2.h under the “Catalog information parameters” section heading: CFTAPI2_CAT_INFO_*<br/>

buffer: Buffer that will be informed of the parameter value.<br/>

bufflen: Length of the buffer sent to the API.</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>If the Return code is positive it contains the last API error code for this session.</p>
<p>If the return code is negative, the buffer is too short. The code is equal to –n ,where the n is equal to the required length.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



 



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>Service</p></td>
<td><p>long ipcai2_monitor_info_get(CftApi2Catalog *catalog, char *param, char *buffer, int bufflen)</p></td>
</tr>
<tr>
<td><p>Definition</p></td>
<td><p>Recovers information about the <span>Transfer CFT</span>.</p></td>
</tr>
<tr>
<td><p>Parameter</p></td>
<td><p>catalog: Pointer to the catalog returned by ipcai2_catalog_open()<br/>

param: Parameter to recover. The parameter is available in cftapi2.h under “Monitor information parameters” topic : CFTAPI2_MON_INFO__*<br/>

buffer: Buffer that was provided the parameter value .<br/>

bufflen: Length of the buffer sent to the API.</p></td>
</tr>
<tr>
<td><p>Return value</p></td>
<td><p>If the return code is positive, it contains the last API error code for the session.</p>
<p>If the return code is negative, the buffer is too short. In this case, the code is equal to –n where n is the required length.</p></td>
</tr>
<tr>
<td><p>Remarks</p></td>
<td><p>None.</p></td>
</tr>
</tbody>
</table>



#### Examples of API usage



The heading file cftapi2.h and the commented example source files are delivered with the product.



Related topics



[About <span>Transfer CFT</span> services in C](Using_CFT_services_in_C.htm)



[About application

programming interfaces](../Using_APIs.htm)

