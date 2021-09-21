{
    "title": "Standand installation (A05ALL )",
    "linkTitle": "Standand installation (A05ALL )",
    "weight": "210"
}In this section you run A05ALL for a standard installation.

## Use A05ALL to perform an auto install

The A05ALL JCL automatically runs the following members.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Step</th>
         <th>Description</th>
         <th>Member </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td>Create and initialize instance files: UCONF, UCONFRUN, FTEST, MONLOG, and LOG.         </td>
         <td>A06FILES         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>
            <p>Assemble and link-edit SGINSTAL for Transfer CFT z/OS options. </p>
            <p>Non-SMP/E installation mode.
                        </p>
         </td>
         <td>A12AOPTS         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>
            <p>Link-edit all Transfer CFT modules.</p>
            <p>Non-SMP/E installation mode.
                        </p>
         </td>
         <td>B20LINK         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Generate an encryption key. See also <a href="../t_customize_instance_zos">Password encryption</a>.         </td>
         <td>CFTGNKEY         </td>
      </tr>
      <tr>
         <td colspan="3">5.A <i>or</i> 5.B         </td>
      </tr>
      <tr>
         <td>5.A         </td>
         <td>
            <p>If cgenable is set to no:</p>
            <ul>
               <li>Sets the uconf variables:            <ul>               <li>          cft.runtime_dir               </li>               <li>          cft.listcat_compat               </li>               <li>          cft.state_compat               </li>            </ul>               </li>
               <li>Generates the SAMPLE(CFTPARM) parameter sample from the SAMPLE(ZCFTPARM) template                </li>
               <li>Generates the SFTP  SAMPLE(CFTSFTP) parameter sample from the  SAMPLE(ZCFTSFTP) template               </li>
            </ul>
         </td>
         <td>CFT$SET          </td>
      </tr>
      <tr>
         <td>5.B         </td>
         <td>
            <p>If cgenable is set to yes:</p>
            <ul>
               <li>Sets the uconf variables for Central Governance               </li>
               <li>Generates the Transfer CFT parameters sample from a template               </li>
            </ul>
         </td>
         <td>CFT$SETC         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>
            <p>Create Transfer CFT files (Parm, Part, Catalog, Com(file),       account).</p>
         </td>
         <td>D40INIT         </td>
      </tr>
      <tr>
         <td>7         </td>
         <td>
            <p>Loads the Transfer CFT default settings. </p>
         </td>
         <td>E50PARM         </td>
      </tr>
      <tr>
         <td colspan="2">  PKI         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>9         </td>
         <td>
            <p>Creates Data base PKI using the sample certificates.</p>
         </td>
         <td>D43PKI         </td>
      </tr>
      <tr>
         <td>10         </td>
         <td>
            <p>If pkitype=passport: Enable PassPort PKI configuration.</p>
         </td>
         <td>D44PASS         </td>
      </tr>
      <tr>
         <td>11         </td>
         <td>
            <p>If pkitype=system:   Enable the PKI system.                           </p>
         </td>
         <td>D47SYST         </td>
      </tr>
      <tr>
         <td colspan="2">   Central Governance         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>15         </td>
         <td>
            <p>If cgenable=yes:</p>
            <p>       Create the Axway <span>Central Governance</span> Demonstration Root Certificate.</p>
         </td>
         <td>CFTCGPKI         </td>
      </tr>
      <tr>
         <td>16         </td>
         <td>
            <p>If cgenable=yes:</p>
            <p>         Transfer CFT to <span>Central Governance</span> registration.                           </p>
         </td>
         <td>CFTCGREG         </td>
      </tr>
      <tr>
         <td colspan="2">   Sentinel         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>20         </td>
         <td>If snenable = yes:            <p>         Sentinel parameters are activated (TCP configuration). </p>            <p>&amp;&amp;&amp; ïïï ùùù</p>         </td>
         <td>SN05CONF         </td>
      </tr>
      <tr>
         <td>25         </td>
         <td>
            <p>If sntlgcre = yes:</p>
            <p> Delete /define log stream – DASDONLY.</p>
         </td>
         <td>SN10CLGR         </td>
      </tr>
      <tr>
         <td colspan="2">   Copilot         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>30         </td>
         <td>
            <p>If copenable=yes:</p>
            <p>Copilot files are transferred in the USS environment (HFS/ZFS). </p>
         </td>
         <td>COPA010         </td>
      </tr>
      <tr>
         <td>31         </td>
         <td>
            <p> If copenable=yes:</p>
            <p>Updates Copilot UCONF parameters.</p>
         </td>
         <td>COPA020         </td>
      </tr>
      <tr>
         <td>32         </td>
         <td>REST API configuration.         </td>
         <td>RESTCFG         </td>
      </tr>
      <tr>
         <td colspan="2">   Secure Relay         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>40         </td>
         <td>
            <p> If Secure Relay is enabled:</p>
            <p>         Install on USS environment, the files for Secure Relay Master Agent.</p>
         </td>
         <td>XSRA010         </td>
      </tr>
      <tr>
         <td>41         </td>
         <td>
            <p>If Secure Relay enabled:</p>
            <p>         Create the runtime directory for the Transfer CFT          Secure Relay Master Agent.</p>
         </td>
         <td>XSRA015         </td>
      </tr>
      <tr>
         <td>42         </td>
         <td>
            <p>If Secure Relay is enabled:</p>
            <p>         Updating Secure Relay parameters (UCONF)</p>
         </td>
         <td>XSRA020         </td>
      </tr>
      <tr>
         <td>45         </td>
         <td>Configure SAML.         </td>
         <td>CFTSAML         </td>
      </tr>
      <tr>
         <td colspan="2">   Optional steps         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>50         </td>
         <td>
            <p>Exits and API(s) samples compilation (ASM, C and COBOL).</p>
            <p>      For COBOL, C: variable LNGPRFX must be customized (I91APICP).</p>
         </td>
         <td>I91APICP         </td>
      </tr>
      <tr>
         <td>51         </td>
         <td>API(s) link-edit.         </td>
         <td>I92APILK         </td>
      </tr>
      <tr>
         <td>52         </td>
         <td>Exits (ASM, C, and COBOL) link-edit.         </td>
         <td>LINKEXLE         </td>
      </tr>
      <tr>
         <td>60         </td>
         <td>Activate the Transfer CFT heartbeat.         </td>
         <td>CFTHEART         </td>
      </tr>
   </tbody>
</table>
