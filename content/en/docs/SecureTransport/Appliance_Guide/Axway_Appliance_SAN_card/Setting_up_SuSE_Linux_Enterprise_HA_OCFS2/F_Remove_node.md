{
    "title": "Remove a node from a SLEHA cluster",
    "linkTitle": "Remove a node from a SLEHA cluster",
    "weight": "230"
}1.  Login as a root user to any cluster node, except the one that is being removed.
2.  Run one of the following commands:  
    `sleha-remove -c <hostname>`  
    or  
    `sleha-remove -c <IP address>`,  
    where `<hostname>` or `<IP address>` is the hostname or the IP address of the node to be removed.
