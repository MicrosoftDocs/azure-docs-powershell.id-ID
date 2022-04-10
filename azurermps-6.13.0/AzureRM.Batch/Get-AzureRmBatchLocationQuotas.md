---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: A39A415A-B403-48D3-AF80-CF7CFE382577
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/get-azurermbatchlocationquotas
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureRmBatchLocationQuotas.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureRmBatchLocationQuotas.md
ms.openlocfilehash: dea724c77b0574e8235c58a2a696987c94ca586d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140865134"
---
# Get-AzureRmBatchLocationQuotas

## SYNOPSIS
Mendapatkan kuota layanan Kumpulan untuk langganan Anda pada lokasi tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBatchLocationQuotas [-Location] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kuota layanan Kumpulan untuk langganan tertentu pada lokasi tertentu.

## EXAMPLES

### Contoh 1: Dapatkan kuota layanan Kumpulan untuk langganan di kawasan Barat AS
```
PS C:\>Get-AzureRmBatchLocationQuotas -Location "westus"
          AccountQuota Location
          ------------ --------
          1            westus
```

Perintah ini mendapatkan kuota langganan saat ini di kawasan AS Barat.
Nilai pengembalian menunjukkan bahwa langganan ini hanya dapat membuat satu akun Kumpulan di kawasan tersebut.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan kawasan tempat cmdlet ini memeriksa kuota.
Untuk informasi selengkapnya, lihat Azure Regions (https://azure.microsoft.com/regions).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSBatchLocationQuotas

## CATATAN

## RELATED LINKS
