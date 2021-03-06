---
title: MSReportServer_ConfigurationSetting 成员 | Microsoft Docs
ms.date: 03/20/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: wmi-provider-library-reference
ms.topic: conceptual
apiname:
- MSReportServer_ConfigurationSetting Members
apilocation:
- reportingservices.mof
apitype: MOFDef
helpviewer_keywords:
- WMI provider [Reporting Services], MSReportServer_ConfigurationSetting class
- MSReportServer_ConfigurationSetting class
ms.assetid: 5e21a53a-a2f8-4b35-a8d9-5483519e3857
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ae51a72f0dc2be73e4175c9e50d03246d5d3b49d
ms.sourcegitcommit: 8ffc23126609b1cbe2f6820f9a823c5850205372
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81632518"
---
# <a name="msreportserver_configurationsetting-members"></a>MSReportServer_ConfigurationSetting 成员
  MSReportServer_ConfigurationSetting 类包含以下属性和方法。  
  
## <a name="public-properties"></a>公共属性  
  
|||  
|-|-|  
|[ConnectionPoolSize](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-connectionpoolsize.md)|返回连接池大小，报表服务器用来与托管报表服务器数据库的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] 实例进行通信。 只读。|  
|[DatabaseLogonAccount](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-databaselogonaccount.md)|指定报表服务器连接到承载报表服务器数据库的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] 实例时使用的登录帐户。 只读。|  
|[DatabaseLogonTimeout](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-databaselogontimeout.md)|指定尝试登录到报表服务器数据库失败前等待的秒数。 只读。|  
|[DatabaseLogonType](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-databaselogontype.md)|指定报表服务器是使用 Windows 服务帐户、Windows 用户帐户还是 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名访问报表服务器数据库。 只读。|  
|[DatabaseName](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-databasename.md)|指定承载报表服务器数据库的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的名称。|  
|[DatabaseQueryTimeout](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-databasequerytimeout.md)|指定命令失败或超时之前必须等待的秒数。报表服务器会根据报表服务器数据库对进程进行计时，而不会根据报表的数据源计时。|  
|[DatabaseServerName](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-databaseservername.md)|指定用来安装报表服务器数据库的服务器的名称。|  
|[InstallationID 属性](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-installationid.md)|返回特定报表服务器实例的唯一标识符。|  
|[InstanceName](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-instancename.md)|指定特定计算机上报表服务器实例的名称。|  
|[IsInitialized](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-isinitialized.md)|指示报表服务器实例是否已初始化。 只读。|  
|[IsSharePointIntegrated](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-issharepointintegrated.md)|指示报表服务器是否配置为 SharePoint 集成模式。|  
|[IsWebServiceEnabled](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-iswebserviceenabled.md)|指示是否已启用报表服务器 Web 服务。 只读。|  
|[IsWindowsServiceEnabled](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-iswindowsserviceenabled.md)|指示是否已启用报表服务器 Windows 服务。 只读。|  
|[MachineAccountIdentity 属性 (WMI)](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-machineaccountidentity.md)|获取安装了报表服务器的计算机的计算机帐户标识。|  
|[PathName](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-pathname.md)|指定报表服务器实例的安装路径。|  
|[SecureConnectionLevel](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-secureconnectionlevel.md)|返回 RSReportServer.config 文件中指定的安全连接级别。|  
|[SenderEmailAddress](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-senderemailaddress.md)|从报表服务器获取用于发送电子邮件的地址。 只读。|  
|[SendUsingSMTPServer](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-sendusingsmtpserver.md)|指定电子邮件配置中 SendUsing 属性是否设置为 TRUE。|  
|[SMTPServer](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-smtpserver.md)|从 RSReportServer.config 文件中获取 SMTP 服务器属性。 只读。|  
|[UnattendedExecutionAccount](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-unattendedexecutionaccount.md)|指定以无人参与方式运行报表时报表服务器将模拟的登录用户帐户。 只读。|  
|[版本](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-version.md)|返回报表服务器的版本。|  
|[VirtualDirectoryReportManager 属性 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-virtualdirectoryreportmanager.md)|返回报表管理器应用程序的虚拟目录。|  
|[VirtualDirectoryReportServer 属性 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-virtualdirectoryreportserver.md)|返回报表服务器 Web 服务应用程序的虚拟目录。|  
|[WindowsServiceIdentityActual](../../reporting-services/wmi-provider-library-reference/configurationsetting-property-windowsserviceidentityactual.md)|返回报表服务器 Windows 服务运行时实际使用的标识。 只读。|  
|[WindowsServiceIdentityConfigured](../../reporting-services/wmi-provider-library-reference/windowsserviceidentityconfigured-property.md)|返回在上次配置报表服务器 Windows 服务时所指定的运行时要使用的标识。 只读。|  
  
## <a name="public-methods"></a>公共方法  
  
|||  
|-|-|  
|[BackupEncryptionKey](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-backupencryptionkey.md)|备份实例的加密密钥。 加密密钥会在使用密码加密后存储。|  
|[CreateSSLCertificateBinding 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-createsslcertificatebinding.md)|创建 TLS/SSL 证书绑定。|  
|[DeleteEncryptedInformation](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-deleteencryptedinformation.md)|从报表服务器数据库删除加密信息。|  
|[DeleteEncryptionKey](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-deleteencryptionkey.md)|从报表服务器数据库删除加密密钥。|  
|[GenerateDatabaseCreationScript](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-generatedatabasecreationscript.md)|生成可用于创建报表服务器数据库的 SQL 脚本。|  
|[GenerateDatabaseRightsScript](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-generatedatabaserightsscript.md)|生成可用来向用户授予报表服务器数据库权限的 SQL 脚本。|  
|[GenerateDatabaseUpgradeScript](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-generatedatabaseupgradescript.md)|生成可用于升级报表服务器数据库的 SQL 脚本。|  
|[GetAdminSiteUrl 方法 (WMI)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-getadminsiteurl.md)|获取管理中心网站的绝对 URL。|  
|[GetDatabaseVersionDisplayName](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-getdatabaseversiondisplayname.md)|获取给定报表服务器数据库版本字符串的显示名称。|  
|[InitializeReportServer](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-initializereportserver.md)|初始化指定报表服务器实例。|  
|[ListInstalledSharePointVersions 方法 (WMI)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-listinstalledsharepointversions.md)|返回一组标记，表示与报表服务器安装在同一台计算机上的 [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] 或 [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] 版本。|  
|[ListIPAddresses 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-listipaddresses.md)|列出计算机的 IP 地址。|  
|[ListReportServersInDatabase](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-listreportserversindatabase.md)|返回报表服务器数据库中存在的报表服务器安装列表，无论这些安装是否具有访问安全信息的权限。|  
|[ListReservedURLs 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-listreservedurls.md)|列出为报表服务器上所有应用程序保留的 URL。|  
|[ListSSLCertificateBindings 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-listsslcertificatebindings.md)|列出 HTTP.SYS 中存在的以及 rsreportserver.config 中应有的 TLS/SSL 证书绑定。|  
|[ListSSLCertificates 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-listsslcertificates.md)|列出计算机上安装的 TLS/SSL 证书。|  
|[ReencryptSecureInformation](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-reencryptsecureinformation.md)|生成新的加密密钥，并使用新密钥对报表服务器数据库中的所有安全信息进行重新加密。|  
|[RemoveSSLCertificateBindings 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-removesslcertificatebinding.md)|删除 TLS/SSL 证书绑定。|  
|[RemoveUnattendedExecutionAccount](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-removeunattendedexecutionaccount.md)|从报表服务器配置中删除无人参与的执行帐户条目。|  
|[RemoveURL 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-removeurl.md)|删除为报表服务器保留的 URL。|  
|[ReserveURL 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-reserveurl.md)|为给定的应用程序添加一个 URL 预留。|  
|[RestoreEncryptionKey](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-restoreencryptionkey.md)|将指定的加密密钥重新应用于报表服务器数据库。|  
|[SetDatabaseConnection](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setdatabaseconnection.md)|设置与特定报表服务器数据库的报表服务器数据库连接。|  
|[SetDatabaseLogonTimeout](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setdatabaselogontimeout.md)|为报表服务器数据库登录尝试指定默认超时值。|  
|[SetDatabaseQueryTimeout](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setdatabasequerytimeout.md)|为报表服务器数据库连接指定默认超时值。|  
|[SetEmailConfiguration](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setemailconfiguration.md)|配置报表服务器用来发送电子邮件的电子邮件传递扩展插件。|  
|[SetSecureConnectionLevel](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setsecureconnectionlevel.md)|设置报表服务器的安全连接级别。|  
|[SetServiceState](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setservicestate.md)|打开和关闭报表服务器 Windows 服务和 Web 服务。|  
|[SetUnattendedExecutionAccount](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setunattendedexecutionaccount.md)|指定用于以无人参与方式运行报表的帐户。|  
|[SetVirtualDirectory 方法 (WMI MSReportServer_ConfigurationSetting)](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setvirtualdirectory.md)|设置应用程序的虚拟目录。|  
|[SetWindowsServiceIdentity](../../reporting-services/wmi-provider-library-reference/configurationsetting-method-setwindowsserviceidentity.md)|将报表服务器 Windows 服务作为指定的 Windows 用户运行，并授予此帐户足够的文件系统权限以允许操作报表服务器。|  
  
## <a name="see-also"></a>另请参阅  
 [MSReportServer_ConfigurationSetting 类](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-class.md)  
  
  
