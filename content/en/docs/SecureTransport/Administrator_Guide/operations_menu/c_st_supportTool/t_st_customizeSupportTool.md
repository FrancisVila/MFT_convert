{
    "title": "Add custom information to the support information file",
    "linkTitle": "Add custom information to the support information file",
    "weight": "180"
}The support tool is implemented as an executable script, `<FILEDRIVEHOME>/bin/collect_support_information`, that collects the information that is specified on the *Support Tool Configuration* page and saves it in the support information file.

To add custom information to the support information file, edit the `<FILEDRIVEHOME>/bin/custom_collect_support_information` script. The main script calls this script before it creates the support information file from the collected information.

By default, the custom script does nothing. Your custom script must write the information that you need to include in the support information files to the support directory that the main script writes to. The script can create files and directories in the support directory. The last action that the main script takes is to combine all the files in the support directory into the support information file.

When you write a custom script, you can use the following defined environment variables:

-   **`${HOST}`–The host name of the system**
-   **`${SUPPORT_DIR}`–The full path name of the directory where the custom script must write its information**

The following example `<FILEDRIVEHOME>/bin/custom_collect_support_information` script illustrates writing a file to the support directory.

    # Collect user files
    #
    USER_HOME="/home/users"
    USERS="partner2 partner7"

    echo "=== Saving user files ==="
    tar -cf "${SUPPORT_DIR}/users_${HOST}.tar" -C "${USER_HOME}" "${USERS}"

**Related topics:**

-   [Configure the support tool](../t_st_configuresupporttool)
-   [Run the support tool](../t_st_runsupporttool)
