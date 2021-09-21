{
    "title": "Directory and file path formats",
    "linkTitle": "Directory and file path formats",
    "weight": "190"
}The ST Web Client users can usually choose any name for the folders they create. However, several folder names may cause conflicting issues and prevent the folder's content from being accessed through a direct link. For example, when there is a sub-folder called "api" in the user's root directory, the user is redirected to SecureTransport's API when trying to access that folder through a direct link or refresh its content.

To prevent such issues, you can specify a file path to open through query string parameters. This will change the destination URL from *https://example.com/api* to *https://example.com/?openFolder=/api*.

The URL format of the links to resources in ST Web Client is determined by the `clientRouter` parameter and, in particular, `forceQueryStringParameter`. The `clientRouter` value represents whether file path URL navigation is enabled. The value of `forceQueryStringParameter` determines whether URLs used to browse folders contain a query string.

The following code snippet shows the default ST Web Client configuration file. With this configuration, ST Web Client uses URL paths.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
"features": {
   "clientRouter": {
      "enabled": true
	}
   },
....
"clientRouter": {
   "folderPathUrl": {
      "forceQueryStringParameter": false
      }
   }
}							</pre>
         </td>
      </tr>
   </tbody>
</table>

To adjust the directory paths, edit the custom configuration file to add those two sections and change the parameters' values as needed.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>clientRouter</th>
         <th>forceQueryStringParameter</th>
         <th>behavior</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>true         </td>
         <td>false         </td>
         <td>
            <p>(Default) URL navigation is enabled, the client router redirects to an URL path.</p>
            <p>For example:</p>
            <p><i>/?openFolder=/path/to/folder</i>
</p>
            <p>redirects to </p>
            <p><i>/path/to/folder</i>
</p>
         </td>
      </tr>
      <tr>
         <td>true         </td>
         <td>true         </td>
         <td>
            <p>URL navigation is enabled, the client router  redirects URL paths to URL with query string.</p>
            <p>For example:</p>
            <p><i>/path/to/folder</i>
</p>
            <p>redirects to <br/><i>/?openFolder=/path/to/folder</i></p>
         </td>
      </tr>
      <tr>
         <td>false         </td>
         <td>N/A         </td>
         <td>URL navigation is disabled. The browser back and forward buttons will not work.         </td>
      </tr>
   </tbody>
</table>
