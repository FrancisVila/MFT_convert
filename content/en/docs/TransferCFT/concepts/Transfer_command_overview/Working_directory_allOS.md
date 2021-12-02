{
    "title": "Working directory",
    "linkTitle": "Working directory",
    "weight": "290"
}This section describes how to specify a working directory to use other than the default (runtime) directory for file transfer flows.

Information is presented by platform:

-   Using a working directory in UNIX or Windows
    -   Conventions and recommendations
    -   Configuration examples

<!-- -->

-   Using a working directory in IBM i or z/OS
    -   Conventions and recommendations
    -   Configuration examples

When you define a working directory for a given transfer flow, all files related to this transfer flow - meaning sent, received, or temporary files - must be part of the working directory tree. Additionally, scripts that are related to the file transfer flow are executed within the defined working directory (as this is the current working directory).

To assign a working directory for the CFTRECV, CFTSEND, SEND, and RECV objects, you use the WORKINGDIR parameter.

The WORKINGDIR parameter value can be an absolute or a relative path. If it is set as a relative path, the working directory is relative to the runtime directory.  
The WORKINGDIR value can include the symbolic variable &HOME to allow different users to work with files placed in their home directories by a generic CFTRECV, CFTSEND, SEND, or RECV.

## Limitations

-   On the z/OS and IBM i platforms, the temporary files do not reside in the working directory, and script execution does not occur there as described above.
-   IBM I and z/OS can only use an absolute path as the WORKINGDIR parameter.

## Using a working directory in UNIX or Windows

### Conventions and recommendations

Note the following conventions and recommendations:

-   All working files - sent, received, and temporary files - must be part of the working directory tree. Transfer CFT does not access files that are outside of the defined working directory tree.

<!-- -->

-   The maximum size for a complete file name is 512 characters. This value includes the total length of the workingdir added to any relative values.

<!-- -->

-   The workingdir has no impact on either the &PATH or &FPATH symbolic variables. Transfer CFT uses only the FNAME contents to fill those variables.

<!-- -->

-   The processing script's path (PREEXEC, EXEC, EXECE, ACKEXEC) if relative, is relative to the default directory (the runtime directory).

<!-- -->

-   Processing scripts are executed inside the workingdir.

### Examples on UNIX or Windows

This section provides the following examples along with a brief description:

-   [Workingdir using a relative fname](#Workingd)
-   [Workingdir and directory tree control](#Workingd2)
-   [Workingdir using the &HOME symbolic variable (example 1)](#Workingd3)
-   [Workingdir using the &HOME symbolic variable (example 2)](#Workingd4)

<span id="Workingd"></span>

#### Workingdir using a relative fname

This example uses a relative fname to send a file that is not in the default directory (the Transfer CFT runtime directory). The example command sends the file /home/user01/a.txt, which on reception is /home/user02/b.txt.

Server:

Client:

User01:

The application that is running under the user01 system account sends the a.txt file to the remote partner PART1 using the transfer flow IDF1.

<span id="Workingd2"></span>

#### Workingdir and directory tree control

In this example, the application that is running under the user01 system account tries to send a file that is outside the working directory tree. The transfer goes into error.

Server:

Client:

User01:

The application that is running under the user01 system account tries to send the home/user01/priv/a.txt file to the remote partner PART1 using the transfer flow IDF2.

<span id="Workingd3"></span>

#### Workingdir using the &HOME symbolic variable (example 1)

In this example, the file to send is located in user01's home directory. The file is received in user02's home directory, and retains its original file name.

At the end of the transfer, the Transfer CFT server executes a reply.cmd script located in &lt;CFTDIRRUNTIME>/exec/reply.cmd. Here, the current working directory of the executed script is the user02's home directory.

Server:

Client:

User01:

The application that is running under the user01 system account sends the 'file\_to\_send' file to the remote partner PART1 using the transfer flow IDF3.

<span id="Workingd4"></span>

#### Workingdir using the &HOME symbolic variable (example 2)

This example is similar to the previous one, except for the location of the script on the server side.

The file to send is in user01's home directory. The file is received in user02's home directory. In this configuration, the received file retains the original file name. At the end of the transfer, the Transfer CFT server executes the reply.cmd script located in /home/user02/exec/reply.cmd. The current working directory of the executed script is the user02 home directory.

Server:

Client:

User01:

The application that is running under the user01 system account sends the ‘file\_to\_send’ file to the remote partner PART1 using the transfer flow IDF4.

## Using working directory in IBM i and z/OS

In IBM i and z/OS environments, the working directory feature lets you specify either the native file system or a UNIX file system directory to use for file transfer flows. When you define a working directory for a given transfer flow, the files related to this transfer flow, either sent or received files, are part of the working directory.

Three scenarios are possible on these platforms:

-   UNIX file system  
    -   If a WORKINGDIR Unix file system is defined, it should be either fully qualified (‘/home/user01’ for example) or include the symbolic variable &HOME (z/OS) or ?HOME (IBM i).  
    -   For example, if the working directory parameter equals &HOME or ?HOME, the working directory is the home directory for the user ID on z/OS or on IBM i.
-   Data set on z/OS  
    WORKINGDIR z/OS data set the syntax is as follows:  
    -   If the segment name ends with a period, for example ‘USER01.PROD.’, then the workingdir refers simply to the data set.  
    -   If the segment name does not end with a final period, for example ‘USER01.PROD.FILE’, then the workingdir refers to a partitioned data set.  
    -   We advise you to include the symbolic variable &USERID in the working directory. For example, if the working directory parameter is ‘&USERID.’, the working directory is the user ID followed by a period.
-   Database on IBM i  
    WORKINGDIR IBM i syntax is as follows:
    -   If there is a slash character (/) in the working directory, it refers to a member of a database file. For example WORKINGDIR= PROD/NEWFILE, FNAME=MEMBER creates PROD/NEWFILE(MEMBER).
    -   Otherwise, if there is no slash, it refers to a database file. For example WORKINGDIR= PROD, FNAME=FILE creates PROD/FILE.  

### Conventions and recommendations

Note the following Transfer CFT z/OS or IBM i conventions and recommendations:

-   Transfer CFT does not authorize sending or receiving Unix file system files that are outside of the designated working directory tree.
-   The maximum size for a complete Unix file name is 512 characters, 44 characters for a z/OS data set name, and 33 characters for a IBM i database file. This value includes the total length of the working directory added to any relative values.
-   The &PATH or &FPATH symbolic variables will contain the WORKINGDIR value.
-   You can only refer to processing scripts that are on native file systems.

## Examples on IBM i and z/OS

### HFS examples

-   [Workingdir using a HFS relative fname](#Workingd7)
-   [Workingdir and HFS directory tree control](#Workingd8)
-   [Workingdir using the HFS &HOME symbolic variable](#Workingd9)

<span id="Workingd7"></span>

#### Workingdir using a HFS relative fname

The example command sends the file `/home/user01/a.txt`, which on reception is `/home/user02/b.txt`.

Server:

Client:

User01:

The application sends the a.txt file to the remote partner PART1 using the transfer flow IDF1.

<span id="Workingd8"></span>

#### Workingdir and HFS directory tree control

In this example, the application tries to send a file that is outside the working directory tree. The transfer goes into error.

Client:

User01:

The application tries to send the /home/user01/priv/a.txt file to the remote partner PART1 using the transfer flow IDF2.

<span id="Workingd9"></span>

#### Workingdir using the &HOME symbolic variable

In this example, the file to send is located in user01's HFS home directory. The file is received in user02's HFS home directory, and retains its original file name.

Server:

Client:

User01:

The application that is running under the user01 system account sends the file 'a.txt' file to the remote partner PART1 using the transfer flow IDF3.

### Data set examples on z/OS

-   [Workingdir using a data set file name](#Workingd10)
-   [Workingdir using a data set file name and the &USERID symbolic variable](#Workingd11)
-   [Workingdir using a partitioned data set file name](#Workingd12)

<span id="Workingd10"></span>

#### Workingdir using a data set file name

The example command sends the file USER01.SND.FTEST, which on reception is USER01.RCV.FTEST.

Server:

Client:

User01:

The application sends the file to the remote partner PART1 using the transfer flow IDF4.

<span id="Workingd11"></span>

#### Workingdir using a data set file name and the &USERID symbolic variable

In this example, the user USER01 sends the file USER01.SND.FTEST, which on reception is USER02.RCV.FTEST.

Server:

Client:

User01:

The user USER01 sends the file to the remote partner PART1 using the transfer flow IDF5.

<span id="Workingd12"></span>

#### Workingdir using a partitioned data set file name

The example command sends the file USER01.SND.LIB(TEST), which on reception is USER01.RCV.LIB(TEST).

Server:

Client:

User01:

The application sends the file to the remote partner PART1 using the transfer flow IDF6.

### Database (\*MBR and \*FILE) examples on IBM i

-   [Workingdir using a \*MBR file name](#Workingd13)
-   [Workingdir using a \*FILE file name](#Workingd14)

<span id="Workingd13"></span>

#### Workingdir using a \*MBR file name

The example command sends the file CFTPROD/SND(FTEST), which on reception is CFTPROD2/RCV(FTEST).

Server:

Client:

User01:

The application sends the file to the remote partner PART1 using the transfer flow IDF7.

<span id="Workingd14"></span>

#### Workingdir using a \*FILE file name

The example command sends the file CFTPROD/UTIN(FTEST), which on reception is CFTPROD2/UTIN(FTEST).

Server:

Client:

User01:

The application sends the file to the remote partner PART1 using the transfer flow IDF8.
