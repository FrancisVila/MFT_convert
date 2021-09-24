{
    "title": " Customize\u00a0installation files (A00CUSTO)",
    "linkTitle": " Customize\u00a0installation files (A00CUSTO)",
    "weight": "200"
}## <span id="Customizing JCL A00CUSTO parameters"></span>Customize JCL <span id="kanchor77"></span>A00CUSTO parameters

The A00CUSTO JOB customizes the installation files. The customization is done directly in the installation library instance environment. You must quit the file editing program and library before you execute the SUBMIT. If you do not first quit these programs before executing the SUBMIT, the message Waiting for data set is returned. If you performed an Installer installation, these parameters are already customized.

### Installed directories

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do            NOT customize the distribution environment.          </td>
      </tr>
</table>

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Variables </th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>CFTV2</p>
         </td>
         <td>
            <p>Prefix of the Transfer CFT instance environment.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DISTLIB</p>
         </td>
         <td>
            <p>Three first qualifiers of the distribution environment.</p>
            <p>Example: Axway.XFB.CFT00332</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DISTLEV</p>
         </td>
         <td>
            <p>Fourth qualifier of the distribution environment (level of distribution) </p>
            <p>Example: CF030000</p>
         </td>
      </tr>
   </tbody>
</table>

You can repeat A00CUSTO several times to customize any parameters that were not customized.

## Advanced parameters

To make any modifications to advanced parameters you must do this prior to starting the A05ALL JCL.

The parameters can be modified in the A12OPTSP member. For more information, refer to [Set standard JCL parameters A12OPTSP](../t_customize_instance_zos).

## Replay the customization

After completing the initial A00CUSTO customization, you can use the JCL A04RPLAY to repeat this process. This JCL recopies the members from distribution environment to the target environment (including the INSTALL, EXEC, UPARM and SAMPLE libraries).

Once the JOB is complete, update the A03PARM file in the target environment and resubmit the JCL A00CUSTO.

Related topics

-   [Installation overview](c_install_overview_zos.htm)
