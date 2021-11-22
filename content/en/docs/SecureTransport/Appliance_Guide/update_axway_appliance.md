{
    "title": "Install security updates",
    "linkTitle": "Install security updates",
    "weight": "130"
}To install security updates on {{< SecureTransport/componentshortname  >}} {{< SecureTransport/releasenumber  >}} Virtual Appliance, run the following command:


    zypper up

The first time you install a security update, you will be prompted to accept the {{< SecureTransport/companyname  >}} GPG key:

New repository or package signing key received:


    Repository: appliance-platform-updates
    Key Name: Axway SecureTransport Appliance <BU.426.ST.Appliance@axway.com>
    Key Fingerprint: 2F4811E2 87CEED53 F951BF78 B006F0E8 9DBDD9E8
    Key Created: Thu 18 Apr 2019 11:46:05 AM EEST
    Key Expires:(does not expire)
    Subkey: 2C76DDE85142DCC3 2019-04-18 [expires: 2021-04-17]
    Rpm Name: gpg-pubkey-9dbdd9e8-5cb8394d

You must accept the key to receive the updates.

> **Note:**
>
> Your firewall should be configured to allow access to http://securetransport-appliance.axway.com/ap-55/ from your appliance.
