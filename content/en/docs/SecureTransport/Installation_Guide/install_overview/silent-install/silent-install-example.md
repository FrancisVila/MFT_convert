{
    "title": "Silent installation  example file",
    "linkTitle": "Silent installation  example file",
    "weight": "120"
}This subsection contains example configuration files used in SecureTransport silent installation:

-   Axway Installer configuration file: `Install_Axway_Installer_V4.10.0.properties`
-   SecureTransport silent installation configuration file: `Install_SecureTransport_V5.5.properties`

## Install\_Axway\_Installer\_V4.10.0.properties

The following example provides and example of the Axway Installer configuration file:

    Component = Axway_Installer

    Component.ComponentType = ComponentPack

    Component.Parent =

    Component.Version = 4.10.0

    Component.SourceDiskNumber = 1

    Component.LongName = Axway

    DocumentationIndexRelativePath =

    Installer_4.10.x_InstallationPrerequisitesGuide_allOS_en/index.htm

    AxwaySupportURL = https://support.axway.com/

    IntegrationDir = Axway_Installer_V4.10.0

    IntegrationDir.Type = Directory

    InstMode = Install

    InstMode.Default = Install

    CreationDate = 27-10-2009 11:23

    CreationDate.Type = Date

    CreationDate.Format = dd-MM-yyyy HH:mm

    InstallMode = Standard

    DVDLocation =

    LevelOfExpertise = 1

    LevelOfExpertise.Show = true

    LevelOfExpertise.Level = 3

    InstallDir = /opt/TMWD/Axway

    InstallationLogicalName = SecureTransport01

    AllAxwayComps32 = false

    AllAxwayComps64 = true

    IncludeFiles =

    IncludeFiles.SecureTransport = Install_SecureTransport_V5.5.properties

## Install\_SecureTransport\_V5.5.properties

The following example provides and example of the SecureTransport silent installation configuration file:

    Component = SecureTransport

    Component.LongName = Axway SecureTransport

    Component.Version = 5.5

    Component.Parent = Axway_Installer

    Component.ComponentType = ComponentPack

    Component.FileIdent = ST

    Component.SupportedOS = aix-power-64;linux-x86-64;win-x86-64

    Component.SourceDiskNumber = 1

    Component.InstallerVersion = 4.10.0

    Component.AllowSpaceInDirectoryName = true

    Component.RootUser = Mandatory

    Component.LimitedCluster = NoCluster

    Component.ConfigureMode = false

    Component.Implementation = Java

    Component.PreferredJavaVersion = 8

    CreationDate = 28-06-2013 11:33

    CreationDate.Type = Date

    CreationDate.Format = dd-MM-yyyy HH:mm

    IntegrationDir = SecureTransport_V5.5

    IntegrationDir.Type = Directory

    SelectedBitArchitecture = 64

    InstMode = Install

    SecureTransport = true

    SecureTransport.Type = Module

    SecureTransport.ModuleType = Installed

    SecureTransport.LogicalName = SecureTransport

    SecureTransport.ParentName = null

    SecureTransport.Title = Axway SecureTransport V5.5

    Server = true

    Server.Type = Module

    Server.ModuleType = Installed

    Server.LogicalName = Server

    Server.ParentName = SecureTransport

    Server.Title = Server

    Edge = false

    Edge.Type = Module

    Edge.ModuleType = NotInstalled

    Edge.LogicalName = Edge

    Edge.ParentName = SecureTransport

    Edge.Title = Edge

    InstallDir = /opt/TMWD/SecureTransport

    isNonRootInstall = false

    userName = root

    dbType = useDBLocal

    internalDBPort = 33060

    internalDBPort.Type = IPPortOwner

    internalDBPort.Max = 65535

    internalDBPort.Min = 1024

    sslAdminPort = 444

    sslAdminPort.Type = Integer

    tomcatShutdownPort = 8005

    tomcatShutdownPort.Type = Integer

    enableLogRotation = true

    SecretFilePath = /opt/TMWD/install//secret

 

 
