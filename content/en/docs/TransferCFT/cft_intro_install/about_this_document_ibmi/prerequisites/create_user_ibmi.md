{
    "title": "Create users and set security rights",
    "linkTitle": "Create users and set security rights",
    "weight": "200"
}This section describes the user rights procedures that you must perform prior to installing Transfer CFT IBM i. Additionally, verify that your operating system and environment requirements are met as described in [Prerequisites](..//transfercft/cft_intro_install/about_this_document_ibmi/prerequisites).

Prior to installation, ensure the following:

-   The **CFTINST** user who performs the Transfer CFT installation and applies Service Packs must have the following special authorities: \*JOBCTL, \*SPLCTL and \*ALLOBJ.
-   The **CFT** user who manages and uses Transfer CFT must have the following special authorities: \*JOBCTL and \*SPLCTL.

Please note that these users must exist prior to the Transfer CFT installation. If it is not the case, you can proceed as follows:

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTUSRPRF USRPRF(CFTINST) PASSWORD(CFTINST) PWDEXP(*YES) USRCLS(*USER) INLPGM(*NONE) INLMNU(MAIN) LMTCPB(*NO) TEXT('*SHARED: MFT Axway Installer User Profile') SPCAUT(<span>*JOBCTL *SPLCTL *ALLOBJ</span>) PWDEXPITV(*SYSVAL)         </td>
      </tr>
   </tbody>
</table>

 

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CRTUSRPRF USRPRF(CFT) PASSWORD(CFT) PWDEXP(*YES) USRCLS(*USER) INLPGM(*NONE) INLMNU(MAIN) LMTCPB(*NO) TEXT('*SHARED: MFT Axway CFT Profile') SPCAUT(<b>*JOBCTL *SPLCTL</b>) PWDEXPITV(*SYSVAL)         </td>
      </tr>
   </tbody>
</table>
