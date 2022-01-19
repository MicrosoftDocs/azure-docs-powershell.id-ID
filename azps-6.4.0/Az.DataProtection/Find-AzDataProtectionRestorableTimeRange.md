---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/find-azdataprotectionrestorabletimerange
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Find-AzDataProtectionRestorableTimeRange.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Find-AzDataProtectionRestorableTimeRange.md
ms.openlocfilehash: 8acbcd7f18bdcb78f35a9bdbf506aba536682688
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136217289"
---
# Find-AzDataProtectionRestorableTimeRange

## SYNOPSIS


## SYNTAX

```
Find-AzDataProtectionRestorableTimeRange -BackupInstanceName <String> -ResourceGroupName <String>
 -VaultName <String> -SourceDataStoreType <RestoreSourceDataStoreType> [-SubscriptionId <String>]
 [-EndTime <String>] [-StartTime <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION


## EXAMPLES

### Contoh 1: Mengambil rentang waktu yang dapat dikembalikan yang valid untuk BackupInstance
```powershell
PS C:\> $startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\>  $instances = Search-AzDataProtectionBackupInstanceInAzGraph -Subscription "subscriptionId" -DatasourceType AzureBlob -ResourceGroup "rgName" -Vault "vaultName"
PS C:\> $pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instances[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
PS C:\> $pointInTimeRange.RestorableTimeRange | fl

EndTime    : 2021-04-24T08:57:36.4149422Z
ObjectType : RestorableTimeRange
StartTime  : 2021-03-25T14:27:31.0000000Z
```

Atur $startTime dan $endTime.
Ambil contoh cadangan.
Ambil rentang waktu yang valid untuk Contoh Cadangan $instance[0].
Dispaly RestorableTimeRange, perhatikan bahwa ini bisa beberapa rentang dicrete.

## PARAMETERS

### -BackupInstanceName
Nama instans cadangan

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Waktu akhir untuk permintaan Rentang Pemulihan Daftar.
Format ISO 8601.

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

### -ResourceGroupName
Nama grup sumber daya tempat vault cadangan ada.

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

### -SourceDataStoreType
Mendapatkan atau mengatur tipe penyimpanan data sumber.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.RestoreSourceDataStoreType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Waktu mulai untuk permintaan Rentang Pemulihan Daftar.
Format ISO 8601.

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

### -SubscriptionId
Id langganan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama vault cadangan.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IAzureBackupFindRestorableTimeRangesResponseResource

## CATATAN

ALIAS

## RELATED LINKS

