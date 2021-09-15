{
    "title": "Install security updates",
    "linkTitle": "Install security updates",
    "weight": "130"
}To install security updates on SecureTransport 5.5 Virtual Appliance, run the following command:

    zypper up

The first time you install a security update, you will be prompted to accept the Axway GPG key:

New repository or package signing key received:

    Repository: appliance-platform-updates

    Key Name: Axway SecureTransport Appliance <BU.426.ST.Appliance@axway.com>

    Key Fingerprint: 2F4811E2 87CEED53 F951BF78 B006F0E8 9DBDD9E8

    Key Created: Thu 18 Apr 2019 11:46:05 AM EEST

    Key Expires:(does not expire)

    Subkey: 2C76DDE85142DCC3 2019-04-18 [expires: 2021-04-17]

    Rpm Name: gpg-pubkey-9dbdd9e8-5cb8394d

You must accept the key to receive the updates.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Your firewall should be configured to allow access to <br/><code>http://securetransport-appliance.axway.com/ap-55/</code> from your appliance.         </td>
      </tr>
</table>
