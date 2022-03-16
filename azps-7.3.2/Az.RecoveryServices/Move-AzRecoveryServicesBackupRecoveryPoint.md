---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/move-azrecoveryservicesbackuprecoverypoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Move-AzRecoveryServicesBackupRecoveryPoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Move-AzRecoveryServicesBackupRecoveryPoint.md
ms.openlocfilehash: 1747cc45ae6dd60d3bc82931595c10d01a803bea
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140196311"
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
Saat ini, satu-satunya nilai yang dapat diterima adalah 'VaultArchive'

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
Titik Pemulihan untuk dipindahkan ke arsip

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## CATATAN

## RELATED LINKS
