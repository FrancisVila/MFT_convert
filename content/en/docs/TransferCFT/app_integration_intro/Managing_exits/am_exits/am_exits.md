{
    "title": "About Access Management exits",
    "linkTitle": "About Access Management exits",
    "weight": "370"
}# About access management exits



This section describes how to configure access management when not using <span>Central Governance</span>.



<span>Transfer CFT</span> offers an access management exit in the form of a dynamic library. This library implements a set of mandatory functions described in the <span>$CFTINSTALLDIR/inc/exam.h</span> file.



Functions include:



-   int exam\_init(const char \*username)

-   char\* exam\_get\_version(void)

-   int exam\_check\_login(const char \*username, const char \*password)

-   int exam\_change\_password(const char \*username, const char \*old\_password, const char \*new\_password)

-   int exam\_check\_permissions(EXAMPermission \*\*perm\_list)

-   int exam\_check\_potential\_permissions(EXAMPermission \*\*perm\_list)



To help you get started, an Access Management exit sample is delivered in: <span>$CFTDIRRUNTIME/src/exit/cftexamsmp1.c</span>



For more information, see [Delivered Access Management exit samples](../Prog/Exits/a_m_exits/am_samples.htm).



Related topics



[UCONf parameters](../uconf/uconf_parameters.htm)

