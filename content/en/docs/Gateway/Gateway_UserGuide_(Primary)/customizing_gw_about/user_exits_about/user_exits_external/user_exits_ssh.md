{
    "title": "SSH user exits",
    "linkTitle": "SSH user exits",
    "weight": "270"
}{{< Gateway/componentlongname  >}}: Customizing Gateway Processes

This topic describes SSH user exits for SECS processes. SSH exits can be divided into three groups:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Group</p>         </td>
         <td><p>Exits</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#session_management">Session management</a></p>         </td>
         <td><ul>
<li><a href="#ExitSechSessionInit">ExitSechSessionInit</a></li>
<li><a href="#ExitSechSessionEnd">ExitSechSessionEnd</a></li>
<li><a href="#ExitSechSessionSuccess">ExitSechSessionSuccess</a></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="#DH_key_exchange">Diffie Hellman key exchange</a></p>         </td>
         <td><ul>
<li><a href="#ExitSechDhParamsGet">ExitSechDhParamsGet</a></li>
<li><a href="#ExitSechDhParamsSet">ExitSechDhParamsSet</a></li>
<li><a href="#ExitSechDhPubKeyGet">ExitSechDhPubKeyGet</a></li>
<li><a href="#ExitSechDhComputation">ExitSechDhComputation</a></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="#Authentication">Authentication</a></p>         </td>
         <td><ul>
<li><a href="#ExitSechSignaturePerform">ExitSechSignaturePerform</a></li>
<li><a href="#ExitSechSignatureVerify">ExitSechSignatureVerify</a></li>
<li><a href="#ExitSechPublicParamsGet">ExitSechPublicParamsGet</a></li>
<li><a href="#ExitSechPublicParamsSet">ExitSechPublicParamsSet</a></li>
<li><a href="#ExitSechUserPasswordGet">ExitSechUserPasswordGet</a></li>
<li><a href="#ExitSechUserPasswordSet">ExitSechUserPasswordSet</a></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

## About SSH user exits

Gateway invokes SSH exits during the SSH negotiation phase of the session-layer handshake process.

<span id="return_code"></span>An invoked SSH exit returns one of three possible values:

<table>
         
         
         
   
   <thead>
      <tr>
<th style="padding-right: 5px; padding-left: 5px; padding-top: 2px; padding-bottom: 2px; background-color: #EFEFEF; border-top-style: Solid; border-right-style: Solid; border-bottom-style: Solid; border-bottom-width: 1px; border-right-width: 1px; border-left-width: 1px; border-left-style: Solid; border-top-width: 1px"><p>Return value</p>         </th>
<th style="padding-right: 5px; padding-left: 5px; padding-top: 2px; padding-bottom: 2px; background-color: #EFEFEF; border-top-style: Solid; border-right-style: Solid; border-bottom-style: Solid; border-bottom-width: 1px; border-top-width: 1px; border-right-width: 1px"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>0</p>         </td>
         <td><p>No action. The exit asks Gateway to proceed normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>The exit processes performed successfully. The exit asks Gateway to use the returned exit parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>–1</p>         </td>
         <td><p>Fatal error. Aborts the current session handshake negotiation without invoking the ExitSechSessionEnd exit.</p>
<p><strong>Note:</strong> In general it is recommended that you do not return a –1 value. It is preferable to return a 1 value with a –1 status.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="session_management"></span>

## SSH Session management exits

<span id="ExitSechSessionInit"></span>

### ExitSechSessionInit

#### Purpose

This exit is called when a new SSH session begins. The exit classes the session as <span style="font-style: italic;">Client</span> or <span style="font-style: italic;">Server</span>.

#### Syntax

int ExitSecshSessionInit(In\_ExitSecshSessionInit\_t \*in, Out\_ExitSecshSessionInit\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsSessionInit</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecshSessionInit_t *in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecshSessionInit_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechSessionEnd"></span>

### ExitSechSessionEnd

#### Purpose

This exit is called when an SSH session terminates. You can use this exit to release all allotted resources.

#### Syntax

int ExitSecshSessionEnd

(InExitSecshSessionEnd\_t \*in, OutExitSecshSessionEnd\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSecsSessionEnd</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSecshSessionEnd_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSecshSessionEnd_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechSessionSuccess"></span>

### ExitSechSessionSuccess

#### Purpose

This exit is called to indicate that the current SSH session has been successfully established. The exit receives the SSH algorithms used for negotiation as input parameters.

#### Syntax

int ExitSechSessionSuccess

(InExitSechSessionSuccess\_t \*in, OutExitSechSessionSuccess\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechSessionSuccess</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechSessionSuccess_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechSessionSuccess_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="DH_key_exchange"></span>

## SSH Diffie Hellman key exchange exits

Gateway calls key exchange exits at the beginning of key exchange negotiation. The practical value of these exits for users is limited. We recommend that you let Gateway handle negotiations with its standard set of processes.

For detailed information about the Diffie Hellman algorithm refer to the SSH transport layer protocol documentation at [www.ietf.com](http://www.ietf.com).

<span id="ExitSechDhParamsGet"></span>

### ExitSechDhParamsGet

#### Purpose

This exit is called to request the <span style="font-style: italic;">p</span> and <span style="font-style: italic;">g</span> parameters for the Diffie Hellman algorithm, to be sent to the remote partner. This exit is called only if the key exchange algorithm has the value <span class="code" style="font-weight: bold;">DH\_GROUP\_EXCHANGE\_SHA1</span> or **DH\_GROUP\_EXCHANGE\_SHA256**.

#### Syntax

int ExitSechDhParamsGet

(InExitSechDhParamsGet\_t \*in, OutExitSechDhParamsGet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechDhParamsGet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechDhParamsGet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechDhParamsGet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechDhParamsSet"></span>

### ExitSechDhParamsSet

#### Purpose

This exit is called to provide the <span style="font-style: italic;">p</span> and <span style="font-style: italic;">g</span> parameters for the Diffie Hellman algorithm, acquired from the remote partner. This exit is called only if the key exchange algorithm has the value <span class="code" style="font-weight: bold;">DH\_GROUP\_EXCHANGE\_SHA1 </span>or<span class="code" style="font-weight: bold;"> DH\_GROUP\_EXCHANGE\_SHA256</span>.

#### Syntax

int ExitSechDhParamsSet

(InExitSechDhParamsSet\_t \*in, ExitSechDhParamsSet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechDhParamsSet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechDhParamsSet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechDhParamsSet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechDhPubKeyGet"></span>

### ExitSechDhPubKeyGet

#### Purpose

This exit requests the Diffie Hellman public key that is sent to the remote partner.

#### Syntax

int ExitSechDhPubKeyGet

(InExitSechDhPubKeyGet\_t \*in, OutExitSechDhPubKeyGet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechDhPubKeyGet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechDhPubKeyGet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechDhPubKeyGet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechDhComputation"></span>

### ExitSechDhComputation

#### Purpose

This exit requests the calculation of a shared secret via the public key provided as input.

#### Syntax

int ExitSechDhComputation

(InExitSechDhComputation\_t \*in, OutExitSechDhComputation\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechDhComputation</p>         </td>
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
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="Authentication"></span>

## Authentication exits

<span id="ExitSechSignaturePerform"></span>

### ExitSechSignaturePerform

#### Purpose

This exit requests the return of a signature created via your private key using the hash furnished as input. According to the algorithm indicated, this may require a private RSA key, a private DSS key, a private RSA key or a private ECDSA key linked to your x509 certificate.

#### Syntax

int ExitSechSignaturePerform

(InExitSechSignaturePerform\_t \*in, OutExitSechSignaturePerform\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechSignaturePerform</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechSignaturePerform_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechSignaturePerform_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechSignatureVerify"></span>

### ExitSechSignatureVerify

#### Purpose

This exit requests a verification of the transfer partner certificate using the partner's public key. The verification result must correspond to the hash provided as input. According to the indicated algorithm, you provide the RSA public key, the DSS public key, the ECDSA public key or the partner's x509 certificate.

#### Syntax

int ExitSechSignatureVerify

(InExitSechSignatureVerify\_t \*in, OutExitSechSignatureVerify\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechSignatureVerify</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechSignatureVerify_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechSignatureVerify_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechPublicParamsGet"></span>

### ExitSechPublicParamsGet

#### Purpose

This exit requests your public parameters for forwarding to the exchange partner. According to the indicated algorithm, you provide your public RSA key, your public DSS key or your x509 certificate. In client mode, Gateway only calls this exit if the client authentication mode is <span style="font-style: italic;">public key</span>. In mode server this exit is always called.

#### Syntax

int ExitSechPublicParamsGet

(InExitSechPublicParamsGet\_t \*in, OutExitSechPublicParamsGet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechPublicParamsGet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechPublicParamsGet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechPublicParamsGet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechPublicParamsSet"></span>

### ExitSechPublicParamsSet

#### Purpose

This exit provides the public parameters sent by the partner. According to the indicated algorithm, you obtain the partner public RSA key, the partner public DSS key or the partner x509 certificate. In client mode, Gateway always calls this exit. In server mode, Gateway calls the exit only when the authentication method is set to <span style="font-style: italic;">public key</span>.

#### Syntax

int ExitSechPublicParamsSet

(InExitSechPublicParamsSet\_t \*in, OutExitSechPublicParamsSet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechPublicParamsSet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechPublicParamsSet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechPublicParamsSet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechUserPasswordGet"></span>

### ExitSechUserPasswordGet

#### Purpose

This exit requests the user name and user password to send to the partner server.

#### Syntax

int ExitSechUserPasswordGet

(InExitSechUserPasswordGet\_t \*in, OutExitSechUserPasswordGet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechUserPasswordGet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechUserPasswordGet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechUserPasswordGet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to [SSH security exit data structures](#SSH_data_structures).

<span id="ExitSechUserPasswordSet"></span>

### ExitSechUserPasswordSet

#### Purpose

This exit provides the user name and password sent by the partner client for verification.

Gateway only calls this exit when operating in server mode.

#### Syntax

int ExitSechUserPasswordSet

(InExitSechUserPasswordSet\_t \*in, OutExitSechUserPasswordSet\_t \*out)

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSechUserPasswordSet</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>InExitSechUserPasswordSet_t*in</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutExitSechUserPasswordSet_t *out</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p><a href="#return_code">Exit processing return code</a></p>         </td>
      </tr>
   </tbody>
</table>

For more information, refer to <span style="font-style: italic;">SSH security exit data structures</span>.

## Subsequent ssh exit calls

To pass custom user data in subsequent ssh exit calls, use the <span class="code">SechStatus\_t->userContext</span> field of the <span class="code">OutExitSechSession</span>\*<span class="code">\_t </span> structures. <span class="code">ExitSechSession</span>\* functions that fills this member, must return <span class="code">1</span> for the value saved in <span class="code">userContext, </span>to be taken into account and passed to subsequent exit calls.

All subsequent exits following the one that filled <span class="code">userContext</span>, will receive that value in the <span class="code">userContext </span>field of the **in** parameter (<span class="code">InExitSech</span>\*<span class="code">\_t</span> structures). If this value is changed, it has to be saved in the corresponding **out** parameter (see above) and the exit changing this value must return 1. Note that this value can be *changed* only in session-related exits, but it is *available* as input for all exits.

To pass this value to the transfer exits, store it in the output parameter of the <span class="code">ExitSechSessionSuccess </span>function. The reason for this is that the file transfer context is aware of the connection only if the session was successfully established. Don't forget to return <span class="code">1</span> from this function to be able to pass the value.

<span id="SSH_data_structures"></span>

## SSH security exit data structures (exitxdef.h file)

Here is an example extract of the SSH structures in an <span class="code">exitxdef.h</span> header file.


       SECH : secs exits for SSH protocol
    *******************************************************************************/
    /*
     *   SECH status
     */
    typedef struct
    {
       int  status; /* exit code : 0 = ok, -1 = error */
       int  reason; /* applicative processing result */
       char userContext[ITP_SECS_UCONTEXT_MAX];
    } SechStatus_t;
    /*
     *   SECH session initialization
     */
    typedef struct
    {
       int  sessionIdentifier;
       int  connectionEnd; /* SSH_CLIENT or SSH_SERVER */
       char sshProf[ITP_SSH_PROF_NAME_MAX+1]; /* current ssh profile name */
       /* client only : user name and password from the site */
       char userName[ITP_USER_NAME_MAX+1];
       char password[ITP_PASSWORD_MAX+1];
       /* client only : the called remote site */
       char siteName[ITP_SITE_NAME_MAX+1];
       /* server only : network called address  */
       unsigned char destAddress[NET_COMM_ADDRESS_MAX+1];
       /* server only : network calling address */
       unsigned char srcAddress[NET_COMM_ADDRESS_MAX+1];
       /* server only : X.25 user data */
       unsigned char userData[NET_COMM_USER_DATA_MAX];
       /* PassPort PS server location */
       unsigned char xppAddress[NET_ADDRESS_MAX+1];
       int  xppPort;
    } InExitSechSessionInit_t;
    typedef struct
    {
       /* flags indicating whether overriding security profile parameters or not */
       short securityOption_p;
       short version_p;
       short keyExchangeAlgos_p;
       short cipherAlgos_p;
       short macAlgos_p;
       short compressionAlgos_p;
       short publicKeyAlgos_p;
       short clientAuthMethods_p;
       short performAllAuthMethods_p;
       short userName_p;
       short MBytesBeforeNewKeys_p;
       short minutesBeforeNewKeys_p;
       short __filler_p[2];
       SechStatus_t status;
       int securityOption;                             /* none or ssh */
       int version;                                    /* protocol version */
       int nbKeyExchangeAlgos;                         /* nb value in list below */
       int keyExchangeAlgos[ITP_SSH_MAX_KEY_EXCHANGE]; /* key exchange algos */
       int nbCipherAlgos;                              /* nb value in list below */
       int cipherAlgos[ITP_SSH_MAX_CIPHER];            /* encryptions algorithms */
       int nbMacAlgos;                                 /* nb value in list below */
       int macAlgos[ITP_SSH_MAX_MAC];                  /* mac algorithms */
       int nbCompressionAlgos;                         /* nb value in list below */
       int compressionAlgos[ITP_SSH_MAX_COMPRESSION];  /* compression algorithms */
       int nbPublicKeyAlgos;                           /* nb value in list below */
       int publicKeyAlgos[ITP_SSH_MAX_PUBLIC_KEY];     /* public key algorithms */
       int nbClientAuthMethods;                        /* nb value in list below */
       int clientAuthMethods[ITP_SSH_MAX_AUTH_METHOD]; /* client auth methods */
       int performAllAuthMethods;                      /* all methods required */
       char userName[ITP_USER_NAME_MAX+1];             /* user name, client only */
       int MBytesBeforeNewKeys;                        /* MBytes to receive or send before negotiating new keys */
       int minutesBeforeNewKeys;                       /* Minutes to wait before negotiating new keys */
       char __filler[248];
    }  OutExitSechSessionInit_t;
    /*
     *   SECH session ending
     */
    typedef struct
    {
       int  sessionIdentifier;
       char __filler[128];
    } InExitSechSessionEnd_t;
    typedef struct
    {
       SechStatus_t status;
       char __filler[128];
    } OutExitSechSessionEnd_t;
    /*
     *   SECH session success
     */
    typedef struct
    {
       int  sessionIdentifier;
       int keyExchangeAlgo;
       int publicKeyAlgo;
       int cipherAlgoCS;
       int cipherAlgoSC;
       int macAlgoCS;
       int macAlgoSC;
       int compressionAlgoCS;
       int compressionAlgoSC;
       char __filler[128];
    } InExitSechSessionSuccess_t;
    typedef struct
    {
       SechStatus_t status;
       char __filler[128];
    } OutExitSechSessionSuccess_t;
    /*
     *   SECH Diffie Hellmann parameters get
     */
    typedef struct
    {
       int  sessionIdentifier;
       char __filler[128];
    } InExitSechDhParamsGet_t;
    typedef struct
    {
       SechStatus_t status;
       int pLen;
       unsigned char p[ITP_DH_KEY_MAX];
       unsigned char g;
       char __filler[128];
    } OutExitSechDhParamsGet_t;
    /*
     *   SECH Diffie Hellmann parameters set
     */
    typedef struct
    {
       int  sessionIdentifier;
       int pLen;
       unsigned char p[ITP_DH_KEY_MAX];
       unsigned char g;
       char __filler[128];
    } InExitSechDhParamsSet_t;
    typedef struct
    {
       SechStatus_t status;
       char __filler[128];
    } OutExitSechDhParamsSet_t;
    /*
     *   SECH Diffie Hellmann public key get
     */
    typedef struct
    {
       int  sessionIdentifier;
       char versionString[ITP_SSH_VERSION_STRING_MAX+1];
       char __filler[128];
    } InExitSechDhPubKeyGet_t;
    typedef struct
    {
       SechStatus_t status;
       int pubKeyLen;
       unsigned char pubKey[ITP_DH_KEY_MAX];
       char __filler[128];
    } OutExitSechDhPubKeyGet_t;
    /*
     *   SECH Diffie Hellmann computation
     */
    typedef struct
    {
       int  sessionIdentifier;
       int pubKeyLen;
       unsigned char pubKey[ITP_DH_KEY_MAX];
       char __filler[128];
    } InExitSechDhComputation_t;
    typedef struct
    {
       SechStatus_t status;
       int sharedSecretLen;
       unsigned char sharedSecret[ITP_DH_KEY_MAX];
       char __filler[128];
    } OutExitSechDhComputation_t;
    /*
     *   SECH signature perform
     */
    typedef struct
    {
       int  sessionIdentifier;
       int algorithmIdentifier;
       int hashLen;
       unsigned char hash[ITP_HASH_MAX];
       char __filler[128];
    } InExitSechSignaturePerform_t;
    typedef struct
    {
       SechStatus_t status;
       int algorithmIdentifier;
       union
       {
          struct
          {
             int signatureLen;
             unsigned char signature[ITP_RSA_SIGN_MAX];
          } rsa;
          struct
          {
             int rLen;
             unsigned char r[ITP_DSS_SIGN_MAX];
             int sLen;
             unsigned char s[ITP_DSS_SIGN_MAX];
          } dss;
          struct
          {
            int signatureLen;
            unsigned char signature[ITP_ECDSA_SIGN_MAX];
          } ecdsa;
       } value;
       char __filler[128];
          } OutExitSechSignaturePerform_t;
    /*
     *   SECH signature verify
     */
    typedef struct

                               {

                                      int  sessionIdentifier;
                            

                                  int algorithmIdentifier;

                                  union

                                  {

                                  struct

                                  {

                                  int signatureLen;

                                  unsigned char signature[ITP_RSA_SIGN_MAX];

                                  } rsa;


                                  struct

                                  {

                                  int rLen;

                                  unsigned char r[ITP_DSS_SIGN_MAX];

                                  int sLen;

                                  unsigned char s[ITP_DSS_SIGN_MAX];

                                  } dss;


                                  struct

                                  {

                                  int signatureLen;

                                  unsigned char signature[ITP_ECDSA_SIGN_MAX];

                                  } ecdsa;


                                  } value;

                                  int hashLen;

                                  unsigned char hash[ITP_HASH_MAX];


                                  char __filler[256];

                               } InExitSechSignatureVerify_t;
    typedef struct
    {
       SechStatus_t status;
       int algorithmIdentifier;
       int isSignatureVerified;
       char __filler[128];
    } OutExitSechSignatureVerify_t;
    /*
     *   SECH public parameters get
     */
    typedef struct
    {
       int  sessionIdentifier;
       int algorithmIdentifier;
       char __filler[128];
    } InExitSechPublicParamsGet_t;

                               typedef struct

                               {

                                  SechStatus_t status;


                                  char userName[ITP_USER_NAME_MAX+1];


                                  int algorithmIdentifier;

                                  union

                                  {

                                  struct

                                  {

                                  int nLen;

                                  unsigned char n[ITP_RSA_KEY_MAX];     /* modulus          */

                                  int eLen;

                                  unsigned char e[ITP_RSA_KEY_MAX];     /* public exponent  */

                                  } rsa;


                                  struct

                                  {

                                  int pLen;

                                  unsigned char p[ITP_DSS_KEY_MAX];     /* prime modulus    */

                                  int qLen;

                                  unsigned char q[ITP_DSS_KEY_MOD_MAX]; /* prime divisor    */

                                  int gLen;

                                  unsigned char g[ITP_DSS_KEY_MAX];     /* order of q mod p */

                                  int yLen;

                                  unsigned char y[ITP_DSS_KEY_MAX];     /* public key       */

                                  } dss;


                                  struct

                                  {

                                  int pointLen;

                                  unsigned char point[2 * ITP_ECDSA_KEY_MAX + 1];     /* public key - Point coordinates (x and y) */

                                  } ecdsa;


                                  struct

                                  {

                                  int certificateLen;

                                  unsigned char certificate[ITP_CERT_LIST_MAX];

                                  } x509v3Sign;

                                  } value;


                                  char __filler[256];

                               } OutExitSechPublicParamsGet_t;
    /*
     *   SECH public parameters set
     */
    typedef struct

                            {

                            int  sessionIdentifier;


                            char userName[ITP_USER_NAME_MAX+1];


                            int algorithmIdentifier;

                            union

                            {

                               struct

                               {
           int nLen;
           unsigned char n[ITP_RSA_KEY_MAX];     /* modulus          */
               int eLen;
           unsigned char e[ITP_RSA_KEY_MAX];     /* public exponent  */
           } rsa;


                               struct

                               {

                               int pLen;

                               unsigned char p[ITP_DSS_KEY_MAX];     /* prime modulus    */

                               int qLen;

                               unsigned char q[ITP_DSS_KEY_MOD_MAX]; /* prime divisor    */

                               int gLen;

                               unsigned char g[ITP_DSS_KEY_MAX];     /* order of q mod p */

                               int yLen;

                               unsigned char y[ITP_DSS_KEY_MAX];     /* public key       */

                               } dss;


                               struct

                               {

                               int certificateLen;

                               unsigned char certificate[ITP_CERT_LIST_MAX];

                               } x509v3Sign;


                               struct

                               {

                               int pointLen;

                               unsigned char point[2 * ITP_ECDSA_KEY_MAX + 1];     /* point (x and y)*/

                               } ecdsa;

                            } value;


                            char __filler[256];

                            } InExitSechPublicParamsSet_t;
    typedef struct
    {
       SechStatus_t status;
       char __filler[128];
    } OutExitSechPublicParamsSet_t;
    /*
     *   SECH user password get
     */
    typedef struct
    {
       int  sessionIdentifier;
       char __filler[128];
    } InExitSechUserPasswordGet_t;
    typedef struct
    {
       SechStatus_t status;
       char userName[ITP_USER_NAME_MAX+1];
       char password[ITP_PASSWORD_MAX+1];
       char __filler[128];
    } OutExitSechUserPasswordGet_t;
    /*
     *   SECH user password set
     */
    typedef struct
    {
       int  sessionIdentifier;
       char userName[ITP_USER_NAME_MAX+1];
       char password[ITP_PASSWORD_MAX+1];
       char __filler[128];
    } InExitSechUserPasswordSet_t;
    typedef struct
    {
       SechStatus_t status;
       char __filler[128];
    } OutExitSechUserPasswordSet_t;
    #endif /* _EXITXDEF_H */
     


     

Related topics

[About user exits](../../)

[External user exits](../)

[User exits: Security functions](../user_exits_security_functions)

[TLS user exits](../user_exits_tls)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
