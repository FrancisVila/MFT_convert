{
    "title": "Use the previous/next command ",
    "linkTitle": "Use previous/next command ",
    "weight": "190"
}You can use the **Up/Down Arrow** keys as a shortcut to recall the previous or next command.

<span id="Partial"></span>

## Partial word recognition

To retrieve a command you know, begin by typing the first characters of the command. CFTUTIL returns only the commands starting with those characters. For example type LI and press **Tab**, the commands LISTCAT, LISTLOG, LISTCOM display. You can then use the **Up/Down Arrow** keys to scroll the list.

<span id="Command-"></span>

### Command-history settings

Use the following uconf parameters to manage the command-history settings.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Default value</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.readline.history_size</p>         </td>
         <td><p>500</p>         </td>
         <td><p>Maximum number of commands that you can store.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.readline.enable</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Save and retrieve the commands from disk.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.readline.history_fname</p>         </td>
         <td><ul>
<li>Win: %APPDATA%\cft\CftutilHistory.txt</li>
<li>Unix: $(HOME)/.cft_history</li>
</ul>         </td>
         <td><p>Name of the file containing the command history.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Modify"></span>

### Modify the command list

The file containing the list of commands is a text file that you can edit or remove, and its location is defined in the <span class="code">cft.readline.history\_fname</span> parameter.
