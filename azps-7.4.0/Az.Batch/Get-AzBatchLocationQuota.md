---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: A39A415A-B403-48D3-AF80-CF7CFE382577
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchlocationquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchLocationQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchLocationQuota.md
ms.openlocfilehash: 6f685b8bcb25df0c9fb39fb5220cdbd744e12f27
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143173025"
---
# Get-AzBatchLocationQuota

## SYNOPSIS
Mendapatkan kuota layanan Batch untuk langganan Anda di lokasi tertentu.

## SYNTAX

```
Get-AzBatchLocationQuota [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kuota layanan Batch untuk langganan tertentu di lokasi tertentu.

## EXAMPLES

### Contoh 1: Dapatkan kuota layanan Batch untuk langganan di kawasan AS Barat
```powershell
Get-AzBatchLocationQuota -Location "westus"
```

```output
          AccountQuota Location
          ------------ --------
          1            westus
```

Perintah ini mendapatkan kuota untuk langganan saat ini di kawasan AS Barat.
Nilai yang dikembalikan menunjukkan bahwa langganan ini hanya dapat membuat satu akun Batch di kawasan tersebut.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Lokasi
Menentukan kawasan di mana cmdlet ini memeriksa kuota.
Untuk informasi selengkapnya, lihat Kawasan Azure (https://azure.microsoft.com/regions).

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSBatchLocationQuotas

## NOTES

## RELATED LINKS
