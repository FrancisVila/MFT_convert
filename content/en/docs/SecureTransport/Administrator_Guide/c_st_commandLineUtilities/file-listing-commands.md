{
    "title": "Command line directory or file listing",
    "linkTitle": "Command line directory or file listing",
    "weight": "270"
}This subsection discusses file listing specifics in SecureTransport and also supplies examples and usage details.

The `ls -l` command is the standard file/directory listing command that returns all files and directories contained in the directory where you run it. You can also specify a *subdirectory listing*, using `ls -l <directory_name> `or a *file listing*, using `ls -l <file_name>`.

The returned output contains all contained files and directories is in the following format:

\[Permissions\] \[ST\_nlink\] \[UID\] \[GID\] \[File\_Size\] \[Date\] \[File\_Name\]

The following table includes the descriptions and specifics of each output parameter:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Utility file</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><span>Permissions</span>
</p>
         </td>
         <td>The read-write-execute permissions for the current file.         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>
            <p><span>ST_nlink</span>
</p>
         </td>
         <td>
            <p>Represents the number of hard links to the file.</p>
            <p>Output of <code>ls -l &lt;file_name&gt;</code>, returns either as '<code>0</code>' or '<code>?</code>' for the <code>ST_nlink</code> value. This behavior applies to deployments on any supported OS.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>UID</p>
         </td>
         <td>The User ID. When listing (file and folder) performed over SFTP on Windows, this value is always presented as a 0.         </td>
      </tr>
      <tr>
         <td>
            <p>GID</p>
         </td>
         <td>The Group ID. When listing (file and folder) performed over SFTP on Windows, this value is always presented as a 0.         </td>
      </tr>
      <tr>
         <td>
            <p>File_Size</p>
         </td>
         <td>
            <p>The size of a file. </p>
            <p>Use the <code>Stfs.Encryption.ListDecryptedSize</code> server configuration option to specify which file size, the original (decrypted) or the encrypted file size, to be reported for encrypted files. The option is available in both SecureTransport Server and Edge, and should be set to the same value on both. The default value is <code>false</code>, meaning the encrypted file size is displayed. When the option is set to <code>true</code>, the original file size (taken from the STFS attribute) is reported. Due to the STFS attribute checks, performance degradation may occur.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Date</p>
         </td>
         <td>For a file, the returned value when that file was last modified; for a directory, it is the returned value for when that directory was created.          </td>
      </tr>
      <tr>
         <td>
            <p>File_Name</p>
         </td>
         <td>The name and extension of the respective file.         </td>
      </tr>
   </tbody>
</table>

A valid return line would look like this:

    rw-rr--r-- 1 100 1001 1024 Aug 19 08:46 samplelog.txt

 
