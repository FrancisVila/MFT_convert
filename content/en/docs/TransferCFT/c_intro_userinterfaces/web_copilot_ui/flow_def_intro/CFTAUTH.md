{
    "title": "Authorized template lists - CFTAUTH ",
    "linkTitle": "Authorized template lists - CFTAUTH ",
    "weight": "230"
}# <span id="kanchor51"></span><span id="Creating_authorization_lists__command_line"></span>Authorized flow definitions - CFTAUTH

<span id="Listing_model_file_identifiers__IDF_"></span>This section describes
the CFTAUTH command and parameters you use to create lists of authorized or unauthorized file transfer identifiers.

Related
topics

Object concepts
[](../../../../concepts/cft_configuration_concepts_start_here/authorization_list_concepts)[Create
authorized/unauthorized identifiers list](../../../../concepts/cft_configuration_concepts_start_here/authorization_list_concepts)

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/id">ID</a></p></td>
<td><p>Authorization list identifier. If the identifier is prefixed by"<code>NOT</code>", the object indicates a list of forbidden file identifiers.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/fname">FNAME</a></p></td>
<td><p>The name of the file where authorized or unauthorized file identifiers (IDF) are listed.</p>
<p>Each element of the list in this file can be:</p>
<ul>
<li>An explicit file identifier, or</li>
<li>A mask (using wildcards '*?'), where all of the file identifiers corresponding to this mask are affected</li>
</ul>
<p>There is no limit to the number of identifiers in this list.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/idf">IDF</a></p></td>
<td><p>List of authorized or unauthorized IDFs.</p>
<p>The value associated with each of these IDFs may be:</p>
<ul>
<li>An explicit
file identifier, or</li>
<li>A mask (using wildcards '*?'), where all of the file identifiers corresponding to this mask are affected by the
command</li>
</ul></td>
</tr>
</tbody>
</table>

<span id="CFTAUTH_example"></span>Example

In this example, the local Transfer CFT can only send files with identifiers of the APLI1, APLI2, LIST type and files with
identifiers beginning with the 3 letters CHQ to the partner
IBM1.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTPART    ID = IBM1,</p>
<p>SAUTH = SIBM1</p>
<p>CFTPART     ID = BULGC8,</p>
<p>RAUTH = RBULGC8</p>
<p>CFTAUTH     ID = SIBM1,</p>
<p>IDF = (APLI1,APLI2,LIST,CHQ*)</p>
<p>CFTAUTH      ID = RBULGC8,</p>
<p>IDF = fil21</p></td>
</tr>
</tbody>
</table>

Transfer CFT can only receive BULGC8 files with identifiers
of the idfdef, idf1, idf2, idf3 type from the partner.

Where the fil21 file contains:

-   idfdef
-   idf1
-   idf2
-   idf3

Please refer to [Create
authorized/unauthorized identifiers list](../../../../concepts/cft_configuration_concepts_start_here/authorization_list_concepts) for an example of how to define a list of unauthorized (excluded) IDFs.
