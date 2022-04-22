---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: F20A5FD3-6EC3-4EFE-988C-75F8583961A4
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/set-azstorageblobcontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Set-AzStorageBlobContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Set-AzStorageBlobContent.md
ms.openlocfilehash: 0730d509ddf207d7541e854b15f34c30b44093e0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142845838"
---
# Set-AzStorageBlobContent

## SYNOPSIS
Mengunggah file lokal ke blob Azure Storage.

## SYNTAX

### SendManual (Default)
```
Set-AzStorageBlobContent [-File] <String> [-Container] <String> [-Blob <String>] [-BlobType <String>]
 [-Properties <Hashtable>] [-Metadata <Hashtable>] [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Force]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ContainerPipeline
```
Set-AzStorageBlobContent [-File] <String> [-Blob <String>] -CloudBlobContainer <CloudBlobContainer>
 [-BlobType <String>] [-Properties <Hashtable>] [-Metadata <Hashtable>]
 [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Force] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BlobPipeline
```
Set-AzStorageBlobContent [-File] <String> -CloudBlob <CloudBlob> [-BlobType <String>]
 [-Properties <Hashtable>] [-Metadata <Hashtable>] [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Force]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageBlobContent** mengunggah file lokal ke blob Azure Storage.

## EXAMPLES

### Contoh 1: Upload file bernama
```
PS C:\>Set-AzStorageBlobContent -Container "ContosoUpload" -File ".\PlanningData" -Blob "Planning2015"
```

Perintah ini mengunggah file yang bernama PlanningData ke blob bernama Planning2015.

### Contoh 2: Upload semua file di bawah folder saat ini
```
PS C:\>Get-ChildItem -File -Recurse | Set-AzStorageBlobContent -Container "ContosoUploads"
```

Perintah ini menggunakan cmdlet inti Windows PowerShell Get-ChildItem untuk mendapatkan semua file dalam folder saat ini dan di subfolder, lalu meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet **Set-AzStorageBlobContent** mengunggah file ke wadah bernama ContosoUploads.

### Contoh 3: Menimpa blob yang sudah ada
```
PS C:\>Get-AzStorageBlob -Container "ContosoUploads" -Blob "Planning2015" | Set-AzStorageBlobContent -File "ContosoPlanning"
```

Perintah ini mendapatkan blob bernama Planning2015 dalam wadah ContosoUploads dengan menggunakan cmdlet Get-AzStorageBlob, lalu meneruskan blob tersebut ke cmdlet saat ini.
Perintah mengunggah file yang bernama ContosoPlanning sebagai Planning2015.
Perintah ini tidak menentukan parameter *Force* .
Perintah meminta konfirmasi kepada Anda.
Jika Anda mengonfirmasi perintah, cmdlet menimpa blob yang sudah ada.

### Contoh 4: Upload file ke wadah menggunakan pipeline
```
PS C:\>Get-AzStorageContainer -Container "ContosoUpload*" | Set-AzStorageBlobContent -File "ContosoPlanning" -Blob "Planning2015"
```

Perintah ini mendapatkan wadah yang dimulai dengan string ContosoUpload menggunakan cmdlet **Get-AzStorageContainer** , lalu meneruskan blob tersebut ke cmdlet saat ini.
Perintah mengunggah file yang bernama ContosoPlanning sebagai Planning2015.

### Contoh 5: Upload blob file ke halaman dengan metadata dan PremiumPageBlobTier sebagai P10
```
PS C:\>$Metadata = @{"key" = "value"; "name" = "test"}
PS C:\> Set-AzStorageBlobContent -File "ContosoPlanning" -Container "ContosoUploads" -Metadata $Metadata -BlobType Page -PremiumPageBlobTier P10
```

Perintah pertama membuat tabel hash yang berisi metadata untuk blob, dan menyimpan tabel hash dalam variabel $Metadata.
Perintah kedua mengunggah file yang bernama ContosoPlanning ke wadah bernama ContosoUploads.
Blob mencakup metadata yang disimpan di $Metadata, dan memiliki PremiumPageBlobTier sebagai P10.

### Contoh 6: Upload file ke blob dengan properti blob tertentu
```
PS C:\> Set-AzStorageBlobContent -File "ContosoPlanning" -Container "ContosoUploads" -Properties @{"ContentType" = "image/jpeg"; "ContentMD5" = "i727sP7HigloQDsqadNLHw=="}
```

Perintah ini mengunggah file yang bernama ContosoPlanning ke kontainer bernama ContosoUploads dengan properti blob tertentu.

## PARAMETERS

### -Blob
Menentukan nama blob.
Cmdlet ini mengunggah file ke blob Azure Storage yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: SendManual, ContainerPipeline
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobType
Menentukan tipe untuk blob yang diunggah cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Blok
- Halaman Nilai defaultnya adalah Blokir.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Block, Page, Append

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientTimeoutPerRequest
Menentukan interval waktu habis pihak klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini akan mencoba kembali permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini mengembalikan kesalahan.

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

### -CloudBlob
Menentukan objek **CloudBlob** .
Untuk mendapatkan objek **CloudBlob** , gunakan cmdlet Get-AzStorageBlob.

```yaml
Type: Microsoft.WindowsAz.Storage.Blob.CloudBlob
Parameter Sets: BlobPipeline
Aliases: ICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CloudBlobContainer
Menentukan objek **CloudBlobContainer** dari pustaka klien Azure Storage.
Cmdlet ini mengunggah konten ke blob dalam wadah yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudBlobContainer** , gunakan cmdlet Get-AzStorageContainer.

```yaml
Type: Microsoft.WindowsAz.Storage.Blob.CloudBlobContainer
Parameter Sets: ContainerPipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Menentukan maksimum panggilan jaringan serentak.
Anda bisa menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini dapat membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth rendah, seperti 100 kilobit per detik.
Nilai defaultnya adalah 10.

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

### -Kontainer
Menentukan nama wadah.
Cmdlet ini mengunggah file ke blob dalam wadah yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: SendManual
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
Menentukan jalur file lokal untuk file yang diunggah sebagai konten blob.

```yaml
Type: System.String
Parameter Sets: SendManual
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ContainerPipeline, BlobPipeline
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Paksa
Menunjukkan bahwa cmdlet ini menimpa blob yang sudah ada tanpa meminta konfirmasi kepada Anda.

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

### -Metadata
Menentukan metadata untuk blob yang diunggah.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PremiumPageBlobTier
Tingkat Blob Halaman

```yaml
Type: Microsoft.WindowsAz.Storage.Blob.PremiumPageBlobTier
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, P4, P6, P10, P20, P30, P40, P50, P60

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properti
Menentukan properti untuk blob yang diunggah. Properti yang didukung adalah: CacheControl, ContentDisposition, ContentEncoding, ContentLanguage, ContentMD5, ContentType.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval batas waktu sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.WindowsAz. Storage. Blob.CloudBlobContainer

### Microsoft.WindowsAz. Storage. Blob.CloudBlob

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageBlob

## NOTES

## RELATED LINKS

[Get-AzStorageBlobContent](./Get-AzStorageBlobContent.md)

[Get-AzStorageBlob](./Get-AzStorageBlob.md)

[Remove-AzStorageBlob](./Remove-AzStorageBlob.md)
