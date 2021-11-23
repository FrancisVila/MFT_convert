{
    "title": "Displaying online help",
    "linkTitle": "Displaying online help",
    "weight": "100"
}Online help is available for all Gateway online commands.

From the command prompt you can display three help levels:

-   [Lists of the subcommands associated with a specific command](#Displaying_subcommands_of_command)
-   [Lists of the parameters of a specified subcommand](#Displaying_params_of_subcommand)
-   [Lists of all details of a command or a subcommand](#Displaying_all_details)

<span id="Displaying_subcommands_of_command"></span>

### Displaying a list of subcommands associated with a specific command

To display a list of the subcommands comprising a specific command, from the command prompt enter the command name followed by a space and a single question mark (with or without quotation marks).

#### Syntax:

command  ?

or

command  "?"

#### Example:

peladm  ?

This command returns a list of all subcommands comprising the `peladm` command:

peladm

create\_site

update\_site

delete\_site

create\_loc\_site

update\_loc\_site

delete\_loc\_site

create\_lsite

update\_lsite

delete\_lsite

create\_appli

update\_appli

delete\_appli

create\_list

update\_list

delete\_list

create\_model

update\_model

delete\_model

create\_user

update\_user

delete\_user

create\_profile

update\_profile

delete\_profile

update\_trans

create\_cgate

update\_cgate

delete\_cgate

create\_cgategroup

update\_cgategroup

delete\_cgategroup

update\_ruletable

create\_decisionrule

update\_decisionrule

delete\_decisionrule

create\_proxy

update\_proxy

delete\_proxy

create\_tradepart

update\_tradepart

delete\_tradepart

<span id="Displaying_params_of_subcommand"></span>

### Displaying a list of the parameters of a specific subcommand

To display a list of the parameters comprising a specific subcommand, from the command prompt enter the command and subcommand, followed by a space and a single question mark (with or without quotation marks).

#### Syntax:

command subcommand  ?

or

command subcommand  "?"

#### Example:

peladm create\_user  ?

This command returns a list of all parameters comprising the `create_user` subcommand.

peladm    create\_user

{-username (-n)}

\[-profile (-pr)\]

\[-group (-gr) group\_name\]

\[-password (-pswd)\]

\[-comments (-cts)\]

\[-expired (-exd)\]

\[-maxretry (-mxr)\]

\[-administrator (-admin) {Y | (N)}

\[-allxfer (-ax) {Y | (N)}

\[disabled (-dd) {Y | (N)}

<span id="Displaying_all_details"></span>

### Displaying all details of a command and each available subcommand

To display details of all the parameters of a command and each available subcommand, enter the name of the command.

To display the complete parameter details of only a subcommand, enter the name of the command, the name of the subcommand and double question marks.

#### Syntax:

command  ??

or

command  subcommand  ??

#### Example:

pelctl  ??

This command returns the details:

pelctl

   start\_site

{-alias (-a)}

\[-init\_mode (-im)\]

\[-resp\_mode (-rm)\]

\[-commpath\_used (-cu) { MAIN | ALT1 | ALT2 | ALT3 }\]

\[-trace\_mode (-tm)\]

\[-cdi\_mode (-cdm)\]

   stop\_site

{-alias (-a)}

\[-init\_mode (-im)\]

\[-resp\_mode (-rm)\]

\[-trace\_mode (-tm)\]

\[-cdi\_mode (-cdm)\]

   control\_trans

{-local\_ident (-i)}

{-action (-a) { C | S | R }}

\[-retry\_delay (-rd)\]

   archive\_log

   suspend\_log

   resume\_log

   archive\_stat

   suspend\_stat

   resume\_stat

   load\_net\_security

   load\_tcp\_org\_port

   trace\_process

{-process\_name (-pname)}

{-trace\_level (-l) { 0..(0)..4 }}

\[-all (-a) to trace process and entity\]

   trace\_entity

{-entity\_name (-ename)}

{-trace\_level (-l) { 0..(0)..4 }}

   kill\_connection

{-connection\_id (-ci)}

   disconnect\_user

{-connected\_user\_id (-cui)}

   detect\_swift\_recovery

### Displaying details of a command without subcommands

The `peltrans`, `pelpur`, and `pelmig` commands have no associated subcommands. You obtain the same help display with either of the following command formats:

command  ?

and

command  ??

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
