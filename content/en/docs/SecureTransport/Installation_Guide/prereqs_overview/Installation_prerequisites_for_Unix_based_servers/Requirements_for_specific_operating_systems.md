{
    "title": "Requirements for specific operating systems",
    "linkTitle": "Requirements for specific operating systems",
    "weight": "120"
}Review the information for your operating system before starting the installer.

## <span id="AIX"></span>AIX requirements

Complete the following tasks before installing SecureTransport on IBM AIX.

### Increase file size limit

There is a default 1 GB limit on the size of files on AIX. The 1GB file size limit must be removed by editing the `/etc/security/limits` file. Change the default to:

`fsize = -1`

You can also use AIX System Management Interface Tool (SMIT) to change the file size limit.

1.  Enter `smitty users`.
2.  From the menu, select `Change / Show Characteristics of a User`.  
    Ensure that `Soft FILE size` is set to unlimited (`-1`).

By default, a JFS filesystem created on AIX has a limit of 2 GB. For best results, create a JFS filesystem with large file support.

### Check and set ARG\_MAX

Before installing SecureTransport, ensure the `ARG_MAX` setting is correct. It must be at least 9. For best results, use 256 or higher, up to 1024.

1.  Check the ARG\_MAX setting by typing the following:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>getconf ARG_MAX         </td>      </tr>   </tbody></table>

2.  If the value is less than 1048576, run the following command as the root user:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>chdev -l sys0 -a ncargs=256         </td>      </tr>   </tbody></table>

### Change maximum bundle size

For Enterprise Clustering, use the following commands to change the maximum bundle size:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>/usr/sbin/no -p -o udp_recvspace=4194304<br/>/usr/sbin/no -p -o udp_sendspace=65536         </td>
      </tr>
   </tbody>
</table>

### Allow larger socket buffers

For Enterprise Clustering, SecureTransport Server requires larger socket buffers than the default. Use the following commands to allow larger socket buffers:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>/usr/sbin/no -p -o rfc1323=1<br>/usr/sbin/no -p -o sb_max=4194304</br></code>
<br/>
</p>
         </td>
      </tr>
   </tbody>
</table>

### Check and set locale

Use the following command to check the locale:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>locale         </td>
      </tr>
   </tbody>
</table>

If the output does not include `LC_CTYPE=en_US.UTF-8`, change the locale to `EN_US.UTF-8` using the Manage Language Environment menu in SMIT. Be sure that EN\_US.UTF-8 locale is installed on your system

## <span id="Oracle,"></span>Oracle Linux / RHEL / CentOS requirements

The following tasks must be completed before installing SecureTransport on Oracle Linux, Red Hat Enterprise Linux or CentOS.

### Install dependencies

To install SecureTransport on Oracle, RHEL, or CentOS systems, you need to install the following packages:

-   32-bit `glibc.i686` library package (provides `ld-linux.so.2`)
-   32-bit `zlib` library package
-   64-bit `libaio` library package

In addition, the installation of SecureTransport with an embedded MariaDB or MySQL database requires the following dependencies:

-   64-bit Perl interpreter required for RHEL 7/8, Oracle Linux 7/8, CentOS 7/8
-   Perl `Data::Dumper` module required for RHEL 7/8, Oracle Linux 7/8, CentOS 7/8
-   Perl `Getopt::Long` module required for RHEL 8, Oracle Linux 8, CentOS 8
-   `ncurses-compat-libs` library required for RHEL 8, Oracle Linux 8, CentOS 8

### Allow larger socket buffers

For Enterprise Clustering, SecureTransport Server requires larger socket buffers than the default. Add the following lines to the `/etc/sysctl.conf` file to allow larger socket buffers:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Pеrl modules can be removed after a successful installation.          </td>
      </tr>
</table>

Then run the following command to apply the settings immediately:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><code>net.core.rmem_max=2096304<br/>net.core.wmem_max=2096304<br/>net.ipv4.tcp_moderate_rcvbuf=1</code>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Increase"></span>Increase the maximum number of file descriptors

SecureTransport requires more than the default number of file descriptors. Add the following line to the `/etc/sysctl.conf` file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><code>sysctl -p</code>
         </td>
      </tr>
   </tbody>
</table>

Then run the following command to apply the settings immediately:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>fs.file-max = 65536         </td>
      </tr>
   </tbody>
</table>

## <span id="SLES req"></span>SLES requirements

The following tasks must be completed before installing SecureTransport on SUSE Linux Enterprise Server:

-   Perform a Minimal System SLES installation. Do not install the X Window System.
-   Install the following packages:
    -   unzip (to unpack the installation package)
    -   numactl
    -   which
    -   glibc-32bit
    -   libz1-32bit
-   Install the Server Base System pattern.
-   If AppArmor is installed, disable it as follows:
    1.  Start YaST.
    2.  Select **System > System Services(Runlevel)**.
    3.  Select **Expert Mode**.
    4.  Select `boot.apparmor` and click **Set/Reset > Disable the service**.
    5.  Click **Finish** to exit the YaST Runlevel tool.
-   [Increase the maximum number of file descriptors](#increase)
