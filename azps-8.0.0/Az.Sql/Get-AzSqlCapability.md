---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 8C5D29AD-0B15-4CD4-8637-86ABD19F41C8
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlcapability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlCapability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlCapability.md
ms.openlocfilehash: 8a9b6789c9f1fd20ca7c102aeb075d2a4665f9a1
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145511311"
---
# Get-AzSqlCapability

## SYNOPSIS
Mendapatkan kemampuan SQL Database untuk langganan saat ini.

## SYNTAX

### FilterResults (Default)
```
Get-AzSqlCapability [-LocationName] <String> [-ServerVersionName <String>] [-EditionName <String>]
 [-ServiceObjectiveName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefaultResults
```
Get-AzSqlCapability [-LocationName] <String> [-Defaults] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlCapability** mendapatkan kemampuan Azure SQL Database yang tersedia pada langganan saat ini untuk suatu wilayah.
Jika Anda menentukan parameter *ServerVersionName*, *EditionName*, atau *ServiceObjectiveName* , cmdlet ini mengembalikan nilai yang ditentukan dan pendahulunya.

## EXAMPLES

### Contoh 1: Mendapatkan kapabilitas untuk langganan saat ini untuk suatu wilayah
```powershell
Get-AzSqlCapability -LocationName "Central US"
```

```output
Location                : Central US
Status                  : Available
SupportedServerVersions : {12.0, 2.0}
```

Perintah ini mengembalikan kemampuan untuk instans SQL Database pada langganan saat ini untuk wilayah AS Tengah.

### Contoh 2: Mendapatkan kemampuan default untuk langganan saat ini untuk suatu wilayah
```powershell
Get-AzSqlCapability -LocationName "Central US" -Defaults
```

```output
Location        : Central US
Status          : Available
ExpandedDetails : Version: 2.0 (Default) -> Edition: Standard (Default) -> Service Objective: S0 (Default)
```

Perintah ini mengembalikan kemampuan default untuk database SQL pada langganan saat ini di wilayah US Tengah.

### Contoh 3: Mendapatkan detail untuk tujuan layanan
```powershell
Get-AzSqlCapability -LocationName "Central US" -ServiceObjectiveName "S1"
```

```output
Location        : Central US
Status          : Available
ExpandedDetails : Version: 12.0 (Available) -> Edition: Standard (Default) -> Service Objective: S1 (Available) 
                  Version: 2.0 (Default) -> Edition: Standard (Default) -> Service Objective: S1 (Available)
```

Perintah ini mendapatkan kemampuan default untuk SQL Database untuk tujuan layanan yang ditentukan pada langganan saat ini.

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

### -Defaults
Menunjukkan bahwa cmdlet ini hanya mendapatkan default.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultResults
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EditionName
Menentukan nama edisi database tempat cmdlet ini mendapatkan kemampuan.

```yaml
Type: System.String
Parameter Sets: FilterResults
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocationName
Menentukan nama Lokasi tempat cmdlet ini mendapatkan kemampuan.
Untuk informasi selengkapnya, lihat Wilayahhttp://azure.microsoft.com/en-us/regions/ Azure (http://azure.microsoft.com/en-us/regions/).

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

### -ServerVersionName
Menentukan nama versi server yang cmdlet ini mendapatkan kemampuan.

```yaml
Type: System.String
Parameter Sets: FilterResults
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceObjectiveName
Menentukan nama tujuan layanan di mana cmdlet ini mendapatkan kemampuan.

```yaml
Type: System.String
Parameter Sets: FilterResults
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

### Microsoft.Azure.Commands.Sql.Location_Capabilities.Model.LocationCapabilityModel

## NOTES

## RELATED LINKS
