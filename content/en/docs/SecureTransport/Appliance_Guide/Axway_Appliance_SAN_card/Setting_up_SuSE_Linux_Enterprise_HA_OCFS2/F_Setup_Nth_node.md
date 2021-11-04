{
    "title": "Setup N-th node in a cluster using multicast",
    "linkTitle": "Setup N-th node in a cluster using multicast",
    "weight": "200"
}To setup the N-th node in a cluster using multicast:

> **Note:**
>
> Caution  
> Make sure you fulfill the following prerequisites.

1.  Run `sleha-join`.
2.  Enter the alias for the first node. Be sure this alias is present in `/root/.ssh/config`.
3.  Enter the root password for the first node when prompted.
4.  Run `mount | grep ocfs2` to check if OCFS2 mount is present.

 

 

 
