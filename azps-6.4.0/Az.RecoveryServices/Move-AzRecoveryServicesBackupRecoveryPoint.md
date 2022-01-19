---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/move-azrecoveryservicesbackuprecoverypoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Move-AzRecoveryServicesBackupRecoveryPoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Move-AzRecoveryServicesBackupRecoveryPoint.md
ms.openlocfilehash: 27259684c5731b616fedbd767266061ba2db39a5
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136182465"
---
# Move-AzRecoveryServicesBackupRecoveryPoint

## SYNOPSIS
Memindahkan titik pemulihan dari tingkat sumber ke tingkat tujuan.

## SYNTAX

```
Move-AzRecoveryServicesBackupRecoveryPoint [-RecoveryPoint] <RecoveryPointBase>
 [-SourceTier] <RecoveryPointTier> [-DestinationTier] <RecoveryPointTier> [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Move-AzRecoveryServicesBackupRecoveryPoint** memindahkan titik pemulihan dari tingkat sumber ke tingkat tujuan. Saat ini hanya tingkatan Sumber yang valid adalah VaultStandard, hanya tingkatan tujuan yang valid adalah VaultArchive.

## EXAMPLES

### Contoh 1: Pindahkan titik pemulihan dari VaultStandard tier ke vaultArchive tier

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
PS C:\> $startDate = (Get-Date).AddDays(-7)
PS C:\> $endDate = Get-Date
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -Item $item[3] -StartDate $startDate.ToUniversalTime() -EndDate $endDate.ToUniversalTime() -VaultId $vault.ID -Tier VaultStandard
PS C:\> Move-AzRecoveryServicesBackupRecoveryPoint -RecoveryPoint $rp[2] -SourceTier VaultStandard -DestinationTier VaultArchive -VaultId $vault.ID
```

Pertama kami mendapatkan vault layanan pemulihan, daftar item cadangan. Lalu, kami mengambil poin pemulihan untuk item cadangan tertentu (dalam $item[3] dalam hal ini) yang ada di tingkat VaultStandard. Kemudian kami memicu pemindahan salah satu poin pemulihan dari daftar rp ke tingkatan VaultArchive.  

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
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
Saat ini, satu-satunya nilai yang dapat diterima adalah 'VaultArchive'

```yaml
Type: RecoveryPointTier
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
Titik Pemulihan untuk dipindahkan ke arsip

```yaml
Type: RecoveryPointBase
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
Type: RecoveryPointTier
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
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## CATATAN

## RELATED LINKS
