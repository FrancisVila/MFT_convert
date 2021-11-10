{
    "title": "Install services in command line",
    "linkTitle": "Install services in command line",
    "weight": "140"
}After adding a Windows service in command line, the default system user is the user that started the service. To define a specific user, you must edit the service properties in the Services page.

> **Note:**
>
> If you plan to integrate Transfer CFT with Central Governance and also plan to use Service mode, please refer to the additional instructions in Service mode set up when using Central Governance.

Windows only

## Install services

### <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> services

1.  To install the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> service, access the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> directory:

    cd %TransferCFT\_directory%

2.  Enter the following:

    cscript /nologo home\\bin\\cftsrvin.vbs n=CFT36

    Where <span class="italic_in_para">n</span>= &lt;CFT plus the current version of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>&gt;

### Copilot services

From the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> home directory, run:

copsrv.exe -install &lt;service\_name> &lt;displayname> &lt;cftdirruntime>

**Example**

For <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> version <span class="mc-variable axway_variables.Component_Version variable">3.9</span> Copilot you would enter:

c:\\CFT36\\Transfer\_CFT\\home\\bin>copsrv.exe -install CFT\_Copilot36 CFT\_Copilot36 c:\\CFT36\\Transfer\_CFT\\runtime

### Activate services

Using CFTUTIL activate the services for both Transfer CFT and Copilot with the uconf <span class="code">service </span>configuration parameters.

<span class="bold_in_para">Example</span>



    uconfset id=cft.nt.service_name, value=CFT36
    uconfset id=cft.nt.service_mode, value=yes

    uconfset id=copilot.nt.service_name, value=CFT_Copilot36
    uconfset id=copilot.nt.service_mode, value=yes

<span id="Service"></span>

## 
