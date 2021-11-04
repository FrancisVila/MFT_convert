{
    "title": "UCONF: General unified configuration parameters",
    "linkTitle": "General configuration parameters",
    "weight": "280"
}Unified configuration, or UCONF, settings and default values are listed in tables
and grouped into the following categories:

-   [Identifier parameters](#Identifi)
-   [Instance
    parameters](#Instance)
-   [Packaging parameters](#Packagin)
-   [Work environment
    parameters](#Work)
-   [Common parameters](#Common)
-   [Trace parameters](#Trace)
-   [<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
    probe configuration](#Transfer2)
-   [Add a character set: transcoding](#Add)
-   [Accounting records](#Statisti)
-   [Compatibility](#Compatib)
-   [Deactivate the default IDF](#Deactivate_idf)

<span id="Identifi"></span>

## Identifier parameters

<table>
   <th>
      <tr>
<th>UCONF         </th>
<th>Default         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.uconf.default_fname </p>         </td>
         <td><p>$(cft.install_dir)/distrib/conf/cftuconf-common.dat
 </p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.instance_fname  </p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftuconf.dat  </p>         </td>
      </tr>
      <tr>
         <td>cft.uconf.runtime_fname         </td>
         <td>$(cft.runtime_dir)/data/cftuconf-run.dat         </td>
      </tr>
   </tbody>
</table>

<span id="Instance"></span>

## Instance parameters

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Default         </th>
<th>Former value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.runtime_dir</p>         </td>
         <td><p>(dir)</p>         </td>
         <td><p> $(CFTDIRRUNTIME)</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install_dir</p>         </td>
         <td><p>(dir)</p>         </td>
         <td><p> $(CFTDIRINSTALL)</p>         </td>
      </tr>
      <tr>
         <td><p>cft.working_dir</p>         </td>
         <td><p>(dir)</p>         </td>
         <td><p>$(cft.runtime_dir)</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.common_fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p> $(cft.install_dir)/distrib/conf/cftuconf-common.ini</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.system_fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.install_dir)/distrib/conf/cftuconf-system.ini</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.msg</p>         </td>
         <td><p> </p>         </td>
         <td><p>New</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.pid</p>         </td>
         <td><p>38016</p>         </td>
         <td><p>New</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.progress</p>         </td>
         <td><p>100</p>         </td>
         <td><p>New</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.state</p>         </td>
         <td><p>RUNNING</p>         </td>
         <td><p>New</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.client_socket</p>         </td>
         <td><p>740</p>         </td>
         <td><p>New</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.manager_pid </p>         </td>
         <td><p>44920</p>         </td>
         <td><p>New</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.notification_port  </p>         </td>
         <td><p>2953</p>         </td>
         <td><p>New</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Packagin"></span>

## Packaging parameters

The following table lists the UCONF identifiers, default values, and former Windows and UNIX file values.

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Default         </th>
<th>Windows         </th>
<th>UNIX         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.runtime_dir </p>         </td>
         <td><p>$(CFTDIRRUNTIME)  </p>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>cft.install_dir </p>         </td>
         <td><p>$(CFTDIRINSTALL)  </p>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>cft.synchrony_dir         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.fname</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftcata  </p>         </td>
         <td><p>$CFTCATA(cft.ini) </p>         </td>
         <td><p>_CFTCATA </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.default_size </p>         </td>
         <td><p>10000  </p>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom.default_size </p>         </td>
         <td><p>1000  </p>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.fname </p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftparm </p>         </td>
         <td><p>$CFTPARM  </p>         </td>
         <td><p>_CFTPARM  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.partfname </p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftpart </p>         </td>
         <td><p>$CFTPART  </p>         </td>
         <td><p>_CFTPART  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.pkifname </p>         </td>
         <td><p>$(cft.runtime_dir)/conf/pki/pkibase  </p>         </td>
         <td><p>$CFTPKU </p>         </td>
         <td><p>_CFTPKU  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.habfname  </p>         </td>
         <td><p>$(cft.runtime_dir)/sec.ini  </p>         </td>
         <td><p>$CFTHINI  </p>         </td>
         <td><p>_CFTHINI  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.secparm </p>         </td>
         <td><p>$(cft.runtime_dir)/data/secparm  </p>         </td>
         <td><p>$CFTHPARM  </p>         </td>
         <td><p>_CFTHPARM  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.keyfname </p>         </td>
         <td><p>$(cft.runtime_dir)/conf/cft.key  </p>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom.fname </p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftcom  </p>         </td>
         <td><p>$CFTCOM  </p>         </td>
         <td><p>_CFTCOM  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.fname </p>         </td>
         <td><p>$(cft.runtime_dir)/log/cftlog  </p>         </td>
         <td><p>$CFTLOG  </p>         </td>
         <td><p>_CFTLOG  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.afname &gt; </p>         </td>
         <td><p>$(cft.runtime_dir)/log/cftalog  </p>         </td>
         <td><p>$CFTALOG  </p>         </td>
         <td><p>_CFTALOG  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.fname </p>         </td>
         <td><p>$(cft.runtime_dir)/log/cftaccnt  </p>         </td>
         <td><p>$CFTACCNT  </p>         </td>
         <td><p>_CFTACNT  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.afname </p>         </td>
         <td><p>$(cft.runtime_dir)/accnt/cftaccnt  </p>         </td>
         <td><p>$CFTAACCN  </p>         </td>
         <td><p>_CFTACNTA  </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Work"></span>

## Work environment parameters

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.working_dir  </p>         </td>
         <td><p>$(cft.runtime_dir) </p>         </td>
         <td><p>Sets the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> work-environment </p>         </td>
      </tr>
      <tr>
         <td><p>cft.idparm </p>         </td>
         <td><p>IDPARM0  </p>         </td>
         <td><p>Sets the IDPARM to use in Copilot (GUI) and <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> (optional)  </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Common"></span>

## Common parameters

Values for ID where the type is Common.

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Default         </th>
<th>Former value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.uconf.shared_fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftuconf-shared.ini  </p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.shared_fname_bak</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.uconf.shared_fname).bak</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.instance_fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftuconf.ini</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.instance_fname_bak</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.uconf.instance_fname)_bak</p>         </td>
      </tr>
      <tr>
         <td>cft.uconf.runtime_fname         </td>
         <td>(fname)         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>cft.uconf.lock_fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/run/uconf.lck</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.lock_delay_ms</p>         </td>
         <td><p>(int)</p>         </td>
         <td><p>100</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.lock_retry</p>         </td>
         <td><p> (int)</p>         </td>
         <td><p>20</p>         </td>
      </tr>
      <tr>
         <td><p>cft.idparm </p>         </td>
         <td><p>(identifier)</p>         </td>
         <td><p>IDPARM0 New</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftcata Win:$CFTCATA(cft.ini) / Unix: _CFTCATA</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.default_size  </p>         </td>
         <td><p>(int)</p>         </td>
         <td><p>10000</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.fname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftparm Win:$CFTPARM(cft.ini) / Unix: _CFTPARM</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.partfname</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftpart Win:$CFTPART(cft.ini) / Unix: _CFTPART</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom.fname</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftcom Win:$CFTCOM(cft.ini) / Unix: _CFTCOM</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom.default_size</p>         </td>
         <td><p>(int)</p>         </td>
         <td><p>1000</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.fname </p>         </td>
         <td><p>fname</p>         </td>
         <td><p> $(cft.runtime_dir)/log/cftlog
Win:$CFTLOG(cft.ini) / Unix: _CFTLOG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.afname</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>$(cft.runtime_dir)/log/cftalog Win:$CFTALOG(cft.ini) / Unix: _CFTLOG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.fname </p>         </td>
         <td><p> fname</p>         </td>
         <td><p>$(cft.runtime_dir)/log/cftaccnt Win:$CFTACCNT(cft.ini) / Unix: _CFTACNT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.afname  </p>         </td>
         <td><p>fname</p>         </td>
         <td><p>$(cft.runtime_dir)/accnt/cftaccnt Win:$CFTAACCN(cft.ini) / Unix: _CFTACNTA</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.maxtrans</p>         </td>
         <td><p> (int)</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.delayed_update</p>         </td>
         <td><p> (int)</p>         </td>
         <td><p>1</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Trace"></span>

## Trace parameters

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Default         </th>
<th>Former value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>trace.xtrace.default_fname
  </p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>$(cft.runtime_dir)/traces/cft.trc New</p>         </td>
      </tr>
      <tr>
         <td><p>trace.xtrace.default_level</p>         </td>
         <td><p>(fname)</p>         </td>
         <td><p>New parameter</p>         </td>
      </tr>
      <tr>
         <td><p>trace.net.level</p>         </td>
         <td><p>(int)</p>         </td>
         <td><p>New parameter</p>         </td>
      </tr>
      <tr>
         <td><p>trace.file.level</p>         </td>
         <td><p>(int)</p>         </td>
         <td><p>New parameter</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer2"></span>

## <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> probe configuration

Use the following parameters to define <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> probes.

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.probes.history_size</p>         </td>
         <td><p>Number of samples kept in the memory for each time class</p>         </td>
      </tr>
      <tr>
         <td><p>cft.probes.time_classes</p>         </td>
         <td><p>Sorted list of time classes in milliseconds</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Add"></span>

## Add a character set: transcoding

<table>
   <th>
      <tr>
<th>ID         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.cft_charsets</p>         </td>
         <td><p>Add a character set id to the existing list of charsets.</p>
<p>The default charsets are:</p>
<ul>
<li>CFT_UTF-8</li>
<li>CFT_UTF-16</li>
<li>CFT_UTF-16LE</li>
<li>CFT_UTF-16BE</li>
<li>CFT_UTF-32</li>
<li>CFT_UTF-32LE</li>
<li>CFT_UTF-32BE</li>
<li>CFT_UCS-2</li>
<li>CFT_UCS-2LE</li>
<li>CFT_UCS-2BE</li>
<li>CFT_BIG5</li>
<li>CFT_CP850</li>
<li>CFT_ISO8859-1</li>
<li>CFT_ISO8859-15</li>
<li>CFT_EBCDIC-FR</li>
</ul>         </td>
      </tr>
      <tr>
         <td>cft.charsets.value.CUSTOM_CHARSET_ID.iconv_map         </td>
         <td><p>Customize the charset that you created.</p>         </td>
      </tr>
   </tbody>
</table>

## Start log and catalog parameters

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.startup.catalog         </td>
         <td>Yes         </td>
         <td>Display/hide catalog at start up.         </td>
      </tr>
      <tr>
         <td>copilot.startup.catalog.filter         </td>
         <td>Errors         </td>
         <td>Filter to use for the catalog display on start up.         </td>
      </tr>
      <tr>
         <td>copilot.startup.log         </td>
         <td>Yes         </td>
         <td>Display/hide log at start up.         </td>
      </tr>
      <tr>
         <td>copilot.startup.log.filter         </td>
         <td>None         </td>
         <td>Filter to use for the log display on start up.         </td>
      </tr>
      <tr>
         <td>cft.cftlog.switch_on_stop         </td>
         <td>No         </td>
         <td>Dictates if the switch log occurs at <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> server shutdown         </td>
      </tr>
   </tbody>
</table>

## Automatically expand the catalog

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.cftcat.auto_expand_percent         </td>
         <td>0         </td>
         <td><p>This value indicates the factor increase, as a percentage, that the catalog will automatically expand.</p>
<p>The value 0 disables the automatic expansion feature.</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Tip  </strong></span>         </td>
         <td>We recommend that you set this to a relatively high value, at least 50. When repeatedly expanded, the catalog's internal structure may become fragmented and, consequently, catalog access less efficient.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td>cft.cftcat.auto_expand_max_size         </td>
         <td>1M         </td>
         <td><p>The maximum number of records for the automatic catalog expansion option.</p>         </td>
      </tr>
   </tbody>
</table>

See also [Automatic catalog expansion](../../admin_monitoring_intro/auto_expand_catalog).

## Parallel transfers

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>uconf:cft.server.maxtrans         </td>
         <td>Modifies the number of parallel transfers. See <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/trantask">trantask</a>.         </td>
      </tr>
   </tbody>
</table>

## Retrieve subdirectories

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>uconf:cft.dirdepth=Yes         </td>
         <td>Enables retrieving subdirectories.         </td>
      </tr>
   </tbody>
</table>

## Synchronous connections

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>uconf: cft.server.cftcoms.max_connection         </td>
         <td>Defines the number of connections for CFTCOMS.         </td>
      </tr>
   </tbody>
</table>

## Purge

### Startup configuration

PURGE when starting <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is now configurable, with the following options:

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.purge.enable_on_start         </td>
         <td>Yes         </td>
         <td>Condition if the purge must be run on <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> startup.         </td>
      </tr>
      <tr>
         <td>cft.purge.background_on_start         </td>
         <td>Yes         </td>
         <td>Condition if the purge must be run on <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> startup.         </td>
      </tr>
      <tr>
         <td>cft.purge.quantity         </td>
         <td>10         </td>
         <td>Number of transfers to delete at once step (only for background).         </td>
      </tr>
      <tr>
         <td>cft.purge.periodicity         </td>
         <td>0         </td>
         <td>Amount of time between each automatic purge.         </td>
      </tr>
   </tbody>
</table>

### Dynamically purge catalog

These parameters modify the amount of time to keep transfers in catalog before purging, without directly modifying the CFTCAT object. For each parameter, enter an integer for the amount of time, optionally followed by the letter D, H, or M to indicate day, hour, or minute respectively. See the example section [Purging the catalog](../../admin_commands_intro/purge_catalog) for details. If you enter the default value, the value defined in CFTCAT configuration is used.

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.purge.rx         </td>
         <td>-1         </td>
         <td>requester state eXecuted         </td>
      </tr>
      <tr>
         <td>cft.purge.sx         </td>
         <td>-1         </td>
         <td>server state eXecuted         </td>
      </tr>
      <tr>
         <td>cft.purge.rt         </td>
         <td>-1         </td>
         <td>requester state Terminated         </td>
      </tr>
      <tr>
         <td>cft.purge.st         </td>
         <td>-1         </td>
         <td>server state Terminated         </td>
      </tr>
      <tr>
         <td>cft.purge.rh         </td>
         <td>-1         </td>
         <td>requester sate Hold         </td>
      </tr>
      <tr>
         <td>cft.purge.sh         </td>
         <td>-1         </td>
         <td>server state Hold         </td>
      </tr>
   </tbody>
</table>

See also, [Purging the catalog](../../admin_commands_intro/purge_catalog), Transfer states and [LISTCAT.](../../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/brief_catalog_listing)

## Customizable network sessions

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.server.max_session         </td>
         <td>0         </td>
         <td><p>Use this setting to overwrite the default maximum number of network sessions.</p>
<p>The default value 0 doubles the maxtrans value.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer"></span>

## Transfer requests

This parameter lets you use the SEND or RECV command without requiring an [IDF](../../../c_intro_userinterfaces/command_summary/parameter_intro/idf). This means that if you do not define a transfer file identifier, a default value (CFTPART IDF) is used. Exceptions:

-   For a SEND command the IDFDEF is used if  available, before searching for the CFTPART value.
-   For a RECV command with an asterisk "\*" the sender provides the IDF.

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.default_idf.enable         </td>
         <td>Yes         </td>
         <td><p>Possible values are:</p>
<ul>
<li>Yes: Indicates that a default file identifier is used when the transfer request IDF is not defined in a CFTRECV or CFTSEND command.</li>
<li>No: Disables the default IDF functionality of no required IDF.If you execute a command without an IDF or using an IDF that does not exist, or using the default IDF defined in CFTPARM (DEFAULT), the commands fails.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Statisti"></span>

## Accounting records

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.accnt.enable_extended_byte_fields         </td>
         <td>No         </td>
         <td><p>For each completed transfer, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can record the number of characters in the file (FBYTE) and the number of characters sent over the line (NBYTE).</p>
<p>Possible values are:</p>
<ul>
<li>No: The FBYTE and NBYTE fields are filled.</li>
<li>Yes: The FBYTE_EXTENDED and NBYTE_EXTENDED fields are filled (length=15), and FBYTE and NBYTE are empty (either 0 or blank depending on the CFTACCNT LANG parameter setting).</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Compatib"></span>

## Compatibility

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default value         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Uconf:cft.listcat_compat         </td>
         <td>No         </td>
         <td><p>Defines the LISTCAT display:</p>
<ul>
<li>Yes = Display using the former product format, which does not include the new columns. The format in LISTCAT is DTSA.</li>
<li>No= Display using the product version 3.0 and higher catalog format. The format in LISTCAT is DTSASPP.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Uconf:cft.state_compat         </td>
         <td>No         </td>
         <td><p>Defines the transfer states:</p>
<ul>
<li>Yes= The phase state is fully compatible with the states in versions prior to 3.0.</li>
<li>No = The state reflects the phase used in Transfer CFT 3.0 and higher. This uses phase instead of the former states, except during the Transfer phase, when the former state is the same as the phase step.</li>
</ul>
<p><span class="bold_in_para">Note</span>: Uconf:cft.state_compat also impacts the <a href="../../../concepts/phase_and_phasestep/ack_phase">acknowledgement</a> behavior if ackstate is set to ignore.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Deactivate_idf"></span>

## Deactivate the default IDF

You can deactivate the default use of the IDF value for the CFTSEND and CFTRECV commands.

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Type         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft.default_idf.enable         </td>
         <td>Yes         </td>
         <td><p>Bool</p>
<p>Yes / No</p>         </td>
         <td><p>Enable the default IDF to use when the transfer request IDF is not explicitly defined by a CFTRECV or CFTSEND command.</p>
<p>DIAGI=434</p>         </td>
      </tr>
   </tbody>
</table>