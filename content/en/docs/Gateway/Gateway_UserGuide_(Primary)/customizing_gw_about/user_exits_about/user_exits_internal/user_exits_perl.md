{
    "title": "User exits in Perl",
    "linkTitle": "User exits in Perl",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

The GIK Perl external user exit <span style="font-weight: bold;">GIKuexpl</span> comprises a set of five Perl exits:

-   <span class="code" style="font-weight: bold;">beforebegin.pl</span> – Transfer receive exit
-   <span class="code" style="font-weight: bold;">afterbegin.pl</span> – Start-of-transfer exit
-   <span class="code" style="font-weight: bold;">afterend.pl</span> – End-of-transfer exit
-   <span class="code" style="font-weight: bold;">xfermonitor.pl</span> – Routing behavior exit
-   <span class="code" style="font-weight: bold;">exitpcnx.pl</span> – Protocol connection exit

All the exits are located in the following directory:

On UNIX

&lt;Gateway installation directory>/run\_time/scripts/perl/

On Windows

&lt;Gateway installation directory>\\run\_time\\scripts\\perl\\

<span id="paras"></span>

## Parameters

Each Perl exit includes a set of parameters (indication and response parameters).

You can access these parameters via two key = value type tables:

-   Indication parameters are referenced by a hash table called <span style="font-weight: bold;">IN</span>.
-   Response parameters are referenced by a hash table called <span style="font-weight: bold;">OUT</span>.

<span id="Indication_Parameters"></span>

### Indication parameters: IN

The indications supplied in this table are for information purposes only and any changes to their values have no effect on the transfer. Two types of indication parameter exist:

-   Transfer TLS parameters (prefixed with <span class="code" style="font-weight: bold;">TlsInfo</span>)
-   Transfer parameters (prefixed with <span class="code" style="font-weight: bold;">Params</span>)

TlsInfo\_server\_auth

Params\_org\_alias

<span id="Response_Parameters"></span>

### Response parameters: OUT

You can modify exit response parameters. Response parameters are prefixed with <span class="code" style="font-weight: bold;">Params</span>:

Params\_dir\_path

The <span class="code" style="font-weight: bold;">afterbegin</span> exit does not use response parameters.

<span id="In_Out_user_parameters"></span>

### Input/Output user parameters: IN/OUT

The <span class="code" style="font-weight: bold;">xfermonitor.pl</span> exit includes certain user parameters that are used as both input and output parameters. These parameters are always prefixed with <span class="code" style="font-weight: bold;">UserParam</span>:

UserParam\_string\_user\_param1

<span id="Perl_parameter_display_script"></span>

### Perl parameter display script

The following is a sample Perl script used to display all transfer indications and response parameters.


    #transfer indications
    @keys = keys %IN;
    @values = values %IN;
    while (@keys) {
        print pop(@keys), '=',pop(@values);
    }
    #response parameters
    @keys = keys %OUT;
    @values = values %OUT;
    while (@keys) {
        print pop(@keys), '=',pop(@values);

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)