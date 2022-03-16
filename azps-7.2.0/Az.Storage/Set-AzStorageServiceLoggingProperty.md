---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 5422429E-C609-4C1F-A021-E2A085B5F74E
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstorageserviceloggingproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageServiceLoggingProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageServiceLoggingProperty.md
ms.openlocfilehash: 7078c6878e1013a7f6e46822a141b9af3833c112
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139948103"
---
# Set-AzStorageServiceLoggingProperty

## SYNOPSIS
Memodifikasi pembuatan log untuk Azure Storage baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storage/set-azstorageserviceloggingproperty) untuk informasi terkini.

## SYNTAX

```
Set-AzStorageServiceLoggingProperty [-ServiceType] <StorageServiceType> [-Version <Double>]
 [-RetentionDays <Int32>] [-LoggingOperations <LoggingOperations[]>] [-PassThru] [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageServiceLoggingProperty** memodifikasi pembuatan log untuk Azure Storage baru.

## EXAMPLES

### Contoh 1: Mengubah properti pembuatan log untuk layanan Blob
```
C:\PS>Set-AzStorageServiceLoggingProperty -ServiceType Blob -LoggingOperations Read,Write -PassThru -RetentionDays 10 -Version 1.0
```

Perintah ini memodifikasi pembuatan log versi 1.0 untuk penyimpanan blob agar menyertakan operasi baca dan tulis.
Azure Storage log layanan mempertahankan entri selama 10 hari.
Karena perintah ini menentukan parameter *PassThru* , perintah menampilkan properti pembuatan log yang diubah.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzStorageContext.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoggingOperations
Menentukan larik Azure Storage operasi layanan.
Azure Storage ini mencatat operasi yang ditentukan parameter ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- Baca
- Menulis
- Hapus
- Semua

```yaml
Type: Microsoft.Azure.Storage.Shared.Protocol.LoggingOperations[]
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.Nullable`1[System.Int32]
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
- File Nilai File saat ini tidak didukung.

```yaml
Type: Microsoft.WindowsAzure.Commands.Storage.Common.StorageServiceType
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
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.Azure. Storage. Shared.Protocol.LoggingProperties

## CATATAN

## RELATED LINKS

[Get-AzStorageServiceLoggingProperty](./Get-AzStorageServiceLoggingProperty.md)

[New-AzStorageContext](./New-AzStorageContext.md)


