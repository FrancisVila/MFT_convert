{
    "title": "Retain or recreate",
    "linkTitle": "Retain or recreate",
    "weight": "80"
}## Files you can copy

During the upgrade procedure, you can copy the following files, if they exist, from a previous version of Gateway:

From `run_time/data/` :

-   Character conversion tables: `table.trn`, `ascii.trn`, `ebcdic.trn`, `iso.trn`, `user1.trn`, `user2.trn`, `oempc.trn `
-   Security tables: `tablex25.adr`, `tableip.adr`
-   Statistics dictionary: `statdic.dat`
-   Mailbox file: `xferb.dat`

From` run_time/etc/`
:

-   Files: `tcpoport.ini`

## Files to regenerate

You **cannot** copy the following files from a previous version - you must regenerate them:

From `run_time/data/`

-   Log file: `log.dat`
-   Mailbox file: `xfer.dat`
-   Context files: \*`ctx.dat`
-   Database files: `admin.dat, cert.dat, cgate.dat, cgategroup.dat, dlist.dat, key.dat, nprof.dat, prof.dat, profile.dat, proxy.dat, ruledec.dat, ruletab.dat, rules.dat, sprof.dat, sshprof.dat, stat.dat, user.dat `

From `run_time/etc/`

-   Configuration file: `conffile`
-   Environment file: `profile `or `profile.bat`

## User exits

User exits (exits from protocol connections) must be recompiled, and their links regenerated in the {{< Gateway/gatewayname  >}} 6.17 environment. For more information, refer to <a href="../../migrating_to_6.17#Migrate_exits" class="MCXref xref">Step 5: upgrade exits</a>.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
