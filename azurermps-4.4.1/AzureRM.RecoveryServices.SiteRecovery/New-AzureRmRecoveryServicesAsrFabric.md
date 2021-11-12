---
external help file: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.dll-Help.xml
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/New-AzureRmRecoveryServicesAsrFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/New-AzureRmRecoveryServicesAsrFabric.md
ms.openlocfilehash: 28c038a6dfd29f9daaeb942afa8fcb4c479cd0aa
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420963"
---
# New-AzureRmRecoveryServicesAsrFabric

## SYNOPSIS
Creates an Azure Site Recovery Fabric.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmRecoveryServicesAsrFabric -Name <String> [-Type <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmRecoveryServicesAsrFabric** membuat Azure Site Recovery Fabric tipe yang ditentukan.

## EXAMPLES

### Contoh 1
```
PS C:\>  $currentJob = New-AzureRmRecoveryServicesAsrFabric -Name $FabricName
```

Starts the fabric creation with passed name and returns the ASR job used to track the fabric creation operation.

## PARAMETERS

### -Nama
Specifies the name of the Azure Site Recovery Fabric.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Specifies the Azure Site Recovery Fabric Type.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: HyperVSite

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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS

[Get-AzureRmRecoveryServicesAsrFabric](./Get-AzureRmRecoveryServicesAsrFabric.md)

[Remove-AzureRmRecoveryServicesAsrFabric](./Remove-AzureRmRecoveryServicesAsrFabric.md)
