{
    "title": "REST API",
    "linkTitle": "REST API",
    "weight": "290"
}# <span>Transfer CFT</span> REST API concepts



This section describes how to use REST API to automate access to <span>Transfer CFT</span> resources. Available resources include administration, configuring, transferring files, and viewing the log and catalog (create, modify, view and delete transfers).



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The REST API server only accepts HTTPS connections.</td>
</tr>
</tbody>
</table>



## Audience



You should have a working knowledge of <span>Transfer CFT</span> and an understanding of basic REST API concepts to implement <span>Transfer CFT</span> REST API.



## REST API documentation



The [Transfer CFT API documentation](http://apidocs.axway.com/swagger-ui/index.html?productname=transfercft&amp;productversion=3.8&amp;filename=transfercft-swagger-api.json) is implemented using Swagger.



<span>Transfer CFT</span> provides a set of Swagger REST APIs that you can use to perform necessary <span>Transfer CFT</span> tasks. Each available API command provides a command description that includes viable parameters. The documentation provides an example for commands that require a body, as well as a description of possible error codes.



<span>Transfer CFT</span> <span>3.9</span> is based on Swagger 2.0 and delivered also for OAS 3.0. For more information on Swagger, refer to [swagger.io](http://swagger.io/).



## Resources



-   <span>API description</span>: Is a technical description, in JSON, that specifies the API verbs, URL, encoding, input and output parameters, errors, etc.: `https://<copilot_host>:<uconf:copilot.restapi.serverport>/cft/api/v1/api-docs/service.json`

-   <span>Example</span>

-   https://localhost:1768/cft/api/v1/api-docs/service.json

-   <span>API documentation</span>: You can access the <span>Transfer CFT</span> Swagger UI documentation at: <span>https://&lt;copilot\_host&gt;:&lt;uconf:copilot.restapi.serverport&gt;/cft/api/v1/ui/</span>

-   <span>Example</span>

-   https://localhost:1768/cft/api/v1/ui/

</uconf:copilot.restapi.serverport></copilot_host>