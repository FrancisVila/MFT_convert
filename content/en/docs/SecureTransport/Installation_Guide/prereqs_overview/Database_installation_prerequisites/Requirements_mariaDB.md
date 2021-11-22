{
    "title": "Requirements for  secure connection to MariaDB database",
    "linkTitle": "Requirements for a MariaDB secure connection",
    "weight": "140"
}{{< SecureTransport/componentshortname  >}} can generate the certificates required for a secure connection to the embedded MariaDB database. If you use an external mechanism to generate the certificates, follow the procedure described in the MariaDB Server Documentation.

The three certificates need to be:

-   On a path reachable by the SecureTransport installation
-   In PEM format
