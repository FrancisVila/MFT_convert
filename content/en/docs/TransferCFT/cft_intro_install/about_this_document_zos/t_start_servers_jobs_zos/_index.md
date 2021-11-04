{
    "title": "Start and stop the server JOBs",
    "linkTitle": "Post-installation",
    "weight": "170"
}This section presents JCL examples that you can use to create the JOBs necessary to run Transfer CFT. All of the JCLs are located in the **target.INSTALL** library.

-   [Starting Transfer CFT JOB CFTMAIN](#Starting%20the%20CFTMAIN%20example)
-   [Transfer CFT user interface server commands](#Transfer%20CFT%20user%20interface%20server)

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If you installed <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> along with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, the uconf <span class="code">copilot.misc.cftstart.enable</span> is automatically set to <span class="code">Yes</span>. This allows <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> to control stopping and starting your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>.         </td>
      </tr>
   </tbody>
</table>

<span id="Starting the CFTMAIN example"></span>

## Start Transfer CFT 

The CFTMAIN JOB is an example of a JCL to start Transfer CFT. Beginning with the CFTMAIN sample, you can create JOBs to meet your operating requirements.

You can perform Transfer CFT commands using the CFTUTIL utility, the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> user interface, or the console interface.

Start the CFTMAIN JCL in the target.INSTALL library.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>CFTMAIN must be APF authorized to start if the UCONF <span class="code">cft.mvs.monitor.check_apf </span>variable is set to <span class="code">Yes</span>. Otherwise, the Transfer CFT log displays <span class="code">CFTI01F CFT error CFT is not APF-authorized</span>.         </td>
      </tr>
   </tbody>
</table>

## Stop Transfer CFT 

The following are commands that you can use to stop Transfer CFT outside of a customized JCL (such as the delivered sample JCL, **CFTSTOP**, in the target.INSTALL library).

**Normal stop**


    /F <Jobname>,SHUT FAST=NO or SHUT FAST=YES

**Quick stop**

Enter the operator command:


    /P <Transfer CFT Jobname>

\- or -


    /F <Transfer CFT Jobname>,SHUT FAST=YES

**Force** <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-weight: bold;">Transfer CFT</span> **shut down**


    /F <Transfer CFT Jobname>,SHUT FAST=KILL

### Restart

The following command restarts Transfer CFT outside of a customized JCL. Enter the operator command:


    /F Jobname,SHUT RESTART=YES

### Status

Use the CFTPING in the target.INSTALL library to ping your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

<span id="Transfer CFT user interface server"></span>

## Transfer CFT Copilot server commands

The Transfer CFT Copilot server is a sub component that is mandatory when using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>. Additionally, this server may function as the node manager when using multi-node.

### Starting the Copilot server

COPRUN is an example of a JCL statement that starts the Transfer CFT Copilot server. The server can be started as a Start Task. The Transfer CFT Copilot server STEPLIB, and then JOBLIB should be defined as an APF. If it is not defined as an APF, no RACF check can be performed. This results in no log-on check being available and all requests are done with the user associated with the server JOB.

When the <span class="code">copilot.misc.CreateProcessAsUser</span> variable is set, STEPLIB or JOBLIB can be non-APF. Only a <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>/PassPort user can sign on to Copilot user interface.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When the ‘cft.mvs.copilot.check_apf’ uconf variable is set to ‘Yes’, CFTCOPL must be APF authorized to start.         </td>
      </tr>
   </tbody>
</table>

LOG message: <span class="code">+CFTI42E Copilot must be APF-authorized.</span>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>CFTCOPL must be APF authorized to start if the UCONF <span class="code">cft.mvs.copilot.check_apf </span>variable is set to <span class="code">Yes</span>. Otherwise, the Transfer CFT log displays <span class="code">CFTI42E Copilot must be APF-authorized</span>.         </td>
      </tr>
   </tbody>
</table>

### Stopping user interface (Copilot) server

COPSTOP is an example of the JCL stop statement for the Transfer CFT UI server. You can also stop the Transfer CFT UI server using the operator command pause (/P jobname) for the server-associated task.

### Checking the Copilot server status

You can use COPSTATU, for example, as the JCL statement to display the Transfer CFT Copilot server status in the current LPAR.

## Register with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

If you intend to implement <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, please refer to the <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Transfer CFT</span> *User's Guide &gt; [*Register with* <span class="mc-variable Primary.CG or_UM variable" style="font-style: italic;">Central Governance</span>](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.
