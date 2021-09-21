{
    "title": "Transfer serialization",
    "linkTitle": "Transfer serialization",
    "weight": "250"
}## Requester mode

If the number of outgoing connections ([CNXOUT](../../../c_intro_userinterfaces/command_summary/parameter_intro/cnxout))
is 1 for a partner, then all transfers with the same level of priority
are activated in order of their submitted request.

This function is referred to as transfer serialization. However, a failed
transfer that has an H or K state does not block activation of
subsequent requests for this same partner.