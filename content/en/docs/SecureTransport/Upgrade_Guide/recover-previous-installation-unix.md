{
    "title": "Recover your previous SecureTransport installation on Unix-like systems",
    "linkTitle": "Recover your previous SecureTransport installation on Unix-like systems",
    "weight": "80"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">After a successful upgrade to <span>SecureTransport</span> <span>5.5</span>, there is no revert / downgrade path: the only way to roll back to a previous <span>SecureTransport</span> version deployment is to restore it from backup.          </td>
      </tr>
</table>

If the upgrade fails, you can recover your backed-up SecureTransport 5.4 installation.

Complete the following steps to restore your SecureTransport installation from a backup on a UNIX or AIX system. If you use a non-root installation, execute all steps for restoring by using your non-root user.

1.  Stop all SecureTransport services.
2.  Verify that all services are stopped. You can check if a process is still running by verifying if the PID exists the `<FILEDRIVEHOME>/var/run` directory.
3.  On Linux, list all services in `systemd` by running `systemctl --all` and look for SecureTransport services. If present, stop and disable the SecureTransport services by using the following commands:  
    `systemctl stop <service name>.service`and `systemctl disable <service name>.service`.
4.  On Linux, verify there are no SecureTransport service files and symlinks to them in `/etc/systemd/system` and `/usr/lib/systemd/system`. If there are any, stop and disable the services and remove the symlinks.
5.  On Linux, reload and reset the unit files by running `systemctl daemon-reload` and `systemctl reset-failed`.
6.  On Linux, copy the backup `init` scripts to `/etc/rc.d` and its respective subdirectories, and ensure that the `rc.d/init.d/rc.stransportSecureTransport<xx>` script is executable.
7.  On AIX, copy the backup `init` script to the `/etc` directory, and verify that `rc.stransportSecureTransport<xx>` or `rc.stransport`, respectively, is executable.
8.  For root installation, replace the `/etc/synchronycomponents` file with the backup synchronycomponents file. For non-root, replace the `/<user's home>/.synchronycomponents` file with the backup synchronycomponents file.
9.  Copy the SecureTransport cron jobs from the backup cron file to `crontab` by using the `crontab -e`.
10. Remove the Axway installation directory and extract the Axway backup.
11. Remove the SecureTransport installation directory and extract the SecureTransport backup.
12. If you use an external database, restore it according to the database vendor's instructions.
13. Execute all the steps for restoring SecureTransport on all instances.
14. Reboot your machines.