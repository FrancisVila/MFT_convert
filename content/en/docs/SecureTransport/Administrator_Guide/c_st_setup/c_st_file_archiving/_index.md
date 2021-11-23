{
    "title": "File archiving",
    "linkTitle": "File archiving",
    "weight": "270"
}The file archiving feature enables the archiving and retrieval of files at the global, business unit, and account levels.

The global File Archiving configuration page is found at **Setup &gt; File Archiving**. There you can enable the feature and configure the global archiving policy, the archiving folder, whether or not encryption is required including the encryption certificate, and how long to keep the archived files. To configure the file archiving global configuration, refer to [File archiving global configuration](t_st_file_archiving_conf).

The file archiving configuration for each business unit can be inherited from the global file archiving configuration or changed for the current business unit. To configure file archiving for a business unit, refer to [Manage business units]().

For individual accounts the file archiving policy can be inherited or overwritten. To configure the file archiving policy for an account, refer to [Manage Accounts](../../accounts). File archiving can also be configured for account templates. To configure the file archiving policy for an account template, refer to [Manage account templates](../../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates).

To configure the maintenance schedule for the archive folder, refer to [Archive Maintenance application](../../applications/applicationsarchivemaintenance).

> **Note:**
>
> The file archive folder and user home folders should reside on a separate storage devices. There is a negative performance impact when the archive folder is on the same storage device as user home folders due to writing data twice on the same storage device.

The archived files are stored using a structured archive format so that the following use cases are supported:

-   When global archive folder is moved along with its content, the archived files are usable in their new location.
-   When account is moved from one business unit to another business unit, the archived files are usable without any additional copying.
-   When business unit archive folder is moved along with its content, the archived files are usable in their new location.
-   When the business unit archive is moved from the global archive one to a dedicated archive, the archived files are usable without any additional copying.

The files in the structured archive folder are searchable by the following parameters:

-   transfer id
-   cycle id
-   start date
-   end date
-   account name
-   file name
-   folder (relative to the account home folder)

The decision whether or not to archive a file is based on the following parameters:

-   If an account is configured with archiving on, the file will be archived.
-   If an account is configured with archiving off, the file will not be archived.
-   If an account is configured with archiving inherited from a business unit and the business is configured with archiving on, the file will be archived.
-   If an account is configured with archiving inherited from a business unit and the business is configured with archiving off, the file will not be archived.
-   If an account is configured with archiving inherited from a business unit and the business unit is configured with archiving inherited from the global archiving configuration, the global configuration will determine whether of not a file is archived.
