{
    "title": "Manage configuration commands",
    "linkTitle": "Manage configuration commands",
    "weight": "240"
}The topics in this section describe how to use command line operations to administer Transfer CFT configuration options, and is comprised of the following:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Command</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="../cftaccnt_concepts">CFTACCNT</a>
         </td>
         <td>Recording mode for statistical data         </td>
      </tr>
      <tr>
         <td><a href="../catalog_parameter_concepts">CFTCAT</a>
         </td>
         <td>Catalog attributes         </td>
      </tr>
      <tr>
         <td><a href="../communication_media_concepts">CFTCOM</a>
         </td>
         <td>Communication media         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftlog">CFTLOG</a>
         </td>
         <td>Transfer log files         </td>
      </tr>
      <tr>
         <td><a href="../network_resource_concepts">CFTNET</a>
         </td>
         <td> Network resources         </td>
      </tr>
      <tr>
         <td><a href="../cftparm_general_parameters">CFTPARM</a>
         </td>
         <td>General parameters definition         </td>
      </tr>
      <tr>
         <td><a href="../transfer_protocol_concepts">CFTPROT</a>
         </td>
         <td>Transfer protocol         </td>
      </tr>
   </tbody>
</table>

## What is a service file medium

Transfer CFT medium refers to any data support or local communication
means used by Transfer CFT. A distinction is made between the media:

-   Accessed by the
    Transfer CFT
-   Accessed by the
    Transfer CFT utility
-   Used by the interactive
    functions
-   Used by the programming
    interface

### Definitions

The following terms are used in this section:

-   PHYSICAL FILE which
    describes the name and physical location of a file type medium
-   If the file name
    begins with a reserved character, designated by char-file - see the Transfer CFT*Operations Guide* corresponding to your OS,
    this is a logical name interpreted by Transfer CFT
-   CFTIN and CFTOUT
    for standard task input/output
-   TCP synchronous
    medium to designate a communication channel

The Transfer CFT medium names can be set up for the:

-   Programming interface
    (catalog name, communication medium name with the Transfer CFT):
    by the OPEN and COM services
-   Transfer CFT:
    CFTPARM, CFTCOM, CFTCAT, CFTLOG, CFTACCNT objects (the name of the Parameter
    file cannot be changed)
-   Transfer CFT utility:
    CONFIG command
-   Interactive functions:
    the customization function is used to set the names of the Parameter,
    Partner, Catalog and Log files, and the Transfer CFT communication medium

### <span id="CFT_monitor_media"></span>Transfer CFT media files

You cannot change the name of the parameter
file. It constitutes the Transfer CFT anchor point containing all the data
defined by the parameter setting, and in particular the names of the other
files and media. However, you can establish a correspondence between this
logical name and a physical name in the flow of CFT activation commands.

The names of the other Transfer CFT media are defined by parameter setting,
although Transfer CFT has default values.

Transfer CFT
media by type of object and parameter

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Object</th>
         <th>Parameter</th>
         <th>File type described</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTCAT </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>Catalog file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTCOM </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>Communication medium </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTLOG </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME<br/>AFNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>Log files </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTACCNT </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME<br/>AFNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>Statistics files </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTPARM </p>
         </td>
         <td valign="top" width="18%">
            <p>PARTFNAM </p>
         </td>
         <td valign="top" width="63%">
            <p>Partner file (obsolete for Windows/Unix)</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTXLATE </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>File containing the description of a translation table </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTDEST </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>File containing a list of partners </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTAUTH </p>
         </td>
         <td valign="top" width="18%">
            <p>FNAME </p>
         </td>
         <td valign="top" width="63%">
            <p>File containing a list of authorized or prohibited IDFs </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTPARM </p>
         </td>
         <td valign="top" width="18%">
            <p>EXEC ... </p>
         </td>
         <td valign="top" width="63%">
            <p>End-of-transfer procedures </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTLOG </p>
         </td>
         <td valign="top" width="18%">
            <p>EXEC </p>
         </td>
         <td valign="top" width="63%">
            <p>Log switching procedure </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="19%">
            <p>CFTACCNT </p>
         </td>
         <td valign="top" width="18%">
            <p>EXEC </p>
         </td>
         <td valign="top" width="63%">
            <p>Statistics file switching procedure </p>
         </td>
      </tr>
</table>

Depending on the system, Transfer CFT supports the following communication
media:

-   Direct organization
    file (relative)
-   TCP synchronous
    medium

For a communication medium based on TCP/IP:

-   Host name
-   Configuration file
    name

Refer to the Transfer CFT*Operations Guide* corresponding
to your OS.

### <span id="Utility_media__CFTUTIL"></span>CFTUTIL media utility

Use the CFTUTIL utility command CONFIG to set the names of the media
it accesses, as presented in the table:

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>CONFIG command </p>
            <p>TYPE parameter</p>
</th>
         <th>File type described</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top">
            <p>PARM </p>
         </td>
         <td valign="top">
            <p>Parameter file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top">
            <p>PART </p>
         </td>
         <td valign="top">
            <p>Partner file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top">
            <p>CAT </p>
         </td>
         <td valign="top">
            <p>Catalog file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top">
            <p>COM </p>
         </td>
         <td valign="top">
            <p>Communication medium </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top">
            <p>INPUT </p>
         </td>
         <td valign="top">
            <p>Input data medium </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top">
            <p>OUTPUT </p>
         </td>
         <td valign="top">
            <p>Output data medium </p>
         </td>
      </tr>
</table>

By default, in the absence of the CONFIG command, the media accessed
by the utility are defined in the Transfer CFT*Operations Guide*
corresponding to your OS.

Depending on the operating system, the media names may be physical files
or logical files. Refer to the Transfer CFT*Operations Guide* corresponding
to your OS.

Depending on the system, the Transfer CFT utility supports the following
communication media:

-   Direct organization
    file (relative)
-   TCP synchronous
    medium

For a communication medium based on TCP/IP:

-   Host name
-   Configuration file
    name

### <span id="Programming_interface_media"></span>Programming interface media

The programming interface provides the following services:

-   Access to the transfer
    catalog
-   Dispatch of commands
    to CFT

The tables below list the media names by service for the COBOL and C
language applications.

#### **Media names by service in COBOL language interface**

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Service</th>
         <th>Command</th>
         <th>Parameter</th>
         <th><b>File type described</b>
</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>CFTI </p>
         </td>
         <td valign="top" width="16%">
            <p>OPEN </p>
         </td>
         <td valign="top" width="16%">
            <p>D-CAT </p>
         </td>
         <td valign="top" width="55%">
            <p>Catalog file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>CFTU </p>
         </td>
         <td valign="top" width="16%">
            <p>COM </p>
         </td>
         <td valign="top" width="16%">
            <p>D-COM </p>
         </td>
         <td valign="top" width="55%">
            <p>CFT communication medium </p>
         </td>
      </tr>
</table>

#### **Media names by service in C language interface**

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Service</th>
         <th>Command</th>
         <th>Parameter</th>
         <th>File type described</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>cftai </p>
         </td>
         <td valign="top" width="16%">
            <p>OPEN </p>
         </td>
         <td valign="top" width="16%">
            <p>cat </p>
         </td>
         <td valign="top" width="55%">
            <p>Catalog file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>cftaix </p>
         </td>
         <td valign="top" width="16%">
            <p>OPEN </p>
         </td>
         <td valign="top" width="16%">
            <p>cat </p>
         </td>
         <td valign="top" width="55%">
            <p>Catalog file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>cftau </p>
         </td>
         <td valign="top" width="16%">
            <p>COM </p>
         </td>
         <td valign="top" width="16%">
            <p>param </p>
         </td>
         <td valign="top" width="55%">
            <p><span>Transfer CFT</span> communication medium </p>
         </td>
      </tr>
</table>

The default names of the media accessed by the programming interface,
CATALOG file and COMMUNICATION medium, are defined in the Transfer CFT*Operations Guide* corresponding to your OS.

Depending on the system, the programming interface supports the following
communication media:

-   Direct organization
    file
-   TCP synchronous
    medium

And in the case of a communication medium based on TCP/IP

-   Host name
-   Configuration file
    name

Refer to the Transfer CFT*Operations Guide* corresponding to your
OS.

### <span id="Interactive_function_media"></span>Interactive function media

The interactive function media are defined by the customization function
of this component. The table below indicates, for each field, the file
type described:

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>File type described</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>Parm </p>
         </td>
         <td valign="top" width="82%">
            <p>Parameter file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>Part </p>
         </td>
         <td valign="top" width="82%">
            <p>Partner file </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>Cat </p>
         </td>
         <td valign="top" width="82%">
            <p>Catalog files </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>Log1 </p>
         </td>
         <td valign="top" width="82%">
            <p>Log files </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>Log2 </p>
         </td>
         <td valign="top" width="82%">
            <p> </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="18%">
            <p>Com </p>
         </td>
         <td valign="top" width="82%">
            <p>Communication medium </p>
         </td>
      </tr>
</table>

If this function is not activated, the media accessed are those defined
at the time the product is installed.

Depending on the system, the interactive functions support the following
communication media:

-   Direct organization
    file
-   TCP synchronous
    medium

For a communication medium based on TCP/IP:

-   Host name
-   Configuration file
    name

Refer to the Transfer CFT*Operations Guide* corresponding to your
OS.
