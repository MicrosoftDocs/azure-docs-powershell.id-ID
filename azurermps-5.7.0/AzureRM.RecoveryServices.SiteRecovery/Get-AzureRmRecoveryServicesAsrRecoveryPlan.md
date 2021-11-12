---
external help file: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: AzureRM.RecoveryServices.SiteRecovery
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.recoveryservices.siterecovery/get-azurermrecoveryservicesasrrecoveryplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/Get-AzureRmRecoveryServicesAsrRecoveryPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/Get-AzureRmRecoveryServicesAsrRecoveryPlan.md
ms.openlocfilehash: b95c3ab14d50558ef184beabcd461a59bb1a05ce
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422245"
---
# Get-AzureRmRecoveryServicesAsrRecoveryPlan

## SYNOPSIS
Mendapatkan paket pemulihan atau semua paket pemulihan di vault Layanan Pemulihan

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Default (Default)
```
Get-AzureRmRecoveryServicesAsrRecoveryPlan [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzureRmRecoveryServicesAsrRecoveryPlan -Name <String> [[-Path] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmRecoveryServicesAsrRecoveryPlan -FriendlyName <String> [[-Path] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmRecoveryServicesAsrRecoveryPlan** mendapatkan detail paket pemulihan yang ditentukan atau semua paket pemulihan di vault Layanan Pemulihan.

## EXAMPLES

### Contoh 1
```
PS C:\> $RP = Get-AzureRmRecoveryServicesAsrRecoveryPlan -Name $RPName
```

Dapatkan paket pemulihan dengan nama yang ditentukan.

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

### -FriendlyName
Menentukan nama mudah dari paket pemulihan yang akan anda dapatkan.

```yaml
Type: String
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Tentukan nama dari paket pemulihan yang akan anda dapatkan.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Menentukan jalur file tempat cmdlet ini menyimpan definisi json rencana pemulihan. Definisi json dapat diedit untuk mengubah rencana pemulihan dan digunakan untuk memperbarui paket pemulihan melalui cmdlet Update-AzureRmRecoveryServicesASRRecoveryPlan

```yaml
Type: String
Parameter Sets: ByName, ByFriendlyName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### System.Collections.Generic.IEnumerable'1[[Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRecoveryPlan, Microsoft.Azure.Commands.RecoveryServices.SiteRecovery, Version=4.0.0.0, Culture=neutral, PublicKeyToken=null]]

## CATATAN

## RELATED LINKS

[New-AzureRmRecoveryServicesAsrRecoveryPlan](./New-AzureRmRecoveryServicesAsrRecoveryPlan.md)

[Remove-AzureRmRecoveryServicesAsrRecoveryPlan](./Remove-AzureRmRecoveryServicesAsrRecoveryPlan.md)

[Update-AzureRmRecoveryServicesAsrRecoveryPlan](./Update-AzureRmRecoveryServicesAsrRecoveryPlan.md)
