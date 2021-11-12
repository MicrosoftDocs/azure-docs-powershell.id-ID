---
external help file: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.dll-Help.xml
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/New-AzureRmRecoveryServicesAsrRecoveryPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/New-AzureRmRecoveryServicesAsrRecoveryPlan.md
ms.openlocfilehash: 59a5cbde2bde2c2cbe5834f73199c7b86791d247
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421428"
---
# New-AzureRmRecoveryServicesAsrRecoveryPlan

## SYNOPSIS
Membuat paket pemulihan ASR.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### EnterpriseToEnterprise (Default)
```
New-AzureRmRecoveryServicesAsrRecoveryPlan -Name <String> -PrimaryFabric <ASRFabric>
 -RecoveryFabric <ASRFabric> -ReplicationProtectedItem <ASRReplicationProtectedItem[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### EnterpriseToAzure
```
New-AzureRmRecoveryServicesAsrRecoveryPlan -Name <String> -PrimaryFabric <ASRFabric> [-Azure]
 -FailoverDeploymentModel <String> -ReplicationProtectedItem <ASRReplicationProtectedItem[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByRPFile
```
New-AzureRmRecoveryServicesAsrRecoveryPlan -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmRecoveryServicesAsrRecoveryPlan** membuat rencana pemulihan Situs Azure di vault Layanan Pemulihan.

Rencana pemulihan mengumpulkan mesin virtual milik aplikasi ke dalam sebuah unit untuk memungkinkannya dipulihkan bersama-sama.

## EXAMPLES

### Contoh 1
```
PS C:\> $currentJob = New-AzureRmRecoveryServicesAsrRecoveryPlan -Name $RPName -PrimaryFabric $PrimaryFabric -RecoveryFabric $RecoveryFabric -ReplicationProtectedItem $RPI
```

Memulai operasi pembuatan rencana pemulihan dengan parameter tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

## PARAMETERS

### -Azure
Alihkan parameter untuk menentukan bahwa lokasi pemulihan untuk paket pemulihan adalah Azure.

```yaml
Type: SwitchParameter
Parameter Sets: EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailoverDeploymentModel
Menentukan model penyebaran failover (Manajer Sumber Daya atau Klasik) dari replikasi item yang diproteksi yang akan menjadi bagian dari rencana pemulihan ini.

```yaml
Type: String
Parameter Sets: EnterpriseToAzure
Aliases: 
Accepted values: Classic, ResourceManager

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama paket pemulihan.

```yaml
Type: String
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Menentukan jalur untuk file json definisi rencana pemulihan. Json definisi rencana pemulihan dapat digunakan untuk membuat rencana pemulihan.

```yaml
Type: String
Parameter Sets: ByRPFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryFabric
Specifies the ASR fabric object for the primary ASR fabric of the replication protected items that will be part of this recovery plan.

```yaml
Type: ASRFabric
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryFabric
Specifies the ASR fabric object for the recovery ASR fabric of the replication protected items that will be part of this recovery plan.

```yaml
Type: ASRFabric
Parameter Sets: EnterpriseToEnterprise
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationProtectedItem
Daftar replikasi item yang diproteksi untuk ditambahkan ke grup pertama rencana pemulihan.

```yaml
Type: ASRReplicationProtectedItem[]
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem[]

## OUTPUTS

### System.Object

## CATATAN

## RELATED LINKS

[Get-AzureRmRecoveryServicesAsrRecoveryPlan](./Get-AzureRmRecoveryServicesAsrRecoveryPlan.md)

[Remove-AzureRmRecoveryServicesAsrRecoveryPlan](./Remove-AzureRmRecoveryServicesAsrRecoveryPlan.md)

[Update-AzureRmRecoveryServicesAsrRecoveryPlan](./Update-AzureRmRecoveryServicesAsrRecoveryPlan.md)


