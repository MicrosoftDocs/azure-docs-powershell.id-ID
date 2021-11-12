---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
Module Name: AzureRM
ms.assetid: F801A78E-6C11-4BD1-BEF4-01C4D6CD36D7
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.siterecovery/new-azurermsiterecoveryreplicationprotecteditem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/New-AzureRmSiteRecoveryReplicationProtectedItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/New-AzureRmSiteRecoveryReplicationProtectedItem.md
ms.openlocfilehash: 28b2f976b85d7db40cdb80cf2b9b58a2d7692952
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422579"
---
# New-AzureRmSiteRecoveryReplicationProtectedItem

## SYNOPSIS
Mengaktifkan replikasi untuk item yang dapat diproteksi dengan membuat item yang diproteksi

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DisableDR (Default)
```
New-AzureRmSiteRecoveryReplicationProtectedItem [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnterpriseToEnterprise
```
New-AzureRmSiteRecoveryReplicationProtectedItem -ProtectableItem <ASRProtectableItem> -Name <String>
 -ProtectionContainerMapping <ASRProtectionContainerMapping> [-WaitForCompletion]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnterpriseToAzure
```
New-AzureRmSiteRecoveryReplicationProtectedItem -ProtectableItem <ASRProtectableItem> -Name <String>
 -ProtectionContainerMapping <ASRProtectionContainerMapping> -RecoveryAzureStorageAccountId <String>
 [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HyperVSiteToAzure
```
New-AzureRmSiteRecoveryReplicationProtectedItem -ProtectableItem <ASRProtectableItem> -Name <String>
 -ProtectionContainerMapping <ASRProtectionContainerMapping> -RecoveryAzureStorageAccountId <String>
 -OSDiskName <String> -OS <String> [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmSiteRecoveryReplicationProtectedItem** membuat item baru Replication Protected.
Gunakan cmdlet ini untuk mengaktifkan replikasi bagi item yang dapat diproteksi.

## EXAMPLES

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama Item Terproteksi Replikasi Situs Azure.

```yaml
Type: String
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OS
Menentukan keluarga sistem operasi.
Nilai yang dapat diterima untuk parameter ini adalah: Windows atau Linux.

```yaml
Type: String
Parameter Sets: HyperVSiteToAzure
Aliases: 
Accepted values: Windows, Linux

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSDiskName
Menentukan nama disk sistem operasi.

```yaml
Type: String
Parameter Sets: HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectableItem
Menentukan Item Azure yang Dapat Diproteksi Pemulihan Situs.

```yaml
Type: ASRProtectableItem
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionContainerMapping
Menentukan objek pemetaan Penampung Pemulihan Situs Azure yang akan digunakan untuk replikasi.

```yaml
Type: ASRProtectionContainerMapping
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryAzureStorageAccountId
Menentukan ID akun penyimpanan Azure yang direplikasi cmdlet ini.

```yaml
Type: String
Parameter Sets: EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion
Mengindikasikan bahwa cmdlet menunggu penyelesaian.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.

Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### ASRProtectableItem
Parameter 'ProtectableItem' menerima nilai tipe 'ASRProtectableItem' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS

[Get-AzureRmSiteRecoveryReplicationProtectedItem](./Get-AzureRmSiteRecoveryReplicationProtectedItem.md)

[Remove-AzureRmSiteRecoveryReplicationProtectedItem](./Remove-AzureRmSiteRecoveryReplicationProtectedItem.md)

[Set-AzureRmSiteRecoveryReplicationProtectedItem](./Set-AzureRmSiteRecoveryReplicationProtectedItem.md)
