{
    "title": " Install Transfer CFT ",
    "linkTitle": "Install Transfer CFT",
    "weight": "160"
}This section describes the steps to perform a Transfer CFT HP NonStop installation, as well as the automatic steps that occur when you run the installation procedure.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To accommodate changing product versions, the convention &lt;version&gt; may be used in place of the actual product version in examples and lists. You should replace &lt;placeholders&gt;, or example values used for demonstrative purposes, with your actual values and target platform details.         </td>
      </tr>
   </tbody>
</table>

## Upload the Transfer CFT archive

Upload the Transfer CFT package corresponding to the target platform to your machine. Perform this upload transfer in BINARY mode to ensure package integrity.

**Example**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Transfer_CFT_3.8_Install_hp_nonstop_oss-ia64-32_BN8580000.zip</p>         </td>
      </tr>
   </tbody>
</table>

Decompress the archive using the unzip command.

**Example**

Depending on your installation, the screen message may differ slightly from the following example.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>/home/cftuser: unzip Transfer_CFT_3.8_Install_hp_nonstop_oss-ia64-32_BN8</p>
            <p>580000.zip</p>
            <p>Archive:  Transfer_CFT_3.8_Install_hp_nonstop_oss-ia64-33_BN8580000.zip</p>
            <p>   creating: Transfer_CFT_OtherUnixes_V3.8/</p>
            <p>  inflating: Transfer_CFT_OtherUnixes_V3.8/TransferCFT_3.8_hp_nonstop_oss-ia</p>
            <p>64-32.run</p>
            <p>inflating: EULA.txt</p>
            <p>inflating: EULA.html</p>         </td>
      </tr>
   </tbody>
</table>

In the example, Transfer CFT package is unzipped in the Transfer\_CFT\_OtherUnixes\_V3.8 directory.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Be certain to read the end-user license agreement.         </td>
      </tr>
   </tbody>
</table>

## Add execution rights

Add execution rights to the Transfer\_CFT\_&lt;version>\_&lt;os>-&lt;arch>-&lt;xx>.run package.

Enter:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>chmod u+x Transfer_CFT_&lt;version&gt;_&lt;os&gt;-&lt;arch&gt;-&lt;xx&gt;.run</p>         </td>
      </tr>
   </tbody>
</table>

## Start the installation

Execute the install command to start the Transfer CFT installation procedure, replacing &lt;installation\_directory> with the directory where you want to install Transfer CFT.

For a new installation, this directory should be empty or nonexistent. However, the installation directory can point to an existing installation in order to upgrade it. For more information on performing an upgrade, refer to [Migrate or upgrade Transfer CFT](#).

You can use the following additional parameters:

-   --cryptokey\_password &lt;password>: the cftcrypt requires a password to generate an encryption key. You can either provide one using this parameter, or interactively enter it during the installation. Either way, the password is checked against the cftcrypt password acceptance criteria, and the installation cannot complete unless a valid password is provided.
-   `<guardian_installation_directory_prefix>` installs the Guardian specific files in its file system space. This parameter is *optional*. It is required only if you want to integrate Transfer CFT with Guardian procedures.
-   --post\_install\_script &lt;fullpathtopinstscript> runs a shell script during the installation procedure after the product has been initialized.

Enter:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>./Transfer_CFT_&lt;version&gt;_&lt;os&gt; &lt;xx&gt;.run install &lt;installation_directory&gt; [&lt;guardian_installation_directory_prefix&gt;] [--post_install_script &lt;fullpathtopinstscript&gt;] [--cryptokey_password &lt;password&gt;]         </td>
      </tr>
   </tbody>
</table>

**Examples**

The following command installs Transfer CFT on the OSS directory /home/cftuser/CFT38. Additionally, the Guardian components are installed using /G/data14/cft38b (which is an equivalent of `$DATA14.CFT38B`) as a prefix.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>/home/cftuser/Transfer_CFT_OtherUnixes_V3.8: ./ TransferCFT_3.8_hp_nonstop_oss-ia 64-32.run install /home/cftuser/CFT38 /G/data14/cft38b         </td>
      </tr>
   </tbody>
</table>

The following command installs Transfer CFT on the OSS directory` /home/cftuser/CFT38`. Additionally, a post installation script `cft_postinst.sh` is run at the end of the installation process.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>/home/cftuser/Transfer_CFT_OtherUnixes_V3.8: ./ TransferCFT_3.8_hp_nonstop_oss-ia 64-33.run install /home/cftuser/CFT38 --post_install_script ./cft_postinst.sh         </td>
      </tr>
   </tbody>
</table>

The following command does the same as above, but additionally sets a password that is used to generate an encryption key so that you do not need to enter it interactively.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>/home/cftuser/Transfer_CFT_OtherUnixes_V3.8: ./ TransferCFT_3.8_hp_nonstop_oss-x86-32.run install /home/cftuser/CFT38 --post_install_script ./cft_postinst.sh --cryptokey_password mypAsswOrd76*         </td>
      </tr>
   </tbody>
</table>

### Installation procedure results

The Transfer CFT installation procedure automatically performs the following:

-   Extracts the Transfer CFT package.
-   Creates a Transfer CFT runtime.
-   Initializes the sample configuration.
-   Creates the Transfer CFT database.
-   Creates a default user for Transfer CFT Copilot:
    -   Login: **guest**
    -   Password: **guest**

### <span id="Guardian"></span>Guardian files

If you opted to install the Guardian files, several files are created in the Guardian system space. The files' volume and subvolumes depend on the installation prefix that you provided.

For example, /G/data14/cft38b creates files where the volume name is $DATA14, the subvolume names begin with cft38b, and that ends with the values described in the following table.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Subvolume</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>&lt;subvolume&gt;IE         </td>
         <td>            <p>Contains the Transfer CFT samples.</p>
            <p>Some of these samples are copied in the user configuration volume &lt;subvolume&gt;UP, where they can be modified.</p>         </td>
      </tr>
      <tr class="even">
         <td>&lt;subvolume&gt;IF         </td>
         <td>            <p>Contains the EMS dictionary and DDL template files.</p>
            <p>CFTPLATE contains the Transfer CFT templates to be concatenated with the system template for an EMS collector. See the XCFTDDL section in <a href="#">Event messages</a>, which describes the DDL template.</p>         </td>
      </tr>
      <tr class="odd">
         <td>&lt;subvolume&gt;IX         </td>
         <td>            <p>Transfer CFT executables and procedures.</p>         </td>
      </tr>
      <tr class="even">
         <td>&lt;subvolume&gt;IP         </td>
         <td>Program samples.         </td>
      </tr>
      <tr class="odd">
         <td>&lt;subvolume&gt;IH         </td>
         <td>Headers.         </td>
      </tr>
      <tr class="even">
         <td><span id="subvolumeUD"></span>&lt;subvolume&gt;UD         </td>
         <td>            <p>Default Transfer CFT subvolume.</p>
            <p>This is used when Transfer CFT needs to create a Guardian file.</p>         </td>
      </tr>
      <tr class="odd">
         <td>&lt;subvolume&gt;UP         </td>
         <td>Contains the procedures copied from the installation samples.         </td>
      </tr>
   </tbody>
</table>

## Enter the Transfer CFT license key

After the installation completes, enter the Transfer CFT license key in the &lt;installation\_directory>/runtime/conf/cft.key file.

## <span id="Install"></span>Install the Guardian specific files

If you ran the installation procedure without providing the parameter &lt;guardian\_installation\_directory\_prefix>, the Guardian specific files were not installed. However, you can install these files later by calling the Guardian installation script.

1.  Load the Transfer CFT profile:

2.  Install the Guardian files:

3.  <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>cftginst.sh --help         </td>
          </tr>
       </tbody>
    </table>

4.  Since installing the Guardian files modifies the Transfer CFT profile, you must reload the profile:
