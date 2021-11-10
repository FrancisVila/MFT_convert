{
    "title": "Retain or recreate",
    "linkTitle": "Retain or recreate",
    "weight": "80"
}## Files you can copy

During the upgrade procedure, you can copy the following files, if they exist, from a previous version of Gateway:

From <span class="code">run\_time/data/</span> :

-   Character conversion tables: <span class="code">table.trn</span>, <span class="code">ascii.trn</span>, <span class="code">ebcdic.trn</span>, <span class="code">iso.trn</span>, <span class="code">user1.trn</span>, <span class="code">user2.trn</span>, <span class="code">oempc.trn </span>
-   Security tables: <span class="code">tablex25.adr</span>, <span class="code">tableip.adr
    </span>
-   Statistics dictionary: <span class="code">statdic.dat
    </span>
-   Mailbox file: <span class="code">xferb.dat
    </span>

From<span class="code"> run\_time/etc/</span>
:

-   Files: <span class="code">tcpoport.ini</span>

## Files to regenerate

You **cannot** copy the following files from a previous version - you must regenerate them:

From <span class="code">run\_time/data/</span>

-   Log file: <span class="code">log.dat
    </span>
-   Mailbox file: <span class="code">xfer.dat
    </span>
-   Context files: \*<span class="code">ctx.dat
    </span>
-   Database files: <span class="code">admin.dat, cert.dat, cgate.dat, cgategroup.dat, dlist.dat, key.dat, nprof.dat, prof.dat, profile.dat, proxy.dat, ruledec.dat, ruletab.dat, rules.dat, sprof.dat, sshprof.dat, stat.dat, user.dat </span>

From <span class="code">run\_time/etc/
</span>

-   Configuration file: <span class="code">conffile
    </span>
-   Environment file: <span class="code">profile </span>or <span class="code">profile.bat
    </span>

## User exits

User exits (exits from protocol connections) must be recompiled, and their links regenerated in the <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> 6.17 environment. For more information, refer to <a href="../../migrating_to_6.17#Migrate_exits" class="MCXref xref">Step 5: upgrade exits</a>.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
