{
    "title": "Requirements for specific operating systems",
    "linkTitle": "Requirements for specific operating systems",
    "weight": "120"
}Review the information for your operating system before starting the installer.

<span id="AIX"></span>

## AIX requirements

Complete the following tasks before installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on IBM AIX.

### Increase file size limit

There is a default 1 GB limit on the size of files on AIX. The 1GB file size limit must be removed by editing the `/etc/security/limits` file. Change the default to:

`fsize = -1`

You can also use AIX System Management Interface Tool (SMIT) to change the file size limit.

1.  Enter `smitty users`.
2.  From the menu, select `Change / Show Characteristics of a User`.  
    Ensure that `Soft FILE size` is set to unlimited (`-1`).

By default, a JFS filesystem created on AIX has a limit of 2 GB. For best results, create a JFS filesystem with large file support.

### Check and set ARG\_MAX

Before installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, ensure the `ARG_MAX` setting is correct. It must be at least 9. For best results, use 256 or higher, up to 1024.

1.  Check the <span class="prog_codeph">ARG\_MAX</span> setting by typing the following:

        getconf ARG_MAX

2.  If the value is less than 1048576, run the following command as the root user:

        chdev -l sys0 -a ncargs=256

### Change maximum bundle size

For Enterprise Clustering, use the following commands to change the maximum bundle size:


    /usr/sbin/no -p -o udp_recvspace=4194304
    /usr/sbin/no -p -o udp_sendspace=65536

### Allow larger socket buffers

For Enterprise Clustering, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server requires larger socket buffers than the default. Use the following commands to allow larger socket buffers:



    /usr/sbin/no -p -o rfc1323=1
    /usr/sbin/no -p -o sb_max=4194304

### Check and set locale

Use the following command to check the locale:


    locale

If the output does not include `LC_CTYPE=en_US.UTF-8`, change the locale to `EN_US.UTF-8` using the Manage Language Environment menu in SMIT. Be sure that EN\_US.UTF-8 locale is installed on your system

<span id="Oracle,"></span>

## Oracle Linux / RHEL / CentOS requirements

The following tasks must be completed before installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on Oracle Linux, Red Hat Enterprise Linux or CentOS.

### Install dependencies

To install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on Oracle, RHEL, or CentOS systems, you need to install the following packages:

-   32-bit `glibc.i686` library package (provides `ld-linux.so.2`)
-   32-bit `zlib` library package
-   64-bit `libaio` library package

In addition, the installation of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> with an embedded MariaDB or MySQL database requires the following dependencies:

-   64-bit Perl interpreter required for RHEL 7/8, Oracle Linux 7/8, and CentOS 7/8
-   Perl `Data::Dumper` module required for RHEL 7/8, Oracle Linux 7/8, and CentOS 7/8
-   Perl `Getopt::Long` module required for RHEL 8, Oracle Linux 8, and CentOS 8
-   `libncurses.so.5` library required for RHEL 8, Oracle Linux 8, and CentOS 8

### Allow larger socket buffers

For Enterprise Clustering, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server requires larger socket buffers than the default. Add the following lines to the `/etc/sysctl.conf` file to allow larger socket buffers:


    net.core.rmem_max=2096304
    net.core.wmem_max=2096304
    net.ipv4.tcp_moderate_rcvbuf=1

Then run the following command to apply the settings immediately:


    sysctl -p

<span id="Increase"></span>

### Increase the maximum number of file descriptors

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> requires more than the default number of file descriptors. Add the following line to the `/etc/sysctl.conf` file:


    fs.file-max = 65536

Then run the following command to apply the settings immediately:


    sysctl -p

<span id="SLES req"></span>

## SLES requirements

The following tasks must be completed before installing SecureTransport on SUSE Linux Enterprise Server:

-   Perform a Minimal System SLES installation. Do not install the X Window System.
-   Install the following packages:
    -   unzip <span style="font-family: Verdana;">(to unpack the installation package)</span>
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
-   <a href="#Increase" class="MCXref xref">Increase the maximum number of file descriptors</a>
