{
    "title": "SecureTransport REST APIs",
    "linkTitle": "SecureTransport REST APIs",
    "weight": "60"
}The current version of REST API for SecureTransport 5.5 is 2.0. It includes new resources and all existing resources (backward compatible), which are still available in the previous versions.

For useful Swagger documents links, refer to [Useful URIs](#useful).

## Administrative credentials

With administrator credentials, you can use the SecureTransport REST API to query, create, modify, and delete user accounts and related SecureTransport configuration information including applications, business units, certificates, sites, subscriptions, and transfer profiles. You can also use the REST API to perform the following actions:

-   Query and kill FTP and HTTP sessions.
-   Query and export logs.
-   Query, create, modify, and delete network zones to configure the SecureTransport Edge protocol.

For more information about network zones, refer to the *SecureTransport Administrator's Guide*.

## User credentials

With user credentials, you can use the SecureTransport REST API to perform the following actions:

-   Perform and manage server-initiated transfers using your transfer sites.
-   Upload files to your home folder.
-   List your home folder.
-   Change your password.
-   Trigger an email from SecureTransport Server with instructions for resetting you password.

## Base REST API URI

The base URI for the REST is `https://<host>:<port>/api/<version>/` where:

-   *`<host>`* is the hostname or the IP address of the SecureTransport server.
-   *`<port>`* is the one of the following:
    -   Administrator resources – Administration Tool port (default 444).
    -   User resources – HTTP or HTTPS port (default 80 or 443).
-   *`<version>`* is the SecureTransport REST API version (`vx.y` where `x` is the major version and `y` is the minor version, v2.0 for SecureTransport 5.5).

## <span id="Useful"></span>Useful URIs

The following are useful REST API URIs:

-   `https://<host>:<port>/api/` – lists all available versions
-   `https://<host>:<port>/api/v<1.3 or lower>/` – resource descriptions
-   `https://<host>:<port>/api/v<1.3 or lower>/docs/index.html` – API reference
-   `https://<host>:<port>/api/<1.4 or above>/` – GET request returns yaml or json Swagger specification:
    -   Returns Swagger yaml specification with no “Accept:” HTTP header or with “Accept: application/x-yaml” header.
    -   Returns Swagger json specification with “Accept: application/json” HTTP header.
-   `https://<host>:<port>/api/application.wadl` – WADL application description
-   `https://<host>:<port>/api/<1.4 or above>/docs/index.html` – Swagger-UI API reference

## HTTP methods

The versions of the SecureTransport API before 2.0 support the following HTTP methods: GET, PUT, POST, and DELETE. API 2.0 also supports the PATCH and HEAD methods. For more information about SecureTransport API 2.0, refer to its Swagger documentation. These methods and the provided resources allow access to a single element or a collection of elements.

## Internet media data types

The Internet media data types supported by the REST API versions prior to 2.0 are `application/json` and `application/xml`. API 2.0 does not support `application/xml` media data type.

The following information is valid only for API versions prior to 2.0. With API 2.0, in order to use REST API with Java, generate the Swagger client stubs from `swagger.yaml` file.

For Java use of the REST API, the SecureTransport Java API provides a library called `ws-representation`, which includes Java classes that represent the data that can be accessed using the REST API. The `ws-representation` library depends on the `jersey-core` and `jersey-server-linking` libraries version 1.13 which are available from http://jersey.java.net/. In addition to them, Java programs require the `jackson` libraries version 1.9.2 and `validation-api `version 1.0.0 GA from J2EE 6. Representations are annotated according to JSR 303. Validation is done on the server side.
