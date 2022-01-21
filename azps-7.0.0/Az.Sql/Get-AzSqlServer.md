---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: C39ACCAC-2BFF-48D0-95EA-D5B402D74D46
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServer.md
ms.openlocfilehash: 817d19208a1d136697b1488227e4ac57bffa99c3
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136573227"
---
# Get-AzSqlServer

## SYNOPSIS
Mengembalikan informasi tentang SQL Database server.

## SYNTAX

```
Get-AzSqlServer [[-ResourceGroupName] <String>] [[-ServerName] <String>] [-ExpandActiveDirectoryAdministrator]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlServer** mengembalikan informasi tentang satu atau beberapa Azure SQL Database lain.
Tentukan nama server untuk melihat informasi hanya untuk server itu.

## EXAMPLES

### Contoh 1: Dapatkan semua contoh SQL Server ditetapkan ke grup sumber daya
```
PS C:\>Get-AzSqlServer -ResourceGroupName "ResourceGroup01"
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net

ResourceGroupName        : resourcegroup01
ServerName               : server02
Location                 : West US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server02.database.windows.net
```

Perintah ini mendapatkan informasi tentang semua Azure SQL Database sumber daya yang ditetapkan ke grup sumber daya ResourceGroup01.

### Contoh 2: Mendapatkan informasi tentang server Azure SQL Database
```
PS C:\>Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01"
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net
```

Perintah ini mendapatkan informasi tentang server Azure SQL Database bernama Server01.

### Contoh 3: Mendapatkan semua SQL Server anda dalam langganan
```
PS C:\>Get-AzResourceGroup | Get-AzSqlServer
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net

ResourceGroupName        : resourcegroup01
ServerName               : server02
Location                 : West US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server02.database.windows.net

ResourceGroupName        : resourcegroup02
ServerName               : server03
Location                 : East US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server03.database.windows.net
```

Perintah ini mendapatkan informasi tentang semua Azure SQL Database pelanggan dalam langganan saat ini.

### Contoh 4: Dapatkan semua contoh SQL Server ditetapkan ke grup sumber daya menggunakan pemfilteran
```
PS C:\>Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "server*"
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net

ResourceGroupName        : resourcegroup01
ServerName               : server02
Location                 : West US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server02.database.windows.net
```

Perintah ini mendapatkan informasi tentang semua Azure SQL Database sumber daya yang ditetapkan ke grup sumber daya ResourceGroup01 yang dimulai dengan "server".

### Contoh 5: Dapatkan semua contoh SQL Server ditetapkan ke grup sumber daya dengan informasi administrator eksternal
```
PS C:\>$val = Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ExpandActiveDirectoryAdministrator
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net
Administrators           : Microsoft.Azure.Management.Sql.Models.ServerExternalAdministrator

ResourceGroupName        : resourcegroup01
ServerName               : server02
Location                 : West US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server02.database.windows.net
Administrators           : Microsoft.Azure.Management.Sql.Models.ServerExternalAdministrator

PS C:\>$val.Administrators
AdministratorType         : ActiveDirectory
PrincipalType             : Group
Login                     : Dummy
Sid                       : df7667b8-f9fd-4029-a0e3-b43c75ce9538
TenantId                  : f553829b-6d84-481b-86a9-42db57c1dc73
AzureADOnlyAuthentication : True

AdministratorType         : ActiveDirectory
PrincipalType             : Group
Login                     : Dummy2
Sid                       : df7667b8-f9fd-4029-a0e3-b43c75ce9538
TenantId                  : f553829b-6d84-481b-86a9-42db57c1dc73
AzureADOnlyAuthentication : True
```

Perintah ini mendapatkan informasi tentang semua Azure SQL Database sumber daya yang ditetapkan ke grup sumber daya ResourceGroup01.

### Contoh 6: Mendapatkan informasi tentang server Azure SQL Database dengan informasi administrator eksternal
```
PS C:\>$val = Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ExpandActiveDirectoryAdministrator
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net
Administrators           : Microsoft.Azure.Management.Sql.Models.ServerExternalAdministrator

PS C:\>$val.Administrators
AdministratorType         : ActiveDirectory
PrincipalType             : Group
Login                     : Dummy
Sid                       : df7667b8-f9fd-4029-a0e3-b43c75ce9538
TenantId                  : f553829b-6d84-481b-86a9-42db57c1dc73
AzureADOnlyAuthentication : True
```

Perintah ini mendapatkan informasi tentang server Azure SQL Database bernama Server01.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpandActiveDirectoryAdministrator
Memperluas Informasi Administrator Direktori Aktif di server.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk server yang ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ServerName
Menentukan nama server yang akan dapatkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel

## CATATAN

## RELATED LINKS

[New-AzSqlServer](./New-AzSqlServer.md)

[Remove-AzSqlServer](./Remove-AzSqlServer.md)

[Set-AzSqlServer](./Set-AzSqlServer.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)


