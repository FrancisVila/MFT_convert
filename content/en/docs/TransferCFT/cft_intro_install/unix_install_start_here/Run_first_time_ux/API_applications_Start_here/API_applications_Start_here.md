{
    "title": "About API applications",
    "linkTitle": "About API applications",
    "weight": "220"
}# <span id="Building_CFT_API_applications"></span>About API applications

This book describes one of two Transfer CFT programming interfaces,
the API applications. This interface enables Transfer CFT to work in conjunction
with external applications.

This book begins with this topic
which introduces the two application families that can be developed using
these two interfaces and the development kit contents for building APIs.

-   Applications communicating
    with Transfer CFT to submit and monitor transfers or query the catalog,
    for example. See [Using APIs.](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Prog/API/Using_APIs.htm)
-   Exits enabling
    user programs to take control during a send operation. See [Managing
    exits.](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Prog/Exits/Managing_exits.htm)

Transfer CFT only provides a programming interface in C. This programming
interface can only be used if the development kit is installed on your
system, C compiler and associated tools.

This book is comprised of the following topics which describe how to
create an API application.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Topic</th>
         <th>Details
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td width="29.021%">
            <p><a href="../creating_an_api_application">Creating an API 
 application</a>
</p>
         </td>
         <td width="70.979%">
            <p>Describes the procedure to create an API application in 
  <span>Transfer CFT</span> UNIX.</p>
         </td>
      </tr>
      <tr>
         <td width="29.021%">
            <p><a href="../creating_an_exit_file">Creating an exit file</a>
</p>
         </td>
         <td width="70.979%">
            <p>Describes how to create an exit file for  <span>Transfer CFT</span> UNIX.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" width="29.021%">
            <p><a href="../creating_a_directory_exit">Creating a directory 
 exit</a>
</p>
         </td>
         <td colspan="1" rowspan="1" width="70.979%">
            <p>Describes how to create a directory exit in  <span>Transfer CFT</span> 
 UNIX.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1" width="29.021%">
            <p>Creating an accounting 
 exit</p>
         </td>
         <td colspan="1" rowspan="1" width="70.979%">
            <p>Describes how to create an accounting exit in UNIX.</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Development_kit_contents"></span>Development kit contents

The development kit used to integrate the Transfer CFT APIs is divided
into several directories:

-   *&lt;installdir>/lib/*
    containing all required libraries, in C, including:
-   A *libcftapi.a*
    module: this library is required for any application using the Transfer
    CFT APIs
-   A *libcftexa.a*
    module: this library is required for any application using the Transfer
    CFT directory exits
-   A *libcftexf.a*
    module; this library is required for any application using the file EXITs
-   A *libcftexe.a*
    module; this library is required for any application using the end of
    transfer EXITs

To generate a user application based on the Transfer CFT APIs and use
the file exit function, you must link the following with the *libcftapi.a* and *libexe.a* libraries.

-   &lt;installdir>/runtime/src/capi/ containing
    a command entry and catalog query example
-   &lt;installdir>/runtime/src/exit/ containing
    simple examples of file exits, directory exits, and end
    of transfer exits
