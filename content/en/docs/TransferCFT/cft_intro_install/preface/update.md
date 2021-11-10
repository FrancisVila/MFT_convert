{
    "title": "Update Transfer CFT ",
    "linkTitle": "Update",
    "weight": "210"
}This section describes how to update your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> HP NonStop by applying a service pack.

The procedure consists of installing a service pack over an existing Transfer CFT installation of the same version. The update procedure uses the same format as for an installation.

If you are not familiar with the installation procedure, you may want to first read <a href="../installation" class="MCXref xref">Install Transfer CFT</a> .

## Procedure

1.  Download the service pack in binary mode. The service pack name contains the letters "SP" and the service pack level.  
    <span class="bold_in_para">Example</span>  
    <span style="font-family: 'Courier New';">Transfer\_CFT\_<span class="mc-variable axway_variables.Release_Number variable">3.9</span>\_**SP4**\_hp\_nonstop\_oss-x86-32\_BN12345678.zip</span>  
    This example is of service pack 4. You can install it over any existing Transfer CFT 3.3.2 for HP NonStop X86 installation. The existing installation can already have one or several applied updates. In this example, possible service packs would include SP1 to SP3, or any available patches.
2.  Decompress the archive using the <span class="code">unzip </span>command.
3.  Load the profile and stop both Transfer CFT and Copilot before applying the update.
4.  Use the <span class="code">install </span>command plus the <span class="code">&lt;pathname></span> to install the service pack. If the pathname is not the same as the existing installation though, the process fails.

-   Example  
    The following example demonstrates a Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> SP4 installation over an existing product installed in <span class="code">/home/cftuser/CFT33x</span>.

> **Note:**
>
>  

When you install a service pack, the contents of the home directory are updated, but the runtime directory remains untouched. This is so that your customizations, such as APIs, are not overwritten.

<span id="Uninstal"></span>

## Uninstall a service pack

A rollback procedure uninstalls the last installed service pack and reverts Transfer CFT to the update level prior to that service pack. If you have applied several updates, you can rollback several times; the rollback procedure does not affect your data.

1.  Load the profile and stop both Transfer CFT and Copilot before starting the rollback procedure.
2.  Execute the <span class="code">./install.sh rollback</span> script located in the installation <span class="code">inst/TransferCFT</span> subdirectory.

-   Example  
    The following example demonstrates a Transfer CFT 3.5 SP4 rollback for a product installed in <span class="code">/home/cftuser/CFT33x.</span>
