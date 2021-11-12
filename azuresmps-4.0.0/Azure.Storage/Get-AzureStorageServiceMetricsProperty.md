---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 3B5B828A-6B3E-49BD-8BA9-916F8B69B8E9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 08eecc8ce6d3cb4047367f1d22c52a6bcbf5f06d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422444"
---
# Get-AzureStorageServiceMetricsProperty

## SYNOPSIS
Mendapatkan properti metrik untuk layanan Azure Storage ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorageServiceMetricsProperty [-ServiceType] <StorageServiceType> [-MetricsType] <ServiceMetricsType>
 [-Context <IStorageContext>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageServiceMetricsProperty** mendapatkan properti metrik untuk Azure Storage ini.

## EXAMPLES

### Contoh 1: Dapatkan properti metrik untuk layanan Blob
```
C:\PS>Get-AzureStorageServiceMetricsProperty -ServiceType Blob -MetricsType Hour
```

Perintah ini mendapatkan properti metrik untuk penyimpanan blob bagi tipe metrik Jam.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzureStorageContext.

```yaml
Type: IStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MetricsType
Menentukan tipe metrik.
Cmdlet ini mendapatkan Azure Storage metrik layanan untuk tipe metrik yang ditentukan parameter ini.
Nilai yang dapat diterima untuk parameter ini adalah: Jam dan Menit.

```yaml
Type: ServiceMetricsType
Parameter Sets: (All)
Aliases: 
Accepted values: Hour, Minute

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceType
Menentukan tipe layanan penyimpanan.
Cmdlet ini mendapatkan properti metrik untuk tipe yang ditentukan parameter ini.
Nilai yang dapat diterima untuk parameter ini adalah:

- Blob 
- Tabel
- Antrean
- File 

Nilai File saat ini tidak didukung.

```yaml
Type: StorageServiceType
Parameter Sets: (All)
Aliases: 
Accepted values: Blob, Table, Queue, File

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[New-AzureStorageContext](./New-AzureStorageContext.md)

[Set-AzureStorageServiceMetricsProperty](./Set-AzureStorageServiceMetricsProperty.md)


