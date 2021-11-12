---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 54585346-04E2-4FB4-B5FD-833A85C46ACB
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Start-AzureStorageBlobCopy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Start-AzureStorageBlobCopy.md
ms.openlocfilehash: 1fc4c94e515de42c969de2c490e66d2aa22669e2
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132429068"
---
# Start-AzureStorageBlobCopy

## SYNOPSIS
Memulai menyalin blob.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ContainerName (Default)
```
Start-AzureStorageBlobCopy [-SrcBlob] <String> -SrcContainer <String> -DestContainer <String>
 [-DestBlob <String>] [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Context <IStorageContext>]
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BlobInstance
```
Start-AzureStorageBlobCopy -CloudBlob <CloudBlob> -DestContainer <String> [-DestBlob <String>]
 [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Context <IStorageContext>] [-DestContext <IStorageContext>]
 [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BlobInstanceToBlobInstance
```
Start-AzureStorageBlobCopy -CloudBlob <CloudBlob> -DestCloudBlob <CloudBlob>
 [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Context <IStorageContext>] [-DestContext <IStorageContext>]
 [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ContainerInstance
```
Start-AzureStorageBlobCopy -CloudBlobContainer <CloudBlobContainer> [-SrcBlob] <String> -DestContainer <String>
 [-DestBlob <String>] [-PremiumPageBlobTier <PremiumPageBlobTier>] [-Context <IStorageContext>]
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShareName
```
Start-AzureStorageBlobCopy -SrcShareName <String> -SrcFilePath <String> -DestContainer <String>
 [-DestBlob <String>] [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ShareInstance
```
Start-AzureStorageBlobCopy -SrcShare <CloudFileShare> -SrcFilePath <String> -DestContainer <String>
 [-DestBlob <String>] [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DirInstance
```
Start-AzureStorageBlobCopy -SrcDir <CloudFileDirectory> -SrcFilePath <String> -DestContainer <String>
 [-DestBlob <String>] [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FileInstance
```
Start-AzureStorageBlobCopy -SrcFile <CloudFile> -DestContainer <String> [-DestBlob <String>]
 [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileInstanceToBlobInstance
```
Start-AzureStorageBlobCopy -SrcFile <CloudFile> -DestCloudBlob <CloudBlob> [-Context <IStorageContext>]
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UriPipeline
```
Start-AzureStorageBlobCopy -AbsoluteUri <String> -DestContainer <String> -DestBlob <String>
 [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureStorageBlobCopy** mulai menyalin blob.

## EXAMPLES

### Contoh 1: Menyalin blob bernama
```
C:\PS>Start-AzureStorageBlobCopy -SrcBlob "ContosoPlanning2015" -DestContainer "ContosoArchives" -SrcContainer "ContosoUploads"
```

Perintah ini memulai operasi penyalinan blob yang bernama ContosoPlanning2015 dari wadah yang bernama ContosoUploads ke wadah yang bernama ContosoArchives.

### Contoh 2: Dapatkan wadah untuk menentukan blob untuk disalin
```
C:\PS>Get-AzureStorageContainer -Name "ContosoUploads" | Start-AzureStorageBlobCopy -SrcBlob "ContosoPlanning2015" -DestContainer "ContosoArchives"
```

Perintah ini mendapatkan wadah bernama ContosoUploads, menggunakan cmdlet **Get-AzureStorageContainer,** lalu meneruskan wadah ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet tersebut memulai operasi penyalinan blob bernama ContosoPlanning2015.
Cmdlet sebelumnya menyediakan wadah sumber.
Parameter *DestContainer* menentukan ContosoArchives sebagai wadah tujuan.

### Contoh 3: Mendapatkan blob untuk menyalin
```
C:\PS>Get-AzureStorageBlob -Container "ContosoUploads" | Start-AzureStorageBlobCopy -DestContainer "ContosoArchives"
```

Perintah ini menghasilkan blob dalam wadah yang bernama ContosoUploads, menggunakan cmdlet **Get-AzureStorageBlob,** lalu meneruskan hasilnya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet tersebut memulai operasi penyalinan blob ke wadah yang bernama ContosoArchives.

### Contoh 4: Menyalin blob yang ditentukan sebagai objek
```
C:\PS>$SrcBlob = Get-AzureStorageBlob -Container "ContosoUploads" -Blob "ContosoPlanning2015"
C:\PS> $DestBlob = Get-AzureStorageBlob -Container "ContosoArchives" -Blob "ContosoPlanning2015Archived"
C:\PS> Start-AzureStorageBlobCopy -ICloudBlob $SrcBlob.ICloudBlob -DestICloudBlob $DestBlob.ICloudBlob
```

Perintah pertama mendapatkan blob bernama ContosoPlanning2015 dalam wadah yang bernama ContosoUploads.
Perintah menyimpan objek tersebut dalam $SrcBlob variabel.

Perintah kedua mendapatkan blob bernama ContosoPlanning2015Archived dalam wadah yang bernama ContosoArchives.
Perintah menyimpan objek tersebut dalam $DestBlob variabel.

Perintah terakhir memulai operasi penyalinan dari wadah sumber ke wadah tujuan.
Perintah menggunakan notasi titik standar untuk menentukan **objek ICloudBlob** untuk $SrcBlob dan $DestBlob blob.

### Contoh 5: Menyalin blob dari URI
```
C:\PS>$Context = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
C:\PS> Start-AzureStorageBlobCopy -AbsoluteUri "http://www.contosointernal.com/planning" -DestContainer "ContosoArchive" -DestBlob "ContosoPlanning2015" -DestContext $Context
```

Perintah ini akan membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci tertentu, lalu menyimpan kunci tersebut dalam $Context variabel.

Perintah kedua menyalin file dari URI tertentu ke blob bernama ContosoPlanning dalam wadah yang bernama ContosoArchive.
Perintah tersebut memulai operasi penyalinan dalam konteks yang disimpan di $Context.

## PARAMETERS

### -AbsoluteUri
Menentukan URI absolut dari file untuk disalin ke Azure Storage blob.

```yaml
Type: String
Parameter Sets: UriPipeline
Aliases: SrcUri, SourceUri

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientTimeoutPerRequest
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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

### -CloudBlob
Menentukan objek **CloudBlob** dari Azure Storage Client.
Untuk mendapatkan objek **CloudBlob,** gunakan cmdlet Get-AzureStorageBlob cmdlet.

```yaml
Type: CloudBlob
Parameter Sets: BlobInstance, BlobInstanceToBlobInstance
Aliases: SrcICloudBlob, SrcCloudBlob, ICloudBlob, SourceICloudBlob, SourceCloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -CloudBlobContainer
Menentukan objek **CloudBlobContainer** dari Azure Storage Client.
Cmdlet ini menyalin blob dari wadah yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudBlobContainer,** gunakan cmdlet Get-AzureStorageContainer cmdlet.

```yaml
Type: CloudBlobContainer
Parameter Sets: ContainerInstance
Aliases: SourceCloudBlobContainer

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Menentukan jumlah maksimum panggilan jaringan bersama.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi guna membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini bisa membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth yang rendah, seperti 100 kilobit per detik.
Nilai default adalah 10.

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

### -Konteks
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzureStorageContext.

```yaml
Type: IStorageContext
Parameter Sets: ContainerName, BlobInstance, BlobInstanceToBlobInstance, ContainerInstance, ShareName, ShareInstance, DirInstance, FileInstance, FileInstanceToBlobInstance
Aliases: SrcContext, SourceContext

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: IStorageContext
Parameter Sets: UriPipeline
Aliases: SrcContext, SourceContext

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DestBlob
Menentukan nama blob tujuan.

```yaml
Type: String
Parameter Sets: ContainerName, BlobInstance, ContainerInstance, ShareName, ShareInstance, DirInstance, FileInstance
Aliases: DestinationBlob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UriPipeline
Aliases: DestinationBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestCloudBlob
Menentukan objek **CloudBlob tujuan**

```yaml
Type: CloudBlob
Parameter Sets: BlobInstanceToBlobInstance, FileInstanceToBlobInstance
Aliases: DestICloudBlob, DestinationCloudBlob, DestinationICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContainer
Menentukan nama wadah tujuan.

```yaml
Type: String
Parameter Sets: ContainerName, BlobInstance, ContainerInstance, ShareName, ShareInstance, DirInstance, FileInstance, UriPipeline
Aliases: DestinationContainer

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContext
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzureStorageContext.

```yaml
Type: IStorageContext
Parameter Sets: (All)
Aliases: DestinationContext

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Mengindikasikan bahwa cmdlet ini menimpa blob tujuan tanpa meminta konfirmasi.

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

### -PremiumPageBlobTier
Premium Tier Blob Halaman

```yaml
Type: PremiumPageBlobTier
Parameter Sets: ContainerName, BlobInstance, BlobInstanceToBlobInstance, ContainerInstance
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval waktu habis di sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.

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

### -SrcBlob
Menentukan nama blob sumber.

```yaml
Type: String
Parameter Sets: ContainerName, ContainerInstance
Aliases: SourceBlob

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainer
Menentukan nama wadah sumber.

```yaml
Type: String
Parameter Sets: ContainerName
Aliases: SourceContainer

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcDir
Menentukan objek **CloudFileDirectory** dari Azure Storage Client.

```yaml
Type: CloudFileDirectory
Parameter Sets: DirInstance
Aliases: SourceDir

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcFile
Spesifikasi objek **CloudFile** dari Azure Storage Client.
Anda dapat membuatnya atau menggunakan Get-AzureStorageFile cmdlet.

```yaml
Type: CloudFile
Parameter Sets: FileInstance, FileInstanceToBlobInstance
Aliases: SourceFile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SrcFilePath
Menentukan jalur relatif file sumber dari direktori sumber atau berbagi sumber.

```yaml
Type: String
Parameter Sets: ShareName, ShareInstance, DirInstance
Aliases: SourceFilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShare
Menentukan objek **CloudFileShare** dari Azure Storage Client.
Anda dapat membuatnya atau menggunakan Get-AzureStorageShare cmdlet.

```yaml
Type: CloudFileShare
Parameter Sets: ShareInstance
Aliases: SourceShare

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShareName
Menentukan nama berbagi sumber.

```yaml
Type: String
Parameter Sets: ShareName
Aliases: SourceShareName

Required: True
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### CloudBlob

Parameter 'CloudBlob' menerima nilai tipe 'CloudBlob' dari saluran

### IStorageContext

Parameter 'Konteks' menerima nilai tipe 'IStorageContext' dari saluran

### IStorageContext

Parameter 'Konteks' menerima nilai tipe 'IStorageContext' dari saluran

### CloudFile

Parameter 'SrcFile' menerima nilai tipe 'CloudFile' dari saluran

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageBlob

## CATATAN

## RELATED LINKS

[Get-AzureStorageBlobCopyState](./Get-AzureStorageBlobCopyState.md)

[Stop-AzureStorageBlobCopy](./Stop-AzureStorageBlobCopy.md)
