{
    "title": "Example silent installation files: SecureTransport Server with MariaDB database on Windows ",
    "linkTitle": "Example silent installation files: SecureTransport Server with MariaDB database ",
    "weight": "130"
}This topic shows examples of silent installation files for {{< SecureTransport/componentshortname  >}} 5.5 with MariaDB database on Windows:

-   Axway Installer configuration file: `Install_Axway_Installer_V4.10.13.properties`
-   SecureTransport silent installation configuration file: `Install_SecureTransport_V5.5.properties`

## Install\_Axway\_Installer\_V4.10.13.properties

The following example provides and example of the Axway Installer configuration file:



    Component = Axway_Installer
    Component.ComponentType = ComponentPack
    Component.SourceDiskNumber = 1
    Component.Parent =
    Component.Version = 4.10.13
    Component.LongName = Axway
     
    CreationDate = 27-10-2009 11:23
    CreationDate.Type = Date
    CreationDate.Format = dd-MM-yyyy HH:mm
     
    IntegrationDir = Axway_Installer_V4.10.13
    IntegrationDir.Type = Directory
     
    LevelOfExpertise = 1
    LevelOfExpertise.Level = 3
    LevelOfExpertise.Show = true
     
    InstallMode = Standard
    DVDLocation =
    DocumentationIndexRelativePath = Installer_4.5.x_InstallationPrerequisitesGuide_allOS_en/index.htm
     
    InstMode = Install
    InstMode.Default = Install
     
    AxwaySupportURL = https://support.axway.com/
     
    InstallDir = C:\\Axway\\
     
    InstallationLogicalName = SecureTransport1
     
    AllAxwayComps32 = false
    AllAxwayComps64 = true
     
    IncludeFiles =
    IncludeFiles.SecureTransport = Install_SecureTransport_V5.5.properties

## Install\_SecureTransport\_V5.5.properties

The following example provides and example of the SecureTransport silent installation configuration file:



    Component = SecureTransport
    Component.SupportedOS = aix-power-64;linux-x86-64;win-x86-64
    Component.SourceDiskNumber = 1
    Component.Parent = Axway_Installer
    Component.Implementation = Java
    Component.Version = 5.5
    Component.ConfigureMode = false
    Component.RootUser = Indifferent
    Component.ComponentType = ComponentPack
    Component.FileIdent = ST
    Component.PreferredJavaVersion = 11
    Component.AllowSpaceInDirectoryName = true
    Component.InstallerVersion = 4.10.13
    Component.MinorVersion = 20211028
    Component.LimitedCluster = NoCluster
    Component.LongName = Axway SecureTransport
    Component.JavaHome = C:\\Axway\\Java\\win-x86\\jre11_u11.0.12_7_64
     
    CreationDate = 27-10-2021 19:07
    CreationDate.Type = Date
    CreationDate.Format = dd-MM-yyyy HH:mm
     
    IntegrationDir = SecureTransport_V5.5
    IntegrationDir.Type = Directory
     
    mssqlPassword =
    mssqlPassword.Format = AES128
     
    oraclePassword =
    oraclePassword.Format = AES128
     
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
     
    InstallDir = C:\\Axway\\SecureTransport\\
     
    userName = root
    isNonRootInstall = false
     
    dbType = useDBLocal
     
    internalDBPort = 33060
    internalDBPort.Type = IPPortOwner
    internalDBPort.Max = 65535
    internalDBPort.Min = 1024
     
    internalDBUseSecureConnection = true
    internalDBAutoGenerateCertificates = true
    internalDBCaPath =
    internalDBServerKeyPath =
    internalDBServerCertPath =
    externalDBUseExistingSchema = false
    externalDBUseSecureConnection = false
     
    sslAdminPort = 444
    sslAdminPort.Type = Integer
     
    tomcatShutdownPort = 8005
    tomcatShutdownPort.Type = Integer
     
    enableLogRotation = true
    SecretFilePath =

 

 
