---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: A39A415A-B403-48D3-AF80-CF7CFE382577
online version: https://docs.microsoft.com/en-us/powershell/module/az.batch/get-azbatchlocationquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Batch/Batch/help/Get-AzBatchLocationQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Batch/Batch/help/Get-AzBatchLocationQuota.md
ms.openlocfilehash: 5c20529e174e37bd4d9d5d3f60b56c448206d09e
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409313"
---
# Get-AzBatchLocationQuota

## SYNOPSIS
Mendapatkan kuota layanan Kumpulan untuk langganan Anda pada lokasi tertentu.

## SINTAKS

```
Get-AzBatchLocationQuota [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Mendapatkan kuota layanan Kumpulan untuk langganan tertentu pada lokasi tertentu.

## CONTOH

### Contoh 1: Dapatkan kuota layanan Kumpulan untuk langganan di kawasan Barat AS
```
PS C:\>Get-AzBatchLocationQuota -Location "westus"
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
Menentukan kawasan tempat cmdlet ini memeriksa kuota.
Untuk informasi selengkapnya, lihat Azure Regions ( https://azure.microsoft.com/regions) .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Batch.Models.PSBatchLocationQuotas

## CATATAN

## LINK TERKAIT
