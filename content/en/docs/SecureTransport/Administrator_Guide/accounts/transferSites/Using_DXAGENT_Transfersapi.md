{
    "title": "Using DXAGENT_TRANSFERSAPI variables  in transfer sites",
    "linkTitle": "Using DXAGENT_TRANSFERSAPI variables  in transfer sites",
    "weight": "290"
}The environment variables with the `DXAGENT_TRANSFERSAPI` prefix can be used in the transfer site definition fields to reference properties submitted via the REST API `customProperties` parameter of the `/transfers/operations` request body.

1.  On the *Add Transfer Site* page or the *Edit Transfer Site* page, in the desired property field, type:  
    `${DXAGENT_TRANSFERSAPI_*}`, where \* is an arbitrary name.  
    For example, ${DXAGENT\_TRANSFERSAPI\_FOO}.  
    Concerning the use of Expression language in fields:  

    -   FTP, HTTP, SSH, PeSIT and Folder Monitor support Expression Language in all fields of type string.

    -   FTP, HTTP and SSH support Expression Language also for the certificates (only when provided via the Admin UI).

    -   Refer to the schema for each transfer site for complete picture and understanding of the supportability.

    PeSIT Acknowledgements are not supported when **Expression Language** is used in a transfer site field related to the following fields:

    -   Pre-Connection phase,

    -   Server and Partner passwords,

    -   Checkpoint Interval,

    -   Checkpoint Window.

    **Important note**: Using Expression Language in these fields while PeSIT Acknowledgments are configured could lead to locking of the account.  
      

2.  To trigger a server-initiated transfer using the */transfers* RESTful API resource, you need to set the value of the dynamic property in the request body.  

> **Note:**
>
> Resubmit and Retry are not supported when using ${DXAGENT\_TRANSFERSAPI\_\*} expressions.

**Related topics:**

-   <a href="../t_st_transfersites#Create" class="MCXref xref">Create a transfer site</a>
-   <a href="../t_st_transfersites#Edit" class="MCXref xref">Edit a transfer site</a>
-    
