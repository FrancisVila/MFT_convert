{
    "title": "Creating  transfer templates",
    "linkTitle": "Ongoing CFTRECV",
    "weight": "300"
}<span id="About_the_Ongoing_CFTRECV_object"></span>

## About the ongoing CFTRECV object

Use the CFTRECV object to:

-   Find the name and
    local physical characteristics of the file to receive
-   List actions to
    perform locally during and after the transfer (translation, compression,
    call to a user EXIT, an end-of-transfer procedure, etc.)
-   View authorized
    time slot and default user associated with the transfers

There is no limit on the number of CFTRECV objects that you can create.

<span style="color: #800000;font-weight: bold;text-decoration: underline;">Related
topics</span>

-   Command syntax
    [CFTRECV](../../../command_summary#CFTRECV)
-   Object concepts
    Default receive templates

<span id="About_the_ongoing_CFTSEND_object"></span>

## About the ongoing CFTSEND object

Use the CFTSEND object to specify:

-   The name and local
    physical characteristics of the file to send
-   The network characteristics
    of the file to send to the partner
-   The actions to
    perform locally during and after a transfer (translation, compression,
    call to a user EXIT, an end-of-transfer procedure...)
-   An authorized time
    slot and default user associated with the transfers

There is no limit to the number of CFTSEND objects that you can create.

You can create a default CFTSEND object. The identifier must correspond
to the file identifier <span style="font-weight: bold;">idf</span> or,
if this parameter is not defined, the default parameter of the CFTPARM
object.