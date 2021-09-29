{
    "title": "REST API return codes",
    "linkTitle": "REST API return codes",
    "weight": "350"
}# Return codes



The Rest server returns some data in HTTP format, including a status header, but the data may also contain a body. You can refer to the Swagger web interface for the exact reply syntax.



HTTP status codes include:



<table data-cellspacing="0">
<thead>
<tr>
<th>Code</th>
<th>Status</th>
<th>Meaning, when to use</th>
</tr>
</thead>
<tbody>
<tr>
<td>200</td>
<td>OK</td>
<td>Everything went fine. The resource you requested has been found.</td>
</tr>
<tr>
<td>201</td>
<td>Created</td>
<td>Use it for synchronous processing, that is, when creating a resource synchronously. This status code goes along with the Response Location HTTP header, indicating where the new resource is accessible.</td>
</tr>
<tr>
<td>202</td>
<td>Accepted</td>
<td>Use it for asynchronous processing, typically for long running tasks (image processing, file compression, etc.). It indicates that the server has accepted the request but the result is not available yet. Responses usually contain a ‘task’ id the client can request (on a different URL) to get the status of a given long-running task.</td>
</tr>
<tr>
<td>400</td>
<td>Bad request</td>
<td>Indicates that the request is malformed. This is usually used to enforce that the requester is providing adequate parameters to the operation. For instance, if the operation requires a numerical identifier and gets a text instead, the server should return this status code.</td>
</tr>
<tr>
<td>401</td>
<td>Unauthorized</td>
<td>The requester provided invalid credentials. May indicate that the user and or password are not correct, or that the rights for the user are not sufficient to modify a transfer.</td>
</tr>
<tr>
<td>404</td>
<td>Not found</td>
<td>The resource was not found. The URL may not be correct.</td>
</tr>
</tbody>
</table>
