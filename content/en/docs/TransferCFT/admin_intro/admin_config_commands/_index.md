{
    "title": "Administrative configuration commands",
    "linkTitle": "Manage the configuration",
    "weight": "210"
}The topics in this section describe how to use command line operations to administer Transfer CFT configuration options, and is comprised of the following:


| Command  | Description  |
| --- | --- |
| <a href="cftaccnt_concepts">CFTACCNT</a>  | Recording mode for statistical data  |
| <a href="catalog_parameter_concepts">CFTCAT</a>  | Catalog attributes  |
| <a href="communication_media_concepts">CFTCOM</a>  | Communication media  |
| <a href="../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftlog">CFTLOG</a>  | Transfer log files  |
| <a href="network_resource_concepts">CFTNET</a>  | Network resources  |
| <a href="cftparm_general_parameters">CFTPARM</a>  | General parameters definition  |
| <a href="transfer_protocol_concepts">CFTPROT</a>  | Transfer protocol  |


## What is a   service file medium

{{< TransferCFT/componentshortname  >}} medium refers to any data support or local communication
means used by  {{< TransferCFT/componentshortname  >}}. A distinction is made between the media:

-   Accessed by the
      {{< TransferCFT/componentshortname >}}
-   Accessed by the
      {{< TransferCFT/componentshortname >}} utility
-   Used by the interactive
    functions
-   Used by the programming
    interface

### Definitions

The following terms are used in this section:

-   PHYSICAL FILE which
    describes the name and physical location of a file type medium
-   If the file name
    begins with a reserved character, designated by **char-file** - see the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide* corresponding to your OS,
    this is a logical name interpreted by  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
-   CFTIN and CFTOUT
    for standard task input/output
-   TCP synchronous
    medium to designate a communication channel

The  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> medium names can be set up for the:

-   Programming interface
    (catalog name, communication medium name with the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>):
    by the OPEN and COM services
-   <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>:
    CFTPARM, CFTCOM, CFTCAT, CFTLOG, CFTACCNT objects (the name of the Parameter
    file cannot be changed)
-   <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> utility:
    CONFIG command
-   Interactive functions:
    the customization function is used to set the names of the Parameter,
    Partner, Catalog and Log files, and the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication medium

<span id="CFT_monitor_media"></span>

### <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> media files

You cannot change the name of the <span style="font-style: italic;">parameter
file</span>. It constitutes the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> anchor point containing all the data
defined by the parameter setting, and in particular the names of the other
files and media. However, you can establish a correspondence between this
logical name and a physical name in the flow of CFT activation commands.

The names of the other  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> media are defined by parameter setting,
although  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> has default values.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
media by type of object and parameter

```

Object

Parameter

File type described

CFTCAT 
FNAME 
Catalog file 
CFTCOM 
FNAME 
Communication medium 
CFTLOG 
FNAME
AFNAME 
Log files 
CFTACCNT 
FNAME
AFNAME 
Statistics files 
CFTPARM 
PARTFNAM 
Partner file (obsolete for Windows/Unix)
CFTXLATE 
FNAME 
File containing the description of a translation table 
CFTDEST 
FNAME 
File containing a list of partners 
CFTAUTH 
FNAME 
File containing a list of authorized or prohibited IDFs 
CFTPARM 
EXEC ... 
End-of-transfer procedures 
CFTLOG 
EXEC 
Log switching procedure 
CFTACCNT 
EXEC 
Statistics file switching procedure 
```

Depending on the system,  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> supports the following communication
media:

-   Direct organization
    file (relative)
-   TCP synchronous
    medium

For a communication medium based on TCP/IP:

-   Host name
-   Configuration file
    name

Refer to the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide* corresponding
to your OS.

<span id="Utility_media__CFTUTIL"></span>

### CFTUTIL media utility

Use the CFTUTIL utility command CONFIG to set the names of the media
it accesses, as presented in the table:


           |  CONFIG command<br/>TYPE parameter  | File type described  |
 --- | --- | --- |
|  PARM  |  Parameter file  |
|  PART  |  Partner file  |
|  CAT  |  Catalog file  |
|  COM  |  Communication medium  |
|  INPUT  |  Input data medium  |
|  OUTPUT  |  Output data medium  |


By default, in the absence of the CONFIG command, the media accessed
by the utility are defined in the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide*
corresponding to your OS.

Depending on the operating system, the media names may be physical files
or logical files. Refer to the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide* corresponding
to your OS.

Depending on the system, the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> utility supports the following
communication media:

-   Direct organization
    file (relative)
-   TCP synchronous
    medium

For a communication medium based on TCP/IP:

-   Host name
-   Configuration file
    name

<span id="Programming_interface_media"></span>

### Programming interface media

The programming interface provides the following services:

-   Access to the transfer
    catalog
-   Dispatch of commands
    to CFT

The tables below list the media names by service for the COBOL and C
language applications.

#### **Media names by service in COBOL language interface**

```

Service

Command

Parameter

**File type described**

CFTI 
OPEN 
D-CAT 
Catalog file 
CFTU 
COM 
D-COM 
CFT communication medium 
```

#### **Media names by service in C language interface**

```

Service

Command

Parameter

File type described

cftai 
OPEN 
cat 
Catalog file 
cftaix 
OPEN 
cat 
Catalog file 
cftau 
COM 
param 
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication medium 
```

The default names of the media accessed by the programming interface,
CATALOG file and COMMUNICATION medium, are defined in the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide* corresponding to your OS.

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

Refer to the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide* corresponding to your
OS.

<span id="Interactive_function_media"></span>

### Interactive function media

The interactive function media are defined by the customization function
of this component. The table below indicates, for each field, the file
type described:

```

Field

File type described

Parm 
Parameter file 
Part 
Partner file 
Cat 
Catalog files 
Log1 
Log files 
Log2 
 
Com 
Communication medium 
```

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

Refer to the  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>*Operations Guide* corresponding to your
OS.
