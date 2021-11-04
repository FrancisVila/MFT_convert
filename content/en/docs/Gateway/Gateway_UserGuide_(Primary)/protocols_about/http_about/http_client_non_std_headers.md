{
    "title": "Adding non-standard HTTP headers ",
    "linkTitle": "Adding non-standard HTTP headers",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

## Introduction

Some HTTP servers require specific, non-standard headers when they receive files. For example, they may require an HTTP header such as *X-Transmit-ID*.

The HTTP header extension in Gateway enables you to add such headers in HTTP requests.

The header extension is available for the HTTP protocol only (not for AS2\_HTTP or RN\_HTTP).

### Supported mode, direction and request methods

-   Gateway acting as client
-   Mode: Initiator
-   Direction: Send
-   Supported request methods: POST and PUT (for sending files only)

## Specifying non-standard HTTP headers

Specify the required HTTP headers, along with any CGI parameters, in the Transfer Request `snd_msg` parameter. If you are using the GUI, enter this information in the **Message to send** parameter on the **[Details](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_details_tab)** tab of the Transfer Request.

When you submit the Transfer Request, the non-standard headers found in `snd_msg` will be sent together with the standard HTTP headers.

### How to complete the `snd_msg` parameter

When completing the Transfer Request `snd_msg` parameter, observe the following rules:

-   The HTTP header string must start with `[xs4hh]` and end with `[/xs4hh]`. Anything that follows the ending tag `[/xs4hh]` is treated as CGI parameters.
-   `[xs4hh]` must be the very first string in the `snd_msg` parameter.
-   The HTTP header pairs within the string must use:
    -   "`=`" to separate the HTTP header id from its value
    -   "`&`" to separate HTTP header id/value pairs

      
    **Example:**` X-Transmit-ID=doc1&X-Bla=doc2`
-   The `[xs4hh]` and `[/xs4hh]` separators must not be used for any other purpose (for example, for CGI parameter values).

All of these rules must be respected. If not, Gateway treats all the `snd_msg` strings as CGI parameters.

Note that the convention for non-standard headers is to prefix the header name with X-.

#### Formatting a string containing HTTP headers and CGI parameters

Use the following format:

`[xs4hh]X-Id1=v1&X-Id2=v2[/xs4hh]xfer_par1=val1&xfer_par2=val2`

#### Escape character

If you need to use one of the HTTP header pair separators ("`=`" or "`&`") inside a header field value, you need to use the escape char: `"%"`.

**Example:** To include "`=234`" at the end of a header field value, format the string as follows:

`[xs4hh]X-Id1=v1%=234[/xs4hh]`

The "`=`" is treated as the assignment separator and the "`%=`" is translated into the ordinary equals part of the field value (v1=234).

**Note:** Also use the `"%"` character if you need to escape the percentage character itself.

Related topics

[Using HTTP in client mode](http_using_in_client_mode.htm)

[About HTTP](http_about.htm)

[Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
