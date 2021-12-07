{
    "title": "About access management exits",
    "linkTitle": "Exit type access management",
    "weight": "180"
}This section describes how to configure access management when not using .

{{< TransferCFT/componentshortname  >}} offers an access management exit in the form of a dynamic library. This library implements a set of mandatory functions described in the `$CFTINSTALLDIR/inc/exam.h` file.

Functions include:

-   int exam\_init(const char \*username)
-   char\* exam\_get\_version(void)
-   int exam\_check\_login(const char \*username, const char \*password)
-   int exam\_change\_password(const char \*username, const char \*old\_password, const char \*new\_password)
-   int exam\_check\_permissions(EXAMPermission \*\*perm\_list)
-   int exam\_check\_potential\_permissions(EXAMPermission \*\*perm\_list)

To help you get started, an Access Management exit sample is delivered in: `$CFTDIRRUNTIME/src/exit/cftexamsmp1.c`

For more information, see   [Delivered Access Management exit samples](am_samples).

Related topics

[UCONf parameters](../../admin_intro/uconf/uconf_parameters)
