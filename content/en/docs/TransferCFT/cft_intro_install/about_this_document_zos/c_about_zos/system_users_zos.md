{
    "title": "About system users",
    "linkTitle": "About system users",
    "weight": "190"
}An APF, authorized program facility, is a security element that allows an installation to identify system or user programs. When a Transfer CFT system does not use an APF, the Transfer CFT USERCTRL parameter has no effect on file permissions and all file actions are done by the account that started Transfer CFT. This means that to enable user control for file permissions, your Transfer CFT requires APF.

### Non-APF installations

In non-APF installations, Transfer CFT is started by the user USERMON and the USERCTRL does not affect file rights or actions.

### APF installations with USERCTRL

#### Receiver side

While Transfer CFT is still started by the user USERMON, in an APF installation the USERCTRL setting has a direct effect on the transfer procedure.

1.  USERCTRL=NO USERID=TEST
    -   A receive is performed by the user USERMON
    -   TEST submits the end-of-transfer procedure
2.  USERCTRL=NO USERID=
    -   A receive is performed by the user USERMON
    -   USERMON submits the end-of-transfer procedure
3.  USERCTRL=NO USERID=NON RACF USERID (not in RACF database)
    -   A receive is performed by the user USERMON
    -   USERMON submits the end-of-transfer procedure
4.  USERCTRL=YES USERID=TEST
    -   A receive is performed by the user TEST
    -   TEST submits the end-of-transfer procedure
5.  USERCTRL=YES USERID=
    -   A receive is performed by the user USERMON
    -   USERMON submits the end-of-transfer procedure
6.  USERCTRL=YES USERID=NON RACF USERID (not in RACF database)
    -   Receive is not performed
    -   End-of transfer procedure not submitted

## Release a resource for receive transfers

You do not usually need to switch users to perform a resource release. To activate a switch during FREE, set the ..UPARM(CNFENV) FREE\_AS\_USER variable to 1.

#### Sender side

1.  USERCTRL=NO USERID=TEST
    -   A send is performed by the user USERMON
    -   TEST submits the end-of-transfer procedure
2.  USERCTRL=YES USERID=TEST
    -   A send is performed by the user TEST
    -   The transfer procedure is submitted by TEST

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Setting the UCONF cft.server.exec_as_user variable to ‘NO’ also directly effects the transfer procedure.</td>
</tr>
</tbody>
</table>
