{
    "title": "Extract the Access Management Cache",
    "linkTitle": "Extract the Access Management Cache",
    "weight": "300"
}If you need to check the {{< TransferCFT/componentlongname  >}} rights for a specific user, you can use the `EXTAMCACHE `command to obtain this information.

Command syntax: EXTAMCACHE

## Parameters


| Parameter  | Description  |
| --- | --- |
| <a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fname">FNAME</a>  | Selects the Access Management cache file. By default, this is the CFTAM file, which is located in the <code>data </code>folder.  |
| <a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fout">FOUT</a>  | Selects the output file. By default, it is the console.  |
| <a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a>  |  Selects the user, or users, for which you want to obtain access rights. By default, the function returns all users.<br/>You can use the wildcard characters <code>*</code> and <code>?</code> to filter the user names.  |


Example

The following command extracts the cache file information for all users and their rights to a text file called `AMuser.txt`.

Or, to filter on user names containing "admin":

The following is an example output:

 
