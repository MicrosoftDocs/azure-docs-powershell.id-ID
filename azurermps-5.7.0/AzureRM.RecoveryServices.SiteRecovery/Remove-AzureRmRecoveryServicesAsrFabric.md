---
external help file: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: AzureRM.RecoveryServices.SiteRecovery
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.recoveryservices.siterecovery/remove-azurermrecoveryservicesasrfabric
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/Remove-AzureRmRecoveryServicesAsrFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/Remove-AzureRmRecoveryServicesAsrFabric.md
ms.openlocfilehash: 45979620ea4067af3fc906dfd7348d27b4850f06
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422586"
---
# Remove-AzureRmRecoveryServicesAsrFabric

## SYNOPSIS
Deletes the specified Azure Site Recovery Fabric from the Recovery Services vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmRecoveryServicesAsrFabric -InputObject <ASRFabric> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmRecoveryServicesAsrFabric** menghapus kain Pemulihan Situs Azure tertentu dari vault layanan Pemulihan.

## EXAMPLES

### Contoh 1
```
PS C:\> $currentJob = Remove-AzureRmRecoveryServicesAsrFabric -Fabric $Fabric
```

Starts the deletion of specified fabric and returns the ASR job used to track the operation.

## PARAMETERS

### -Konfirmasi
Tentukan apakah konfirmasi diperlukan. Atur nilai parameter konfirmasi ke $false untuk melewati konfirmasi.

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

### -Force
Memaksa perintah untuk berjalan tanpa menyediakan peringatan tambahan.

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

### -InputObject
The input object to the cmdlet: The ASR fabric object corresponding to the fabric to be deleted.

```yaml
Type: ASRFabric
Parameter Sets: (All)
Aliases: Fabric

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet dijalankan tanpa menjalankan cmdlet tersebut.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRFabric

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS

[Get-AzureRmRecoveryServicesAsrFabric](./Get-AzureRmRecoveryServicesAsrFabric.md)

[New-AzureRmRecoveryServicesAsrFabric](./New-AzureRmRecoveryServicesAsrFabric.md)
