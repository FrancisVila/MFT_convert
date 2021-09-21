{
    "title": "Silent installation  example file",
    "linkTitle": "Silent installation  example file",
    "weight": "120"
}This subsection contains example configuration files used in SecureTransport silent installation:

-   Axway Installer configuration file: `Install_Axway_Installer_V4.10.0.properties`
-   SecureTransport silent installation configuration file: `Install_SecureTransport_V5.5.properties`

## Install\_Axway\_Installer\_V4.10.0.properties

The following example provides and example of the Axway Installer configuration file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>Component = Axway_Installer</pre><pre>Component.ComponentType = ComponentPack</pre><pre>Component.Parent =</pre><pre>Component.Version = 4.10.0</pre><pre>Component.SourceDiskNumber = 1</pre><pre>Component.LongName = Axway</pre><pre>DocumentationIndexRelativePath =</pre><pre>Installer_4.10.x_InstallationPrerequisitesGuide_allOS_en/index.htm</pre><pre>AxwaySupportURL = <a href="https://support.axway.com/">https://support.axway.com/</a></pre><pre>IntegrationDir = Axway_Installer_V4.10.0</pre><pre>IntegrationDir.Type = Directory</pre><pre>InstMode = Install</pre><pre>InstMode.Default = Install</pre><pre>CreationDate = 27-10-2009 11:23</pre><pre>CreationDate.Type = Date</pre><pre>CreationDate.Format = dd-MM-yyyy HH:mm</pre><pre>InstallMode = Standard</pre><pre>DVDLocation =</pre><pre>LevelOfExpertise = 1</pre><pre>LevelOfExpertise.Show = true</pre><pre>LevelOfExpertise.Level = 3</pre><pre>InstallDir = /opt/TMWD/Axway</pre><pre>InstallationLogicalName = SecureTransport01</pre><pre>AllAxwayComps32 = false</pre><pre>AllAxwayComps64 = true</pre><pre>IncludeFiles =</pre><pre>IncludeFiles.SecureTransport = Install_SecureTransport_V5.5.properties</pre>
         </td>
      </tr>
   </tbody>
</table>

## Install\_SecureTransport\_V5.5.properties

The following example provides and example of the SecureTransport silent installation configuration file:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>Component = SecureTransport</pre><pre>Component.LongName = Axway SecureTransport</pre><pre>Component.Version = 5.5</pre><pre>Component.Parent = Axway_Installer</pre><pre>Component.ComponentType = ComponentPack</pre><pre>Component.FileIdent = ST</pre><pre>Component.SupportedOS = aix-power-64;linux-x86-64;win-x86-64</pre><pre>Component.SourceDiskNumber = 1</pre><pre>Component.InstallerVersion = 4.10.0</pre><pre>Component.AllowSpaceInDirectoryName = true</pre><pre>Component.RootUser = Mandatory</pre><pre>Component.LimitedCluster = NoCluster</pre><pre>Component.ConfigureMode = false</pre><pre>Component.Implementation = Java</pre><pre>Component.PreferredJavaVersion = 8</pre><pre>CreationDate = 28-06-2013 11:33</pre><pre>CreationDate.Type = Date</pre><pre>CreationDate.Format = dd-MM-yyyy HH:mm</pre><pre>IntegrationDir = SecureTransport_V5.5</pre><pre>IntegrationDir.Type = Directory</pre><pre>SelectedBitArchitecture = 64</pre><pre>InstMode = Install</pre><pre>SecureTransport = true</pre><pre>SecureTransport.Type = Module</pre><pre>SecureTransport.ModuleType = Installed</pre><pre>SecureTransport.LogicalName = SecureTransport</pre><pre>SecureTransport.ParentName = null</pre><pre>SecureTransport.Title = Axway SecureTransport V5.5</pre><pre>Server = true</pre><pre>Server.Type = Module</pre><pre>Server.ModuleType = Installed</pre><pre>Server.LogicalName = Server</pre><pre>Server.ParentName = SecureTransport</pre><pre>Server.Title = Server</pre><pre>Edge = false</pre><pre>Edge.Type = Module</pre><pre>Edge.ModuleType = NotInstalled</pre><pre>Edge.LogicalName = Edge</pre><pre>Edge.ParentName = SecureTransport</pre><pre>Edge.Title = Edge</pre><pre>InstallDir = /opt/TMWD/SecureTransport</pre><pre>isNonRootInstall = false</pre><pre>userName = root</pre><pre xml:space="preserve">dbType = useDBLocal</pre><pre xml:space="preserve">internalDBPort = 33060</pre><pre>internalDBPort.Type = IPPortOwner</pre><pre>internalDBPort.Max = 65535</pre><pre>internalDBPort.Min = 1024</pre><pre>sslAdminPort = 444</pre><pre>sslAdminPort.Type = Integer</pre><pre>tomcatShutdownPort = 8005</pre><pre>tomcatShutdownPort.Type = Integer</pre><pre>enableLogRotation = true</pre><pre>SecretFilePath = /opt/TMWD/install//secret</pre>
         </td>
      </tr>
   </tbody>
</table>

 

 
