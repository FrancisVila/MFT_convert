{
    "title": "Check Point firewall",
    "linkTitle": "Check Point firewall",
    "weight": "280"
}To enable Check Point firewalls, in Check Point NG firewalls (AI R55 and higher), set the FTP connection to FTP\_BASIC. This allows bidirectional communications and sets the firewall to allow commands not terminated with a newline.

The Check Point firewall must allow bidirectional communication. It must not enforce new line termination.

As the Check Point documentation states, the FTP\_BASIC protocol type was introduced in the Check Point R55 NG AI. If you apply it to the FTP object, it enforces a reduced set of the FTP security checks done by the regular FTP protocol type. The following checks are not enforced by FTP\_BASIC:

-   That every packet is terminated with a newline character, so that the PORT command is not split across packets.
-   Bidirectional traffic on the data connection is not allowed, as it can be used improperly.

> **Note:**
>
> FTP\_BASIC also disables FTP BOUNCE protection and so can be viewed as potentially less secure. This, as well as a more secure method to disable the newline check (FTP PACKET check) are described in Check Point Secure Knowledge SK27122.

**Related topics:**

-   [Cisco PIX firewall](../r_st_cisco_pix_firewall)
-   [Raptor firewall](../r_st_raptor_firewall)
