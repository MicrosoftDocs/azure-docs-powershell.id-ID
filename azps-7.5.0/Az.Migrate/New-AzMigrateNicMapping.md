---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/new-azmigratenicmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateNicMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateNicMapping.md
ms.openlocfilehash: aa5910d75d90de9ae7405b9083b38dc316b0aeab
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145783234"
---
# New-AzMigrateNicMapping

## SYNOPSIS
Membuat objek untuk memperbarui properti NIC dari server replikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.migrate/new-azmigratenicmapping) untuk informasi terbaru.

## SYNTAX

```
New-AzMigrateNicMapping -NicID <String> [-TargetNicIP <String>] [-TargetNicName <String>]
 [-TargetNicSelectionType <String>] [-TargetNicSubnet <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzMigrateNicMapping membuat pemetaan NIC sumber yang dilampirkan ke server yang akan dimigrasikan.
Objek ini disediakan sebagai input ke cmdlet Set-AzMigrateServerReplication untuk memperbarui NIC dan propertinya untuk server replikasi.

## EXAMPLES

### Contoh 1: Membuat objek NIC
```powershell
New-AzMigrateNicMapping -NicID a2399354-653a-464e-a567-d30ef5467a31 -TargetNicSelectionType primary -TargetNicIP "172.17.1.17"
```

```output
IsPrimaryNic IsSelectedForMigration NicId                                TargetStaticIPAddress TargetSubnetName
------------ ---------------------- -----                                --------------------- ----------------
false        false                  a2399354-653a-464e-a567-d30ef5467a31
```

Membuat objek pembaruan NIC.

## PARAMETERS

### -NicID
Menentukan ID NIC yang akan diperbarui.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetNicIP
Menentukan IP dalam subnet tujuan yang akan digunakan untuk NIC.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetNicName
Menentukan nama NIC yang akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetNicSelectionType
Menentukan apakah NIC yang akan diperbarui akan menjadi primer, sekunder, atau tidak dimigrasikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetNicSubnet
Menentukan nama Subnet untuk NIC di Virtual Network tujuan tempat server perlu dimigrasikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtNicInput

## NOTES

ALIAS

## RELATED LINKS

