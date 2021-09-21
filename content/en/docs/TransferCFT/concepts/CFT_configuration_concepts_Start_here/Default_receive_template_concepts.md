{
    "title": "Default receive template CFTRECV",
    "linkTitle": "Default receive template CFTRECV",
    "weight": "180"
}This topic describes general file reception concepts and the
CFTRECV template.

[Receive
file parameter summary](#receive_file_parameter_summary) 

[Receiving
a file](#receiving_a_file)

[About
the default CFTRECV object](#about_the_default_cftrecv_object)

Related
topics

-   Command syntax
    [CFTRECV](../../../c_intro_userinterfaces/command_summary)
-   Parameter list
    [CFTRECV](../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv)

## <span id="Receive_file_parameter_summary"></span>Receive file parameter summary

This section lists the parameters and syntax that you use to create
a receive file transfer using the command line interface. Certain
parameters can be classified into categories:

-   identification
    parameters

<!-- -->

-   general: ID,
    USERID, GROUPID
-   specific to
    the PeSIT protocol (PeSIT D CFT profile or PeSIT E): RUSER, SUSER

<!-- -->

-   protection of the
    parameters set: FORCE
-   free parameters
    set locally by the Transfer CFT user: COMMENT, OPERMSG, DELETE, NOTIFY
-   execution control
    parameters:

<!-- -->

-   general: PRI
-   user: EXEC,
    EXIT
-   cycle management:
    MINDATE, CYCTIME

<!-- -->

-   data processing
    parameters: NCOMP, XLATE, FCODE
-   file parameters
    (general):

<!-- -->

-   file management:
    FACTION, FDISP
-   physical name:
    FNAME, WFNAME  
    physical characteristics (global file): FSPACE, FORG, FTYPE
-   physical characteristics
    (records) : FRECFM, FLRECL, FBLKSIZE, FKEYLEN, FKEYPOS

*Use of parameters defining file characteristics:*
Several of the parameters defining the characteristics of the receiver
file can often be omitted in normal practice since the protocol messages
transport (or make it possible to locate) the indications relative to
the file characteristics communicated by the sender.

For a given transfer, these protocol values are the DEFAULT values of
the corresponding Fxxxxx parameters:

<table cellspacing="0" hspace="9" vspace="9">
   <col/>
   <col/>
      <tr>
         <td valign="top" width="26%">
            <p>PeSIT E CFT/CFT</p>
            <p>PeSIT D CFT profile </p>
         </td>
         <td valign="top" width="74%">
            <p>In PeSIT E (CFT to CFT), or PeSIT D CFT profile (transfer 
 between 2  <span>Transfer CFT</span>s), the default values taken by the FSPACE, 
 FTYPE, FBLKSIZE, FLRECL and FRECFM parameters are the values sent by the 
 partner (see the CFTSEND object, NSPACE, NTYPE, NBLKSIZE, NLRECL, NRECFM 
 parameters). For open mode operation, the FNAME parameter can also inherit 
 the value of the partner NFNAME parameter. </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="26%">
            <p>PeSIT E </p>
         </td>
         <td valign="top" width="74%">
            <p>In PeSIT E, the default values taken by the FKEYLEN and 
 FKEYPOS parameters are the values sent by the partner (see the NKEYLEN 
 and NKEYPOS parameters of the CFTSEND object). </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="26%">
            <p>PeSIT SIT profile </p>
         </td>
         <td valign="top" width="74%">
            <p>In PeSIT SIT profile, the "file size", "record 
 format" and "record length" information items sent by the 
 protocol are taken as the default values of the FSPACE, FRECFM, FLRECL 
 parameters.</p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="26%">
            <p>ODETTE </p>
         </td>
         <td valign="top" width="74%">
            <p>In the ODETTE protocol, the default values of the FRECFM, 
 FLRECL and FSPACE parameters are deduced from the ODETTE parameters received</p>
         </td>
      </tr>
</table>

<span id="new_link_receive_templates"></span>For more information, see the [Protocol](../../../protocols_start_here) topics.

## <span id="Receiving_a_File"></span>Receiving a file

The figure below shows the general relationships
that are established between a user RECV command and the CFTPART and CFTRECV
parameter setting commands, within the framework of a transfer from a
single partner.

If there is no CFTRECV command with an identifier
ID = FI, the default characteristics indicated in the CFTRECV ID = &lt;default>
command, are used to supplement those indicated in the RECV command as
required.

Correspondence
between the RECV file command and Transfer CFT parameter setting

<img src="Correspondence_between_RECV_and_parameter.gif" width="729" height="440" />

## <span id="About_the_default_CFTRECV_object"></span>About the CFTRECV template object

Use the Initial CFTRECV object to:

-   Give the default
    name and local physical characteristics of the file to receive
-   Define the default
    actions to perform locally during and after the transfer (translation,
    compression, call to a user EXIT, an end-of-transfer procedure...)
-   Authorize the default
    time slot and default user associated with the transfers

There is no limit on the number of CFTRECV objects that you can create
in Ongoing CFTRECV folder. In this topic, you define the template CFTRECV
object.

Certain default objects cannot be deleted. The template CFTSEND, CFTRECV
and CFTETB objects can not be deleted if they are used by another configuration.

### <span id="Parameters_Associated_with_a_Model_File"></span>Parameters Associated with a Model File

CFTRECV commands include parameters controlling the reception process
and the storing of the data received.

Each CFTRECV command - "default" command excluded - controls
the receiving of the model file having the same identifier (IDF corresponding
to the ID of the CFTRECV command). The "default" CFTRECV command,
for its part, applies to all other model files (IDF not corresponding
to any CFTRECV command ID).

For clarity, all CFTRECV commands are usually grouped in a parameter
setting source file and the default CFTRECV command is placed in the first
or last position.

The CFTRECV command is used to specify, for each model file (IDF):

-   the name and the
    physical characteristics (for example: format and record length) of the
    receiver file
-   the actions to
    be performed locally such as:

<!-- -->

-   call of a user-written
    "file EXIT" task during the transfer
-   actions performed
    by the monitor on the receiver file at the beginning of transfer
-   data translation
    during reception
-   call to a procedure
    to be executed on completion of the transfer, and so on

<!-- -->

-   miscellaneous parameters
    controlling the execution of transfers, such as:

<!-- -->

-   authorized
    time slot
-   default user
    identifier associated with transfers

The receiver file name and physical characteristics parameters are taken
into account at each new receive transfer, at the start of the transfer.
If Transfer CFT is creating a new receiver file:

-   these parameters,
    if explicitly defined, take precedence over the values extracted (or deduced)
    from the protocol messages received
-   however, if the
    receive transfer is initiated by a local RECV command, any explicitly
    defined parameters accompanying this command *take precedence over the
    parameters of the CFTRECV command* if the value of the FORCE parameter
    is FORCE = NO (for all the parameters common to both commands, CFTRECV
    only supplies the default values to RECV)
-   *they
    are not taken into account* if defined in the CFTRECV command and if
    the value of the FORCE parameter is FORCE = YES

The following precedence rule applies globally:

-   If FORCE = NO,
    the parameters of RECV take precedence over those of CFTRECV
-   If FORCE = YES,
    the parameters of CFTRECV take precedence over those of RECV  
    These parameters themselves take precedence over the protocol values
    received which themselves take precedence over any default file characteristics
    provided for within some systems, independently of the Transfer CFT parameter
    setting.
-   Where an already
    existing file is reused to receive the data of a new transfer, it is generally
    not possible to take new file characteristics into account: Transfer CFT’s
    "standard" behavior then simply involves checking that the new
    values are compatible with the existing ones.
-   If data is stored
    in an already existing "envelope" (for example, when Transfer
    CFT adds a new member to an already existing partitioned file), this corresponds
    to an intermediate case between the two previous ones. New values may
    be taken into account for some parameters but not for others; Transfer
    CFT’s behavior is system-dependent.

The file received may be stored during the transfer in a temporary file
which is renamed at the end of the transfer.

 