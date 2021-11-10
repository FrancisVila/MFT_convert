{
    "title": "Example silent installation files: SecureTransport Server with Oracle database  on a Linux cluster",
    "linkTitle": "Example silent installation files: SecureTransport Server with Oracle database ",
    "weight": "140"
}This topic shows examples of silent installation files for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server with an external Oracle database on a Linux cluster:

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
     
    InstallDir = /root/Axway/
    InstallationLogicalName = SecureTransport2
     
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
    Component.MinorVersion = 20211125
    Component.LimitedCluster = NoCluster
    Component.LongName = Axway SecureTransport
    Component.JavaHome = /root/Axway/Java/linux-x86/jre11_u11.0.12_7_64
     
    CreationDate = 09-11-2021 11:58
    CreationDate.Type = Date
    CreationDate.Format = dd-MM-yyyy HH:mm
     
    IntegrationDir = SecureTransport_V5.5
    IntegrationDir.Type = Directory
     
    mssqlPassword =
    mssqlPassword.Format = AES128
     
    oraclePassword = YourEncryptedPassword
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
     
    ServerDocker = false
    ServerDocker.Type = Module
    ServerDocker.ModuleType = NotInstalled
    ServerDocker.LogicalName = ServerDocker
    ServerDocker.ParentName = SecureTransport
    ServerDocker.Title = ServerDocker
     
    EdgeDocker = false
    EdgeDocker.Type = Module
    EdgeDocker.ModuleType = NotInstalled
    EdgeDocker.LogicalName = EdgeDocker
    EdgeDocker.ParentName = SecureTransport
    EdgeDocker.Title = EdgeDocker
     
    InstallDir = /root/Axway/SecureTransport/
     
    userName = root
     
    isNonRootInstall = false
     
    dbType = useOracleExternal
     
    oracleHost = 10.222.2.22
    oracleHost.Type = HostName
     
    oraclePort = 1521
    oraclePort.Type = Integer
     
    oracleUserName = gblagovwin
     
    oracleServiceName = oracle19c
     
    oracleUseExistingSchema = true
     
    oracleUseSecureConnection = false
     
    oracleCertificateDN =
    OracleTrustStoreFilePath =
     
    oracleKerberosMode = false
    oracleUseKerberosFile = false
    OracleKrbConfPath =
    OracleKrbCachePath =
     
    oracleUseProxy = false
     
    oracleProxyUser =
     
    externalDBTrustStore =
     
    oracleTlsVersion =
     
    externalDBUseExistingSchema = true
    externalDBUseSecureConnection = false
     
    sslAdminPort =
     
    tomcatShutdownPort =
     
    enableLogRotation = true
     
    SecretFilePath = /opt/taeh
    SecretFilePath.Type = File
     
    clusterNodeValue = 10.164.64.64

 

 
