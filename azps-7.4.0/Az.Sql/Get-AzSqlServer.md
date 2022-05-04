---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: C39ACCAC-2BFF-48D0-95EA-D5B402D74D46
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServer.md
ms.openlocfilehash: 2216b993a2f9ddb5ad50389416ba1647407dd507
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144741412"
---
# Dapatkan-AzSqlServer

## SYNOPSIS
Mengembalikan informasi tentang server SQL Database.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/get-azsqlserver) untuk informasi terbaru.

## SYNTAX

```
Get-AzSqlServer [[-ResourceGroupName] <String>] [[-ServerName] <String>] [-ExpandActiveDirectoryAdministrator]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlServer** mengembalikan informasi tentang satu atau beberapa server Azure SQL Database.
Tentukan nama server untuk melihat informasi hanya untuk server tersebut.

## EXAMPLES

### Contoh 1: Mendapatkan semua instans SQL Server yang ditetapkan ke grup sumber daya
```powershell
Get-AzSqlServer -ResourceGroupName "ResourceGroup01"
```

```output
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

Perintah ini mendapatkan informasi tentang semua server Azure SQL Database yang ditetapkan ke grup sumber daya ResourceGroup01.

### Contoh 2: Mendapatkan informasi tentang server Azure SQL Database
```powershell
Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01"
```

```output
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

### Contoh 3: Mendapatkan semua instans SQL Server dalam langganan
```powershell
Get-AzResourceGroup | Get-AzSqlServer
```

```output
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

Perintah ini mendapatkan informasi tentang semua server Azure SQL Database dalam langganan saat ini.

### Contoh 4: Mendapatkan semua instans SQL Server yang ditetapkan ke grup sumber daya menggunakan pemfilteran
```powershell
Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "server*"
```

```output
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

Perintah ini mendapatkan informasi tentang semua server Azure SQL Database yang ditetapkan ke grup sumber daya ResourceGroup01 yang dimulai dengan "server".

### Contoh 5: Dapatkan semua instans SQL Server yang ditetapkan ke grup sumber daya dengan informasi administrator eksternal
```powershell
$val = Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ExpandActiveDirectoryAdministrator

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

$val.Administrators
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

Perintah ini mendapatkan informasi tentang semua server Azure SQL Database yang ditetapkan ke grup sumber daya ResourceGroup01.

### Contoh 6: Mendapatkan informasi tentang server Azure SQL Database dengan informasi administrator eksternal
```powershell
$val = Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ExpandActiveDirectoryAdministrator
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

$val.Administrators
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Perluas Informasi Administrator Direktori Aktif di server.

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
Menentukan nama grup sumber daya tempat server ditetapkan.

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
Menentukan nama server yang didapat cmdlet ini.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel

## NOTES

## RELATED LINKS

[Baru-AzSqlServer](./New-AzSqlServer.md)

[Hapus-AzSqlServer](./Remove-AzSqlServer.md)

[Atur-AzSqlServer](./Set-AzSqlServer.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


