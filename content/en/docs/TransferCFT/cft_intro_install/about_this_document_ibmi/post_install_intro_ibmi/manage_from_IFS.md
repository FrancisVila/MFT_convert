{
    "title": "Manage Transfer CFT\u00a0using IFS",
    "linkTitle": "Manage Transfer CFT\u00a0using IFS",
    "weight": "200"
}This section explains how you can use Transfer CFT on the IFS environment. To do this you must run the following commands:

1.  Log on the iSeries using the Transfer CFT account.

2.  Execute the QSH command.

3.  Change the directory:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>cd  /home/cft/TransfertCFT/runtime         </td>      </tr>   </tbody></table>

4.  Load the profile:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>. ./profile         </td>      </tr>   </tbody></table>

5.  You can then use standard Transfer CFT programs, such as:

-   CFTSTART: Start Transfer CFT
-   CFTSTOP: Stop Transfer CFT
-   COPSTART: Start UI Server
-   COPSTOP: Stop UI Server
-   CFTUTIL
-   PKIUTIL
-   Etc.
