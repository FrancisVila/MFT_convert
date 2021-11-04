{
    "title": "C API Transfer and Selection parameters ",
    "linkTitle": "Transfer and selection parameters",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

Transfer parameters:

-   [Gateway transfer parameters](#gw_transfer_parameters)
-   [Scheduling transfer parameters](#scheduling)
-   [File/Transfer organization transfer parameters](#ft_organization)
-   [Options transfer parameters](#options)
-   [Message transfer parameters](#message)
-   [PeSIT transfer parameters](#pesit)
-   [FTP transfer parameters](#ftp)
-   [SMTP/POP3 transfer parameters](#smtp_pop3)
-   [X.400 transfer parameters](#x400)
-   [SFTP transfer parameters](#sftp)
-   [Trading Partner transfer parameters](#trading_partner)
-   [Sentinel transfer parameters](#sentinel)
-   [Transfer parameters used <span style="font-style: italic;">only</span> with PUT](#put_only)
-   [Transfer parameters used <span style="font-style: italic;">only</span> with GET](#get_only)

Selection parameters:

-   [Gateway selection parameters](#gw_selection_parameters)

<span id="_transfer_paras"></span>

## Transfer parameters

<span id="gw_transfer_parameters"></span>

### Gateway transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_ORG_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_ALIAS_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DEST_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_ALIAS_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_ORIGINATOR</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DESTINATION</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_LOCAL_AGENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_REMOTE_AGENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_APPLI</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PROTO_FILE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DIR_PATH</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_DIR_PATH_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_FILE_COMPONENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_FILE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PATHNAME (match dir_path + file_component)</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_FILE_PATH_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_REPLY_TO_XFER</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TYPE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_USER_STATE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_MODE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DIRECTION</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_COMPRESSION</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_FILE_TYPE</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PROTO_FILE_TYPE_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_FILE_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PROTO_FILE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PARAM1</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_USER_PARAM_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PARAM2</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_USER_PARAM_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NACK_ACTION</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_REQUEST_METHOD</p>         </td>
         <td><p>Char</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DIR_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_FILE_PATH_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_ROUTE_FROM_XFER</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CONNECTOR_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_CONNECTOR_ID_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_MODEL</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MODEL_NAME_MAX</p>         </td>
      </tr>
   </tbody>
</table>

<span id="scheduling"></span>

### Scheduling transfer parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadD-Column1-Header1">Type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_YDAY</p>         </td>
         <td><p>Short</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DATE_TO_BEGIN</p>         </td>
         <td><p>time_t</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DATE_TO_END</p>         </td>
         <td><p>time_t</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_HIST_CREATE_DATE</p>         </td>
         <td><p>time_t</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PRIORITY</p>         </td>
         <td><p>Short</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RETRY_COUNT_MAX</p>         </td>
         <td><p>Short</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_INTERVAL</p>         </td>
         <td><p>Long</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PERMANENT</p>         </td>
         <td><p>Uchar</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ft_organization"></span>

### File/Transfer organization transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_FILE_ORG</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_REC_FMT</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_REC_LEN</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SYS_DEP</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_FILE_SYS_DEP_PARAM_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_BLOCK_SIZE</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DATA_CODE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PADDING</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X_REC_FMT</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X_REC_LEN</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X_DATA_CODE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_KEY_LEN</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_KEY_OFFSET</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TEXT_FILE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRUNCATING_ALLOWED</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_FILE_LABEL</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_FILE_LABEL_MAX</p>         </td>
      </tr>
   </tbody>
</table>

<span id="options"></span>

### Options transfer parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadD-Column1-Header1">Type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_ACKNOWLEDGMENT_OPTION</p>         </td>
         <td><p>Uchar</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PURGE_OPTION</p>         </td>
         <td><p>Uchar</p>         </td>
      </tr>
   </tbody>
</table>

<span id="message"></span>

### Message transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_MSG_BUF</p>         </td>
         <td><p>C=unsigned char</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_MSG_MAX</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SND_MSG</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_USER_MSGX_MAX</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pesit"></span>

### PeSIT transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_SND_USER</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PESIT_USER_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SND_APPLI</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PESIT_APPLI_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SND_TEXT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PESIT_TEXT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RCV_USER</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PESIT_USER_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RCV_APPLI</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PESIT_APPLI_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RCV_TEXT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PESIT_TEXT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_MAX_REQUEST</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_MAX_FILE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="ftp"></span>

### FTP transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_FTP_COMMAND</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_USER_COMMAND_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_APPEND</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_UNIQ_FILENAME</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="smtp_pop3"></span>

### SMTP/POP3 transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_MAIL_SUBJECT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MAIL_SUBJECT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_ATTACH_EXTRACT_FILE</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_GENERATE_XFB_SUBJECT</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_FROM</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MAIL_ADDRESS_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TO</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MAIL_ADDRESS_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CC</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MAIL_ADDRESS_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_BCC</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MAIL_ADDRESS_MAX</p>         </td>
      </tr>
   </tbody>
</table>

<span id="x400"></span>

### X.400 transfer parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_X420_ORG_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_DEST_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_SITE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_ORIGINATOR</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_RECIPIENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_DN_REQUEST</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_PRIORITY</p>         </td>
         <td><p>short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_IPMID_USER</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_IPMID_USER_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p>X420_USER_RELATIVE_ID</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_BODY_PART_TYPE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_SUBJECT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_MAIL_SUBJECT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_ORIGINATOR_FORMAL_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_ORIGINATOR_FREE_FORM_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_ORIGINATOR_TEL_NUMBER</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_RECIPIENT_FORMAL_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_RECIPIENT_FREE_FORM_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_RECIPIENT_TEL_NUMBER</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_RECIPIENT_RECEIPT_NOTIF_REQ</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_RECIPIENT_REPLY_REQUEST</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_REPLY_TO_IPM_ID_USER</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_REPLY_TO_IPM_ID_USER_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_EXPIRE_DATE_AND_TIME</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_IMPORTANCE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_SENSITIVITY</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>The following parameters are read-only (used only with GET):</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_CONTENT_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p>X400_CONTENT_ID_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_UA_RN_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p>X420_UA_RN_ID_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_MTS_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p>X400_MTS_ID_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_REPLY_DATE_AND_TIME</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_TRANSFER_SIZE</p>         </td>
         <td><p>Ulong</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_TRANSFER_START_TIME</p>         </td>
         <td><p>Ulong</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_TRANSFER_TIME</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_SUBMISSION_TIME</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X420_AUTO_FORWARD</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X400_SUBJECT_MTS_ID</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="sftp"></span>

### SFTP transfer parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadD-Column1-Header1">Type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_NEWLINE_CONVENTION</p>         </td>
         <td><p>Char</p>         </td>
      </tr>
   </tbody>
</table>

<span id="trading_partner"></span>

### Trading Partner transfer parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadD-Column1-Header1">Type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_RECEIPT_REPLY_TO_XFER</p>         </td>
         <td><p>long</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_TYPE</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_NACK_DESC</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_REQ</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_REQ_SYNC</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_REQ_TO</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_SUBTYPE</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_SEND_MODE</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RECEIPT_REPLY_BY_XFER</p>         </td>
         <td><p>long</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_FORMAT</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_SIGN</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_CIPHER</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_COMPRESS</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_ORG</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_DEST</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CONTENT_TYPE</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_STATE</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_CIPHERING_ALGO</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_KEY_CIPHERING_ALGO</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_COMPRESSION_ALGO</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_SIGNING_ALGO</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_RECEIPT_SIGNING_ALGO</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_REPLY_BY_XFER</p>         </td>
         <td><p>long</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_MIC_ALGO</p>         </td>
         <td><p>int</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_MIC</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_MSG_ID</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TRADE_RECEIPT_RECIPIENT</p>         </td>
         <td><p>String</p>         </td>
      </tr>
   </tbody>
</table>

<span id="sentinel"></span>

### Sentinel transfer parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadD-Column1-Header1">Type         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_SENTINEL_TRANSFER_FILTER</p>         </td>
         <td><p>Char</p>         </td>
      </tr>
   </tbody>
</table>

<span id="put_only"></span>

### Transfer parameters used only with PUT

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_T_FROZEN_STATE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DIR_NAME_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>X_VFD_DIR_ALIAS_LEN</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_EX_SENTINEL_IDENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_E_TRKIDENT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_EX_SENTINEL_OBJECTNAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_E_TRKOBJECTNAME_MAX</p>         </td>
      </tr>
   </tbody>
</table>

<span id="get_only"></span>

### Transfer parameters used only with GET

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Supervision information</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_LOCAL_IDENT</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DATE_CREATE</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SEQUENCE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_USER_PROCESSED</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SELECT_REQ</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_REC_COUNT (file_att)</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_FILE_SIZE (file_att)</p>         </td>
         <td><p>offset_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_EXTRACT_DATE (file_att)</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CIPHER_TYPE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_KEY_MATERIAL</p>         </td>
         <td><p>Ustring</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_GROUP_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_GROUP_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>Dynamic information</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_STATE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RETRY_COUNT</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_X_BYTES</p>         </td>
         <td><p>Offset_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_F_BYTES</p>         </td>
         <td><p>Offset_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DATE_BEGIN</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_DATE_END</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_LAST_END_REASON</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_LAST_END_DIAG</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_LAST_END_ERR</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TOTAL_REQUEST</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_TOTAL_FILES</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SPROF (Security)</p>         </td>
         <td><p>String</p>         </td>
         <td><p>SPROF_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CIPHER_SUITE (Security)</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CLIENT_AUTH (Security)</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_SERVER_AUTH (Security)</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>User</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_USERNAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>USER_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_END_XFER_SCRIPT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>FILE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_RCV_MSG</p>         </td>
         <td><p>String</p>         </td>
         <td><p>USER_MSGX_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_MASTER</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NEXT_XFER</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_ENDED</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_TO_BEGIN</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_CANCELED</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_SUSPENDED</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_FROZEN</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_PROGRESSING</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_OTHERS</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_NB_TOTAL</p>         </td>
         <td><p>Ushort</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Protocol information</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_XFER_IDENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>PROTO_XFER_IDENT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_PROTOCOL</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Status information</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CALLED_ADDRESS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>NET_ADDRESS_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_CALLED_SAP</p>         </td>
         <td><p>String</p>         </td>
         <td><p>NET_SAP_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_T_HTTP_HOST_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>HOST_NAME_MAX</p>         </td>
      </tr>
   </tbody>
</table>

<span id="_selection_paras"></span>

## Selection parameters

<span id="gw_selection_parameters"></span>

### Gateway selection parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FieldIdent         </th>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadD-Column1-Header1">Max String         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>GIK_S_LOCAL_IDENT</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_IDENT_INF</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_IDENT_SUP</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_PROTOCOL</p>         </td>
         <td><p>Int</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_ORG_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>PROTO_IDENT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_DEST_ALIAS</p>         </td>
         <td><p>String</p>         </td>
         <td><p>PROTO_IDENT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_YDAY_INF</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_YDAY_SUP</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_SEQUENCE_INF</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_SEQUENCE_SUP</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_FROM_DATE</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_TO_DATE</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_LIST_TRANS_STATE</p>         </td>
         <td><p>short* <strong>Buff</strong></p>
<p>Int (in bytes)</p>         </td>
         <td><p>XFER_LIST_LEN (Max number of short)</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_DIRECTION</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_FILE_TYPE</p>         </td>
         <td><p>String</p>         </td>
         <td><p>PROTO_FILE_TYPE_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_FILE_NAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>PROTO_FILE_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_USERNAME</p>         </td>
         <td><p>String</p>         </td>
         <td><p>USER_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_APPLI</p>         </td>
         <td><p>String</p>         </td>
         <td><p>APPLI_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_USER_STATE</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_TYPE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_MASTER</p>         </td>
         <td><p>Long</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_PROTO_IDENT</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_PROTO_ID_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_FIRSTREC</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_MODE</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_BEGIN_PRIORITY</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_END_PRIORITY</p>         </td>
         <td><p>Short</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_BEGIN_BEFORE</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_BEGIN_AFTER</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_END_BEFORE</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_END_AFTER</p>         </td>
         <td><p>time_t</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_PERMANENT</p>         </td>
         <td><p>Uchar</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_PARAM1</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_USER_PARAM1_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_PARAM2</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_USER_PARAM2_NAME_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>GIK_S_ITEM</p>         </td>
         <td><p>String</p>         </td>
         <td><p>ITP_FILE_NAME_MAX</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About C API](../)

[C API primitives](../c_api_primitives)

[C API usage examples](../c_api_usage_examples)

[Possible Duplicate management for SWIFTNet](../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate)

[SWIFTNet Header Info](../../../connectors_about/swiftnet_about/swiftnet_header_info)

[SWIFTNet Signature List](../../../connectors_about/swiftnet_about/swiftnet_sig_list)

[SWIFTNet Distribution List](../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_distribution_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
