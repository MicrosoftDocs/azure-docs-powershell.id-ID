---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 5422429E-C609-4C1F-A021-E2A085B5F74E
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Set-AzureStorageServiceLoggingProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Set-AzureStorageServiceLoggingProperty.md
ms.openlocfilehash: c70adb10be6c221873c54f56f2fa6749d1027e66
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420169"
---
# Set-AzureStorageServiceLoggingProperty

## SYNOPSIS
Memodifikasi pembuatan log untuk Azure Storage baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureStorageServiceLoggingProperty [-ServiceType] <StorageServiceType> [-Version <Double>]
 [-RetentionDays <Int32>] [-LoggingOperations <LoggingOperations[]>] [-PassThru] [-Context <IStorageContext>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorageServiceLoggingProperty** mengubah pembuatan log untuk Azure Storage baru.

## EXAMPLES

### Contoh 1: Mengubah properti pembuatan log untuk layanan Blob
```
C:\PS>Set-AzureStorageServiceLoggingProperty -ServiceType Blob -LoggingOperations Read,Write -PassThru -RetentionDays 10 -Version 1.0
```

Perintah ini memodifikasi pembuatan log versi 1.0 untuk penyimpanan blob agar menyertakan operasi baca dan tulis.
Azure Storage log layanan mempertahankan entri selama 10 hari.
Karena perintah ini menentukan parameter *PassThru,* perintah menampilkan properti pembuatan log yang diubah.

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

### -LoggingOperations
Menentukan larik Azure Storage layanan.
Azure Storage akan mencatat operasi yang ditentukan parameter ini.
Nilai yang dapat diterima untuk parameter ini adalah:

- Tidak ada
- Baca
- Menulis
- Hapus
- Semua

```yaml
Type: LoggingOperations[]
Parameter Sets: (All)
Aliases: 
Accepted values: None, Read, Write, Delete, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan properti pembuatan log yang diperbarui.
Jika Anda tidak menentukan parameter ini, cmdlet ini tidak mengembalikan nilai.

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

### -RetentionDays
Menentukan jumlah hari layanan Azure Storage mempertahankan informasi yang dicatat.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceType
Menentukan tipe layanan penyimpanan.
Cmdlet ini memodifikasi properti pembuatan log untuk tipe layanan yang ditentukan oleh parameter ini.
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

### -Versi
Menentukan versi pembuatan log Azure Storage baru.
Nilai default adalah 1,0.

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### IStorageContext

Parameter 'Konteks' menerima nilai tipe 'IStorageContext' dari saluran

## OUTPUTS

### Microsoft.WindowsAzure. Storage. Shared.Protocol.LoggingProperties

## CATATAN

## RELATED LINKS

[Get-AzureStorageServiceLoggingProperty](./Get-AzureStorageServiceLoggingProperty.md)

[New-AzureStorageContext](./New-AzureStorageContext.md)


