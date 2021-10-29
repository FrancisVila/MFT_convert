{
    "title": "Swagger UI usage",
    "linkTitle": "Swagger UI usage",
    "weight": "330"
}The Swagger UI is both documentation and a client for the REST API. Each supported API command provides a detailed description, including possible parameters.

Swagger builds the HTTP frames and sends them to the REST server. However, before sending a command you must provide credentials.

#### Authorization

Basic authorization

Enter your Transfer CFT login name and password in the **Username/Password** fields. Click **Authorize**.

Bearer authorization

Copy your token from the Transfer CFT UI My Access Tokens page into the Value field and click Authorize. Click **Authorize**.

![](/Images/TransferCFT/authorization_swagger.png)

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See Generate an access token.         </td>
      </tr>
   </tbody>
</table>

#### Try it out option

The Try it out option allows you to execute API requests from within the Swagger UI.
