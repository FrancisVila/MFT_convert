{
    "title": " Transfer CFT REST API concepts",
    "linkTitle": "REST API",
    "weight": "290"
}This section describes how to use REST API to automate access to Transfer CFT resources. Available resources include administration, configuring, transferring files, and viewing the log and catalog (create, modify, view and delete transfers).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The REST API server only accepts HTTPS connections.         </td>
      </tr>
   </tbody>
</table>

## Audience

You should have a working knowledge of Transfer CFT and an understanding of basic REST API concepts to implement Transfer CFT REST API.

## REST API documentation

The [Transfer CFT API documentation](http://apidocs.axway.com/swagger-ui/index.html?productname=transfercft&productversion=3.8&filename=transfercft-swagger-api.json) is implemented using Swagger.

Transfer CFT provides a set of Swagger REST APIs that you can use to perform necessary Transfer CFT tasks. Each available API command provides a command description that includes viable parameters. The documentation provides an example for commands that require a body, as well as a description of possible error codes.

Transfer CFT 3.9 is based on Swagger 2.0 and delivered also for OAS 3.0. For more information on Swagger, refer to [swagger.io](http://swagger.io/).

## Resources

-   API description: Is a technical description, in JSON, that specifies the API verbs, URL, encoding, input and output parameters, errors, etc.: `https://<copilot_host>:<uconf:copilot.restapi.serverport>/cft/api/v1/api-docs/service.json`  
    Example  
    https://localhost:1768/cft/api/v1/api-docs/service.json
-   API documentation: You can access the Transfer CFT Swagger UI documentation at: https://&lt;copilot\_host>:&lt;uconf:copilot.restapi.serverport>/cft/api/v1/ui/  
    Example  
    https://localhost:1768/cft/api/v1/ui/
