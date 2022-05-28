---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/move-azrecoveryservicesbackuprecoverypoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Move-AzRecoveryServicesBackupRecoveryPoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Move-AzRecoveryServicesBackupRecoveryPoint.md
ms.openlocfilehash: 3a1be2a132b7751ccafaf1e47f1f5cf6120c1a07
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145558934"
---
# Move-AzRecoveryServicesBackupRecoveryPoint

## SYNOPSIS
Memindahkan titik pemulihan dari tingkat sumber ke tingkat tujuan.

## SYNTAX

```
Move-AzRecoveryServicesBackupRecoveryPoint [-RecoveryPoint] <RecoveryPointBase>
 [-SourceTier] <RecoveryPointTier> [-DestinationTier] <RecoveryPointTier> [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Move-AzRecoveryServicesBackupRecoveryPoint** memindahkan titik pemulihan dari tingkat sumber ke tingkat tujuan. Saat ini hanya tingkat Sumber yang valid adalah VaultStandard, hanya tingkat tujuan yang valid adalah VaultArchive.

## EXAMPLES

### Contoh 1: Pindahkan titik pemulihan dari tingkat VaultStandard ke tingkat VaultArchive

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
$startDate = (Get-Date).AddDays(-7)
$endDate = Get-Date
$rp = Get-AzRecoveryServicesBackupRecoveryPoint -Item $item[3] -StartDate $startDate.ToUniversalTime() -EndDate $endDate.ToUniversalTime() -VaultId $vault.ID -Tier VaultStandard
Move-AzRecoveryServicesBackupRecoveryPoint -RecoveryPoint $rp[2] -SourceTier VaultStandard -DestinationTier VaultArchive -VaultId $vault.ID
```

Pertama kita mendapatkan vault layanan pemulihan, daftar item cadangan. Kemudian, kami mengambil titik pemulihan untuk item cadangan tertentu ($item[3] dalam hal ini) yang berada di tingkat VaultStandard. Kemudian kita memicu pemindahan untuk salah satu titik pemulihan dari daftar rp ke tingkat VaultArchive.  

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DestinationTier
Tingkat Tujuan untuk pemindahan Titik Pemulihan.
Saat ini satu-satunya nilai yang dapat diterima adalah 'VaultArchive'

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointTier
Parameter Sets: (All)
Aliases:
Accepted values: VaultArchive

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPoint
Titik Pemulihan untuk berpindah ke arsip

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceTier
Tingkat Sumber untuk pemindahan Titik Pemulihan.
Saat ini satu-satunya nilai yang dapat diterima adalah 'VaultStandard'

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointTier
Parameter Sets: (All)
Aliases:
Accepted values: VaultStandard

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultId
ID ARM dari Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## NOTES

## RELATED LINKS
