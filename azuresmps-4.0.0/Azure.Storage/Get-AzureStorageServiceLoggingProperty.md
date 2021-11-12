---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 494291A1-D854-4E97-B5EE-27BB5653D97C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 81d2afa18740f7d1b94880bec3883fe419314be1
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426243"
---
# Get-AzureStorageServiceLoggingProperty

## SYNOPSIS
Mendapatkan properti pembuatan log untuk Azure Storage baru.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorageServiceLoggingProperty [-ServiceType] <StorageServiceType> [-Context <IStorageContext>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageServiceLoggingProperty** mendapatkan properti pembuatan log untuk Azure Storage baru.

## EXAMPLES

### Contoh 1: Mendapatkan properti pembuatan log untuk layanan Blob
```
C:\PS>Get-AzureStorageServiceLoggingProperty -ServiceType Blob
```

Perintah ini mendapatkan properti pembuatan log untuk penyimpanan blob.

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

### -ServiceType
Menentukan tipe layanan penyimpanan.
Cmdlet ini mendapatkan properti pembuatan log untuk tipe layanan yang ditentukan oleh parameter ini.
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

[Set-AzureStorageServiceLoggingProperty](./Set-AzureStorageServiceLoggingProperty.md)


