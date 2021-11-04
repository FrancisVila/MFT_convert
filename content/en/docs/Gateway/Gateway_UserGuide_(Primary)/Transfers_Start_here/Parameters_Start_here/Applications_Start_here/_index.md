{
    "title": "About applications",
    "linkTitle": "Managing application objects",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Introduction to Applications](#intro)

[How Gateway assigns an Application](#How_Gateway_assigns_an_Application)

<span id="intro"></span>

## Applications

When you define a File Transfer Request you can provide certain file system attributes via the <span style="font-style: italic;">Application object</span>. Some of the attributes are used by the local file system (local attributes). Others are used to manage file data content that is transmitted over the network (transfer attributes). Additionally, an Application object contains parameters that define how this Application can send or receive files. For example:

-   Local file system attributes such as name, file structure and type
-   Record format
-   Data encryption and padding
-   Online record attributes
-   Compression mode

The file transfer process may occur between different platforms, for example, Windows workstations, MVS Mainframes, UNIX servers and so on. Since the data storage format on these machines may be completely different, Gateway provides automatic character set conversion via the Application or the Model object. So, Gateway can transparently convert a file sent from an EBCDIC system (that is, MVS) whose final destination is an ASCII system, and vice versa.

It is recommended that you use an Application with certain protocols (for example, PEL). With other protocols, Applications are used for a specific purpose (for example, a link between the Application name and the protocol file name in PeSIT or FTP).

You can use the GUI or online commands to manage Applications.

<span id="How_Gateway_assigns_an_Application"></span>

## How Gateway assigns an application

Before data transfer, Gateway assigns the appropriate Application to the Transfer, depending on the protocol.

### PeSIT Transfers

The Application name is the incoming protocol file name. Depending on the type of data to be transferred, the default Application names are:

-   DEFAULT\_B (Binary)
-   DEFAULT\_A (ASCII)
-   DEFAULT\_E (EBCDIC)

If Gateway cannot locate the required Application (from those listed above), it uses the Application named DEFAULT.

### FTP/SFTP Transfers

From the client station, you can define Application names with an FTP <span class="code">SITE</span> command before using the <span class="code">STOR</span> or the <span class="code">RETR</span> command. Depending on the FTP data type, the default Application names are:

-   FTP\_A (ASCII)
-   FTP\_B (binary)
-   FTP\_E (EBCDIC)

Since ASCII and EBCDIC are meaningless for SFTP, Gateway always assigns the default Application FTP\_B to SFTP Transfers.

### HTTP Transfers

Since the client station does not provide the Application name, Gateway uses the default FTP Applications for file reception.

Sites and Applications always belong to a group. For a Transfer to be valid, its Remote Site and Application must belong to the same group. However, applications can be configured over http by setting the parameter <span class="code">use\_applications </span>to <span class="code">1</span> in <span class="code">&lt;installation\_folder>/run\_time/etc/pelsetup.def</span> file, section <span class="code">FT\_HTTP </span>(configuration needs to be rebuilt)

#### Line endings conversion

Gateway offers the possibility to convert line-endings when receiving a file.

This functionality is configurable, activated by the <span class="code">\[ft\_http\]convert\_ascii\_line\_endings</span> parameter (default is set to <span class="code">0 - Disabled</span>).

When this parameter is set to <span class="code">1</span>, the line endings are converted according to the target machine.

## File organizations on Mainframe

The following notes on file organization relate to sending and receiving files to and from a mainframe.

### Sequential

In a sequential file organization, records are organized in the sequence by which they were added. New records cannot be inserted between existing records, but only at the end of the last record. It is a simple file organization that allows processing of batches of records in the file without altering its structure. However, to access a particular record, processing must run through all the other records before it as there is no method to point to the location of a certain record. Searching for a record, especially when there are thousands of entries, may be time consuming. Note that after a record is written in the file it cannot be shortened, lengthened or deleted, it can only be rewritten if the length doesn't change.

### Relative

Another approach of organizing records in a file would be to generate a key pointing to the relative position in the file where the record begins. The relative key is assigned to determine the order of records in the file. The first record would have a relative number of 1, the second record would have a relative number of 2 and so on. Records may have various sizes, in bytes, so they can be arranged relative to each other, with the restriction that care must me taken to always insert a new record with the next relative key in the sequence (Assuming that the last record has the relative number 7, the new record that would be inserted must and would have the relative number 8). Also, with the relative key, you can randomly access any record without starting from the top record. The disadvantage is its dependence on relative keys. If you do not know the relative key of a particular record, you won't be able to randomly access the file.

### Indexed

An indexed file organization contains record reference numbers, like unique identifiers for each record in relation to other records. These references are similar to the primary keys in a RDBMS. Alternate keys can also be defined to allow alternate methods of accessing the record. For example, instead of accessing an employee's record using employee numbers, you can use an alternate key that reference employees by departments. This allows greater flexibility for users to randomly search through thousands of records in a file. However, additional meta information has to be maintained for each of these files increasing their size on disk and requiring periodic maintenance to avoid wasted space and avoid performance degradation.

Related topics

[Working with Applications](working_with_applications_(gui))

[Working with Applications (command line)](working_with_applications_cli)

[Application objects: Parameters List](working_with_applications_cli/application_object_parameter_list)

[Overview: Applications](../../../ov_gateway/ov_applications)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
