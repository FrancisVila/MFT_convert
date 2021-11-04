{
    "title": "Managing keys",
    "linkTitle": "Managing keys",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Importing a Key](#Importing_a_key)

[Displaying keys](#Displaying_keys)

[Renaming a Key](#Renaming_a_key)

[Deleting a Key](#Deleting_a_key)

[Enabling and disabling a Key](#Enabling_Disabling_a_key)

<span id="Importing_a_key"></span>

## Importing a Key

To import a Key using the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Key</span> sub-node, and then select <span style="font-weight: bold;">Import...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Key management</span> window:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Key Name</p>         </td>
         <td><p>Name of the key (must be unique).</p>
<p>Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Enable</p>         </td>
         <td><p>Status of the key.</p>
<p>Check box to enable.</p>         </td>
      </tr>
      <tr>
         <td><p>Group</p>         </td>
         <td><p>Key group</p>         </td>
      </tr>
      <tr>
         <td><p>Comment</p>         </td>
         <td><p>Comments about the key.</p>         </td>
      </tr>
      <tr>
         <td><p>File containing the key</p>         </td>
         <td><p>Name and path for the file containing the key.</p>
<p>You can use the Browse button to select the file.</p>         </td>
      </tr>
      <tr>
         <td><p>File format</p>         </td>
         <td><p>Key file encoding.</p>
<p>Possible values:</p>
<ul>
<li>DER</li>
<li>PEM</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Key Type</p>         </td>
         <td><p>Key type.</p>
<p>Possible values:</p>
<ul>
<li>PRIVATE</li>
<li>PUBLIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Algorithm</p>         </td>
         <td><p>Key file algorithm.</p>
<p>Possible values:</p>
<ul>
<li>RSA</li>
<li>DSS</li>
<li><p>ECDSA_NISTP256</p></li>
<li><p>ECDSA_NISTP384</p></li>
<li><p>ECDSA_NISTP521</p></li>
<li>ED25519</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

1.  Complete the fields and then click <span style="font-weight: bold;">OK</span> to confirm.  
    Gateway displays the imported key in the right-hand pane.

> **Note:**
>
> Restrictions apply in FIPS mode when importing a key in Gateway. For more details see Using FIPS

<span id="Displaying_keys"></span>

## Displaying keys

To display all keys in the database

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Click the <span style="font-weight: bold;">Key</span> sub-node.  
    Gateway displays all existing Keys in the display pane (right pane). The display comprises columns containing the following key information:
    -   Name
    -   State
    -   Group
    -   Date created
    -   Type
    -   Comment
    -   Fingerprint

> **Note:**
>
> In FIPS mode, the keys that do not meet the FIPS 140-2 standard are marked in Navigator GUI with a FIPS restricted label and icon.

<span id="Renaming_a_key"></span>

## Renaming a Key

To modify a Key name:

1.  Display Keys (as described above).
2.  Right-click to select the key to rename, and select <span style="font-weight: bold;">Rename</span> from the context menu.  
    Gateway highlights the name in the display pane.
3.  Type the new name over the existing name, and click outside of the name field to complete the process.

<span id="Deleting_a_key"></span>

## Deleting a Key

To remove a Key from the database:

1.  Display Keys (as described above).
2.  In the right pane, right-click to select the key to delete, and select <span style="font-weight: bold;">Delete</span> from the context menu.
3.  In the confirmation window, click <span style="font-weight: bold;">YES</span>.  
    Gateway removes the selected key from the database.

<span id="Enabling_Disabling_a_key"></span>

## Enabling and disabling a Key

To disable a key that exists in the database:

1.  Display Keys (as described above).
2.  In the right pane, right-click to select the key to modify, and select <span style="font-weight: bold;">Enable/Disable</span> from the context menu.  
    If the Key was:
    -   <span style="font-style: italic;">disabled</span>, Gateway changes the state to <span style="font-style: italic;">enabled</span>
    -   <span style="font-style: italic;">enabled</span>, Gateway changes the state to <span style="font-style: italic;">disabled</span>

      
    Gateway displays a tag in the <span style="font-weight: bold;">State</span> column for that key to indicate the status of the key:
    -   <span style="color: #ff0000;">Red</span> = disabled
    -   <span style="color: #008000;">Green</span> = enabled

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
