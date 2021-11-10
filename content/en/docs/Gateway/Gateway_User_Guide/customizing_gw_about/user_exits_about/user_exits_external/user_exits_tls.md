{
    "title": "TLS user exits",
    "linkTitle": "TLS  user exits",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

This topic describes the following TLS user exits for SECS processes:

-   [ExitSecsSessionInit](#ExitSecsSessionInit)
-   [ExitSecsSessionEnd](#ExitSecsSessionEnd)
-   [ExitSecsCheckCertList](#ExitSecsCheckCertList)
-   [ExitSecsComputation](#ExitSecsComputation)
-   [ExitSecsGetCertList](#ExitSecsGetCertList)
-   [ExitSecsBuildCaDnList](#ExitSecsBuildCaDnList)
-   [ExitSecsHandshakeDone](#ExitSecsHandshakeDone)
-   [ExitSecsGetSrvPubKey](#ExitSecsSetSrvPubKey)
-   [ExitSecsSetSrvPubKey](#ExitSecsGetSrvPubKey)

## TLS user exits

<span id="ExitSecsSessionInit"></span>

### ExitSecsSessionInit

#### Purpose

This exit is called when the Security Profile to be used is located within the current TLS session. It indicates that a new TLS session is being processed.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>If you decide to use this exit to override the list of ciphers in the TLS security profiles, it is only possible to configure <em>eight</em> TLS ciphers.
(Otherwise, you can configure 32 TLS cyphers; see <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/TLS_Security_profiles__GUI_.htm">Managing TLS Security Profiles</a></em>for further information.         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> This security exit enables you to override the Handshake session parameters taken from the current TLS Profile (sprof). You can select which parameters to override via a set of flags. These flags follow the naming convention:

A flag name is composed of the associated parameter name followed by the sequence<span class="code"> \_p</span>.

<span style="font-weight: bold;">Example:</span> The flag <span class="code">cache\_enabled\_p</span> corresponds to the output parameter <span class="code">cache\_enabled</span>.

A value of 1 for a flag indicates that the parameters taken from the exit output structure should override the corresponding parameters taken from the sprof object.

#### Syntax

int ExitSecsSessionInit(In\_ExitSecsSessionInit\_t \*in, Out\_ExitSecsSessionInit\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsSessionInit</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsInit_t *in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsInit_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsBuildCaDnList"></span>

### ExitSecsBuildCaDnList

#### Purpose

This exit is only called in server mode and is intended to provide the data that is required to build the Certificate Request TLS PDU. Its output structure contains the DER encoded accepted authorities Distinguished Name list to send to the client. This list must be formatted as follows:

<img src="/Images/Gateway/ExitSecsBuildCaDn_756x360.png" class="maxWidth" />

where:

-   Byte 1: certificate type supported list length (>0)

Followed by one to n occurrences of:

-   Byte 1: supported certificate type:
    -   rsa\_sign = 1
    -   dsa\_sign = 2\*
    -   rsa\_fixed\_dh = 3\*
    -   dss\_fixed\_dh = 4\*

(\* = not yet supported by the internal manager)

Followed by:

-   Byte 1 and 2: authority list total length (>2)

Followed by one to n occurrences of:

-   Byte 1 and 2: DER encoded authority Distinguished Name (DN) length (>1)
-   Byte 3 to n: DER encoded authority distinguished name

#### Syntax

int ExitSecsBuildCaDnList

(InExitSecsBuildCaDnList\_t \*in, OutExitSecsBuildCaDnList\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsBuildCaDnList</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsBuildCaDnList_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsBuildCaDnList_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsGetCertList"></span>

### ExitSecsGetCertList

#### Purpose

Gateway calls this exit when it operates in either server or client mode. Use this exit to provide the certification chain to send to the remote partner.

In client mode, the accepted authorities distinguished name list sent by the server is supplied in the exit input structure.

The certification chain built (if possible) must be formatted as follows:

<img src="/Images/Gateway/ExitSecsGetCertList_756x358.png" class="maxWidth" />

Where the bytes represent from 1 to n occurrences of:

-   Byte 1 to 3: DER encoded certificate length
-   Byte 4 to n: DER encoded certificate

<span style="font-weight: bold;">Note:</span> To use the internal product RSA computation mechanisms, complete the private key field in the OutExitSecsGetCertList\_t structure and assign the value 1 to the private\_key\_p flag.

#### Syntax

int ExitSecsGetCertList

(InExitSecsGetCertList\_t \*in, OutExitSecsGetCertList\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsGetCertList</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_ExitSecsSessionGetCert_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitSecsSessionnGetCert_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsCheckCertList"></span>

### ExitSecsCheckCertList

#### Purpose

This exit is called when receiving the remote certificate chain (client and server mode). This command is intended to process the certification path verification.

The certification path given follows the syntax described in the ExitSecsGetCertList definition.

The verification process is used to determine whether the remote partner identity is correct or not. The purpose of such a process is to accept the connection or to refuse it. As detailed in the TLS specification (RFC 2246), various reasons related to the certification path verification may lead to sending an alert (an alert is followed by a disconnection).

For this reason, the output reason field of this exit is mandatory. The available associated reason codes, in case of verification failure, are given in the file <span class="code">secsudefs.h</span>.

#### Syntax

int ExitSecsCheckCertList(InExitSecsCheckCertList\_t \*in,

OutExitSecsCheckCertList\_t \*out)

Input parameters

InExitSecsCheckCertList\_t\*in

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsCheckCertList</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsCheckCertList_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsCheckCertList_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsComputation"></span>

### ExitSecsComputation

#### Purpose

This exit is called at several steps of the negotiation, and is required when the certificate-related exits (ExitSecsGetCertList and ExitSecsCheckCertList) are called. Its purpose is to create the associated RSA (remote public key and local private key) operations that take part in the authentication process.

<span style="font-weight: bold;">Note:</span> To perform RSA computations (in both client and server mode), the corresponding cipher key must be available.

Since the security exits are mostly independent, you can schedule this exit whether the building of the certification path to send, and the checking of the certification path received are internally processed or not. It can be useful when hardware-encryption modules are available on the host machine.

#### Syntax

int ExitSecsComputation

(InExitSecsComputation\_t \*in, OutExitSecsComputation\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsComputation</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsComputation_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsComputation_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsHandshakeDone"></span>

### ExitSecsHandshakeDone

#### Purpose

This exit is scheduled just after the TLS (or SSL) handshake negotiation is finished. It informs you of the security parameters used for the current session.

<span style="font-weight: bold;">Note:</span> Because this is an informative exit, only an overall return code value of 1 can lead to a disconnection.

#### Syntax

int ExitSecsHandshakeDone

(InExitSecsHandshakeDone\_t \*in, OutExitSecsHandshakeDone\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsHandshakeDone</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsHandshakeDone_t *in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsHandshakeDone_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsSessionEnd"></span>

### ExitSecsSessionEnd

#### Purpose

This exit is scheduled when the data transfer is entirely complete.

<span style="font-weight: bold;">Note:</span> This exit is used to indicate that the SECS server internal session context is being deleted.

#### Syntax

int ExitSecsSessionEnd

(InExitSecsSessionEnd\_t \*in, OutExitSecsSessionEnd\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsSessionEnd</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsSessionEnd_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsSessionEnd_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsGetSrvPubKey"></span>

### ExitSecsGetSrvPubKey

#### Syntax

int ExitSecsGetSrvPubKey

(InExitSecsGetSrvPubKey\_t \*in, OutExitSecsGetSrvPubKey\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsGetSrvPubKey</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsGetSrvPubKey_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsGetSrvPubKey_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to [TLS security exit data structures](#TLS_data_structures).

<span id="ExitSecsSetSrvPubKey"></span>

### ExitSecsSetSrvPubKey

#### Syntax

int ExitSecsSetSrvPubKey

(InExitSecsSetSrvPubKey\_t \*in, OutExitSecsSetSrvPubKey\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsSetSrvPubKey</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecsSetSrvPubKey_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecsSetSrvPubKey_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="../user_exits_security_functions#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more details, refer to <span style="font-style: italic;">TLS security exit data structures</span>.

 

<span id="TLS_data_structures"></span>

## TLS security exit data structures (exitxdef.h file)

Here is an example extract of the TLS structures in an <span class="code">exitxdef.h</span> header file.


    /******************************************************************************
       SECS : secs exits for TLS protocol
    *******************************************************************************/
    #define SECS_KEY_MAX                4096/8
    /* SECS status */
    typedef struct
    {
        int  status; /* Executed Exit status code : 0 or -1 */
        int  reason; /* Applicative treatment result */
        char secs_ucontext[ITP_SECS_UCONTEXT_MAX]; /* User Context */
        char message[ITP_SECS_MESSAGE_MAX];
    } secs_status_t;
    /*
     * SECS session initialization.
     */
    typedef struct
    {
        int           session_identifier;
        int           mode;                    /* ITP_SECS_CLIENT or ITP_SECS_SERVER */
        char          sprof[ITP_SPROF_NAME_MAX+1];      /* Current security profile name */
        char          sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];/* User parameter taken from current sprof */
        unsigned char dest_address[NET_COMM_ADDRESS_MAX+1];   /* RESPONDER : network called address  */
        unsigned char src_address[NET_COMM_ADDRESS_MAX+1];    /* RESPONDER : network calling address */ 
        unsigned char user_data[NET_COMM_USER_DATA_MAX];      /* RESPONDER : X.25 user data */
        char     xpp_entity_name[ITP_XPP_ENTITY_NAME_MAX+1]; /* PassPort PS entity for certificates and keys */
        char     xpp_entity_password[ITP_XPP_ENTITY_PASSWORD_MAX+1];/* PassPort PS entity password */
        char     xpp_partner_entity_name[ITP_XPP_ENTITY_NAME_MAX+1]; /* PassPort PS partner entity */
        char     xpp_address[ITP_HOST_NAME_MAX+1];           /* PassPort PS server location */
        int      xpp_port;
        int      xpp_trace_level;
        int      xps_trace_level;
    } InExitSecsSessionInit_t;
    typedef struct
    {
        /* flags indicating whether overriding security profile parameters or not */
        short         cache_enabled_p;
        short         renegotiate_enabled_p;
        short         close_notify_disabled_p;
        short         client_auth_policy_p;
        short         server_auth_policy_p;
        short         cipher_suites_p;
        short         __filler_p[4];
        secs_status_t status;
        short         cache_enabled;                    /* 0=NO, 1=YES                        */
        short         renegotiate_enabled;              /* 0=NO, 1=YES                        */
        short         close_notify_disabled;            /* 0=NO, 1=YES                        */
        int           client_auth_policy;               /* MANDATORY, OPTIONAL or ANONYMOUS   */
        int           server_auth_policy;               /* MANDATORY, OPTIONAL or ANONYMOUS   */ 
        int           nb_cipher_suites;                 /* cipher suites element number       */
        int           cipher_suites[ITP_CIPHER_SUITES_MAX];
       char __filler[128];
    }  OutExitSecsSessionInit_t;
    /*
     * SECS session termination.
     */
    typedef struct
    {
        int           session_identifier;
        char          sprof[ITP_SPROF_NAME_MAX+1];
        char          secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
        char          sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];
        char __filler[128];
    } InExitSecsSessionEnd_t;
    typedef struct
    {
        secs_status_t status;
        char __filler[128];
    } OutExitSecsSessionEnd_t;
    /*
     * SECS key
     */
    typedef struct
    {
        unsigned char modulo[SECS_KEY_MAX];      /* RSA key modulo */ 
        unsigned char private_exp[SECS_KEY_MAX]; /* RSA key private exponent */
        unsigned char public_exp[SECS_KEY_MAX];  /* RSA key public exponent */
    } secs_rsa_key_t;
    typedef struct
    {
        int key_type; /* ITP_SECS_RSA_512, ITP_SECS_RSA_1024, ITP_SECS_RSA_2048 */
        union key_s
        {
            secs_rsa_key_t rsa_key;
        } key;
    } secs_key_t;
    /*
     * SECS certificates to send to partner
     */
    typedef struct
    {
        int       session_identifier;
        char      sprof[ITP_SPROF_NAME_MAX+1];
        char      secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
        char      sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];  
        int       ca_list_len;
        unsigned char ca_list[ITP_CA_DN_LIST_MAX]; /* received DER encoded CA DN list buffer (client only) */ 
        char __filler[128];
    } InExitSecsGetCertList_t;
    typedef struct
    {
        short     private_key_p; /* flag indicating that a private key is provided or not */
        short     cert_list_p;   /* flag indicating whether a cert list is provided or not */
        short     external_cert_ref_p;
        short     __filler_p[2];
        secs_status_t status;
        int       cert_list_len; /* total length of the received DER encoded certifcate chain */
        unsigned char cert_list[ITP_CERT_LIST_MAX]; /* received DER encoded certificate chain */ 
        char      external_cert_ref[ITP_CERT_NAME_MAX+1];
        secs_key_t    private_key; /* private Key to Use for internal RSA computation purpose */
        char __filler[128];
    } OutExitSecsGetCertList_t;
    /*
     * SECS partner certificates checking
     */
    typedef struct
    {
        int      session_identifier;
        char     sprof[ITP_SPROF_NAME_MAX+1];
        char     secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
        char     sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];
        int      cert_list_len;                    /* Total length of the received DER encoded
                                                   certificate chain                        */
        unsigned char cert_list[ITP_CERT_LIST_MAX];     /* Received DER encoded certificate chain   */ 
        char __filler[128];
    } InExitSecsCheckCertList_t;
     
    typedef struct
    {
        short         public_key_p;                  /* flag indicating that a private key is
                                                        provided or not                   */ 
        short         __filler_p[4];
        secs_status_t status;
        secs_key_t    public_key;              * Public key to use for RSA computation    */ 
        char          xpp_partner_entity_name[ITP_XPP_ENTITY_NAME_MAX+1];
        char __filler[128];
    } OutExitSecsCheckCertList_t;
    /*
     * SECS build accepted CA authorities DN list (server only)
     */
    typedef struct
    { 
        int           session_identifier;
        char          sprof[ITP_SPROF_NAME_MAX+1];
        char          secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
        char          sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];
    } InExitSecsBuildCaDnList_t; 
    typedef struct
    {
        short         ca_list_p;
        short         __filler_p[2];
        secs_status_t status;
        int           ca_list_len; /* Total length of the DER encoded CA DN list to send */ 
        unsigned char ca_list[ITP_CA_DN_LIST_MAX]; /* DER encoded CA DN list to send buffer */ 
        char __filler[128];
    } OutExitSecsBuildCaDnList_t; 
    /* 
     * SECS get server public key (server only)
     */
    typedef struct
    {
       int  session_identifier;
       char sprof[ITP_SPROF_NAME_MAX+1];
       char secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
       char sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];  
       char __filler[128];
    } InExitSecsGetSrvPubKey_t;
    typedef struct
    {
       short         srv_pub_key_p; /* indicates that parameter is provided */
       short         __filler_p[2];
       secs_status_t status;
       secs_key_t    srv_pub_key;
       char __filler[128];
    } OutExitSecsGetSrvPubKey_t;
    /* 
     * SECS set server public key (client only)
     */
    typedef struct
    {
       int     session_identifier;
       char    sprof[ITP_SPROF_NAME_MAX+1];
       char    secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
       char    sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];  
       secs_key_t srv_pub_key;
       char __filler[128];
    } InExitSecsSetSrvPubKey_t;
    typedef struct
    {
       secs_status_t status;
       char __filler[128];
    } OutExitSecsSetSrvPubKey_t;
    /*
     * SECS public or private key computation
     */
    typedef struct
    {
        int      session_identifier;
        char     sprof[ITP_SPROF_NAME_MAX+1];
        char     secs_ucontext[ITP_SECS_UCONTEXT_MAX]; 
        char     sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX]; 
        char     external_cert_ref[ITP_CERT_NAME_MAX+1]; /* external reference to the local certificate sent
                                                          if the RSA computation exit is to be scheduled */
        int           key_mode;    /* ITP_SECS_KEY_TYPE_PUB or ITP_SECS_KEY_TYPE_PRV */
        int           cipher_mode; /* ITP_SECS_MODE_ENCIPHER or ITP_SECS_MODE_DECIPHER */
        int           padding_type;
        int           data_len;
        unsigned char data[ITP_COMPUTATION_DATA_MAX];  /* input data to be computed */
        int           hash_len;
        unsigned char hash[ITP_COMPUTATION_DATA_MAX];  /* hash may be used when verifying signature (read only) */
        secs_key_t    key; 
        char __filler[128];
    } InExitSecsComputation_t;
    typedef struct
    {
        short         sign_verified_p;
        short         data_p;
        short         __filler_p[4];
        secs_status_t status;
        int           sign_verified;
        int           data_len;                  /* Length of computed data */
        unsigned char data[ITP_COMPUTATION_DATA_MAX]; /* Result data buffer */
        char __filler[128];
    } OutExitSecsComputation_t;
    /*
     * SECS handshake Done
     */
    typedef struct
    {
        int      session_identifier;
        char     sprof[ITP_SPROF_NAME_MAX+1];
        char     secs_ucontext[ITP_SECS_UCONTEXT_MAX];
        char     sprof_user_param[ITP_SECS_USER_PARAM_SIZE_MAX];
        int      version;      /* Protocol version used during the Handshake */
        int      cipher_suite; /* cipher suite used               */
        int      client_auth;  /* client authentication level     */
        int      server_auth;  /* server authentication level     */
        int      cache_used;   /* Usage of session caching or not */
        char __filler[128];
    } InExitSecsHandshakeDone_t;
    typedef struct
    {
        short    subject_dn_p;
        short    issuer_dn_p;
        short    __filler_p[2];
        secs_status_t status;
        char     subject_dn[DN_NAME_MAX+1]; /* remote subject dn */
        char     issuer_dn[DN_NAME_MAX+1];  /* remote issuer dn  */
        char     __filler[128];
    } OutExitSecsHandshakeDone_t;

Related topics

[About user exits](../../)

[External user exits](../)

[User exits: Security functions](../user_exits_security_functions)

[SSH user exits](../user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
