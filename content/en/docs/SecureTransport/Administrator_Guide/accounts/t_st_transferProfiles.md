{
    "title": "Transfer profiles",
    "linkTitle": "Transfer profiles",
    "weight": "180"
}*Transfer profiles* provide additional information for PeSIT transfers. A subscription that retrieves files from a PeSIT transfer site or sends files directly to a PeSIT transfer site can specify a transfer profile for that site to use when receiving or sending the files. If no transfer profile is specified, there must be a default transfer profile and it is used.

Because transfer profiles are used only with PeSIT transfers, the *Transfer Profiles* page is not available until a PeSIT
transfer site exists.

## Create a transfer profile

Use the following procedure to create a transfer profile.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.

2.  Click the name of the account to which to add a transfer profile.  
    The *Account Settings* page for that account is displayed.

3.  Click the **Transfer Profiles** tab.  
    The *Transfer Profiles* page is displayed.

4.  Click **Add New.**  
    The *Add Transfer Profile* page is displayed.

5.  Enter the field values described in the following table.  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Transfer Profile Name         </td>
         <td>
            <p>The name you use to select the transfer profile in the subscription.</p>
            <p>If this name must matches the name of the IDF (PeSIT protocol PI 12) on a remote PeSIT partner for an transfer from the remote partner, this transfer profile is used.</p>
         </td>
      </tr>
      <tr>
         <td>Files To Send         </td>
         <td>
            <p>Used to select the files to send when a partner site downloads.</p>
            <p>Relative to the user’s home folder, so <code>/file</code> refers to a file in the home folder</p>
            <p>Any valid expression including PeSIT expressions</p>
            <p>For details, see <a href="../../c_st_expressionlanguage">Expression Language</a>.</p>
         </td>
      </tr>
      <tr>
         <td>Acknowledge Transfer         </td>
         <td>If this option is selected, a successful transfer is acknowledged  by the receiving partner after the transfer finished and the transfer processing has been completed.         </td>
      </tr>
      <tr>
         <td>Receive Files As         </td>
         <td>
            <p>Used to name the files received when files are transferred to <span>SecureTransport</span>.</p>
            <p>Relative to the user’s home folder, so <code>/file</code> refers to a file in the home folder</p>
            <p>Any valid expression including PeSIT expressions.</p>
            <p>For details, see <a href="../../c_st_expressionlanguage">Expression Language</a>.</p>
         </td>
      </tr>
      <tr>
         <td>File Label         </td>
         <td>Controls whether the file name relative to the user’s home folder is sent, the full file path and name is sent, or no file name is sent. Ignored when receiving files.         </td>
      </tr>
      <tr>
         <td>All files         </td>
         <td>If this option is selected, when <span>SecureTransport</span> initiates a download from the PeSIT partner, it gets all files whose names match the pattern. If this option is cleared, <span>SecureTransport</span> gets the first file with a matching file name.         </td>
      </tr>
      <tr>
         <td>Transfer Mode         </td>
         <td><code>BINARY</code>, <code>ASCII</code>, <code>EBCDIC</code>, or <code>EBCDIC_NATIVE</code>. Use <code>EBCDIC_NATIVE</code> for files that use EBCDIC LF (0x25) as the end-of-line character.         </td>
      </tr>
      <tr>
         <td>Record Format         </td>
         <td>Fixed or Variable.         </td>
      </tr>
      <tr>
         <td>
            <p>Record Length</p>
         </td>
         <td>
            <p>Specifies the length of the records in bytes.</p>
            <p>Record Format and Record Length are only taken into account if the received or sent files do not have transfer metadata defined (PI31 and PI32).</p>
         </td>
      </tr>
      <tr>
         <td>Strip padding symbols         </td>
         <td>
            <p>When <strong>Strip padding symbols</strong> is selected, the padding characters will be removed. This is the default behavior. When <strong>Strip padding symbols</strong> is not selected, the padding characters will not be removed.</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>Additional attributes         </td>
         <td>
            <p>This group of options provides controls for you to add or remove custom attributes as <i>attribute:value</i> pairs with your transfer profile. See <a href="../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables">Additional attributes</a>.</p>
<h5>Add an attribute</h5>
            <ul>
               <li>Click <b>Add Attribute</b> to enable input in the <strong>Attribute</strong> and <strong>Value</strong> fields.                </li>
               <li>Enter the respective values and click the Save (<img src="SaveIcon.png"/>) icon.               </li>
            </ul>
            <p>Repeat the process to add more Additional attributes, if necessary.</p>
<h5>Delete an attribute</h5>
            <p>Simply select the corresponding check-box of one or more attributes to remove and then click <b>Delete</b>.</p>
         </td>
      </tr>
   </tbody>
</table>

6.  Click **Add**.  
    The new transfer profile is added to the list for the user.

## Edit a transfer profile

Use the following procedure to edit a transfer profile.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account that owns the transfer profile to edit.
3.  Click the **Transfer Profiles** tab.
4.  Click the name of the transfer profile to edit.
5.  Edit the desired settings for the transfer profile.
6.  Click **Save**.

## Delete a transfer profile

Use the following procedure to delete a transfer profile.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the under the account that owns the transfer profile you want to delete.
3.  Click the **Transfer Profiles** tab.
4.  Select the checkboxes next to the names of the transfer profiles to delete.
5.  Click **Delete**.
