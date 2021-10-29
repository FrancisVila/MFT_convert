{
    "title": "Troubleshoot error messages when loading the profile",
    "linkTitle": "Troubleshoot error when loading profile",
    "weight": "450"
}If error messages display when loading the profile, for example "CFTDIRDAT parameter not set", the error may be due to a new file in the $CFTDIRRUNTIME/profile.d directory. An example of this is cft-autocomplete.bash\_completion, which was introduced in Transfer CFT 3.3.0.

To fix this issue, you can run the following command :

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftruntime -p $CFTDIRINSTALL $CFTDIRRUNTIME         </td>
      </tr>
   </tbody>
</table>

This command saves the current profile and creates a new one. You can compare the previous profile file with the new one, and keep the file you require.
