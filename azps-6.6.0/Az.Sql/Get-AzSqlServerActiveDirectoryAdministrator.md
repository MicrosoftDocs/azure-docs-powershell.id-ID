---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: FEDA14CF-632F-4D15-A22B-C73A1298094F
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlserveractivedirectoryadministrator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerActiveDirectoryAdministrator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerActiveDirectoryAdministrator.md
ms.openlocfilehash: 10a3ffc28b87b17c1d000ce46e5782f3fe6c35c8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142076413"
---
# Get-AzSqlServerActiveDirectoryAdministrator

## SYNOPSIS
Mendapatkan informasi tentang administrator Azure AD untuk SQL Server.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/get-azsqlserveractivedirectoryadministrator) untuk informasi terbaru.

## SYNTAX

```
Get-AzSqlServerActiveDirectoryAdministrator [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlServerActiveDirectoryAdministrator** mendapatkan informasi tentang administrator Azure Active Directory (Azure AD) untuk AzureSQL Server dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang administrator untuk server
```
PS C:\>Get-AzSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01"
ResourceGroupName ServerName DisplayName ObjectId IsAzureADOnlyAuthentication
----------------- ---------- ----------- -------- -----------
ResourceGroup01   Server01   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b true
```

Perintah ini mendapatkan informasi tentang administrator Azure AD untuk server bernama Server01 yang terkait dengan grup sumber daya bernama ResourceGroup01.

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat SQL Server ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Menentukan nama SQL Server tempat cmdlet ini mendapatkan informasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerActiveDirectoryAdministrator.Model.AzureSqlServerActiveDirectoryAdministratorModel

## CATATAN

## RELATED LINKS

[Remove-AzSqlServerActiveDirectoryAdministrator](./Remove-AzSqlServerActiveDirectoryAdministrator.md)

[Set-AzSqlServerActiveDirectoryAdministrator](./Set-AzSqlServerActiveDirectoryAdministrator.md)

[Disable-AzSqlServerActiveDirectoryOnlyAuthentication](./Disable-AzSqlServerActiveDirectoryOnlyAuthentication.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


