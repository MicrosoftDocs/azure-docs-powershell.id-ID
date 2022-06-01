---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/start-azrecoveryservicesasrtestfailovercleanupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Start-AzRecoveryServicesAsrTestFailoverCleanupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Start-AzRecoveryServicesAsrTestFailoverCleanupJob.md
ms.openlocfilehash: 3308ea1d163206a7c2e51e22e320f832f5722cf5
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145977619"
---
# Start-AzRecoveryServicesAsrTestFailoverCleanupJob

## SYNOPSIS
Memulai operasi pembersihan failover pengujian.

## SYNTAX

### ByRPIObject (Default)
```
Start-AzRecoveryServicesAsrTestFailoverCleanupJob -ReplicationProtectedItem <ASRReplicationProtectedItem>
 [-Comment <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Start-AzRecoveryServicesAsrTestFailoverCleanupJob -ResourceId <String> [-Comment <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByRPObject
```
Start-AzRecoveryServicesAsrTestFailoverCleanupJob -RecoveryPlan <ASRRecoveryPlan> [-Comment <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzRecoveryServicesAsrTestFailoverCleanupJob memulai operasi pembersihan** failover pengujian pada item yang dilindungi replikasi atau rencana pemulihan tempat failover pengujian telah dilakukan.

## EXAMPLES

### Contoh 1

Pekerjaan untuk melacak pengujian failover Pembersihan Azure Site Recovery recoveryPlan.

```powershell
Start-AzRecoveryServicesAsrTestFailoverCleanupJob -RecoveryPlan $recoveryPlan -Comment "testing done"
```

### Contoh 2

Memulai operasi pembersihan failover pengujian. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Start-AzRecoveryServicesAsrTestFailoverCleanupJob -Comment 'testing done' -ReplicationProtectedItem $rpi
```

## PARAMETERS

### -Komentar
Komentar Pengguna untuk Uji Failover.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -RecoveryPlan
Rencana Pemulihan untuk melakukan pembersihan failover pengujian.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRecoveryPlan
Parameter Sets: ByRPObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReplicationProtectedItem
Item yang Dilindungi Replikasi untuk melakukan pembersihan failover pengujian.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem
Parameter Sets: ByRPIObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya item/ rencana pemulihan yang dilindungi replikasi untuk membersihkan failover pengujian.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases:

Required: True
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRecoveryPlan

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## NOTES

## RELATED LINKS
