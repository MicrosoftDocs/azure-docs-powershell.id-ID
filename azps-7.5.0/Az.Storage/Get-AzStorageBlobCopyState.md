---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: CBD157D2-37C5-491F-A806-6B39F1D0415A
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstorageblobcopystate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobCopyState.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobCopyState.md
ms.openlocfilehash: f5399749ff0f7b0c64b010ac773ffc35f54cf11d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144191752"
---
# Get-AzStorageBlobCopyState

## SYNOPSIS
Mendapatkan status salinan blob Azure Storage.

## SYNTAX

### NamePipeline (Default)
```
Get-AzStorageBlobCopyState [-Blob] <String> [-Container] <String> [-WaitForComplete]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### BlobPipeline
```
Get-AzStorageBlobCopyState -CloudBlob <CloudBlob> [-WaitForComplete] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### ContainerPipeline
```
Get-AzStorageBlobCopyState -CloudBlobContainer <CloudBlobContainer> [-Blob] <String> [-WaitForComplete]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageBlobCopyState** mendapatkan status salinan blob Azure Storage.
Ini harus berjalan pada blob tujuan salin.

## EXAMPLES

### Contoh 1: Mendapatkan status salinan blob
```
C:\PS>Get-AzStorageBlobCopyState -Blob "ContosoPlanning2015" -Container "ContosoUploads"
```

Perintah ini mendapatkan status salinan blob bernama ContosoPlanning2015 dalam kontainer ContosoUploads.

### Contoh 2: Dapatkan status salin untuk blob dengan menggunakan alur
```
C:\PS>Get-AzStorageBlob -Blob "ContosoPlanning2015" -Container "ContosoUploads" | Get-AzStorageBlobCopyState
```

Perintah ini mendapatkan blob bernama ContosoPlanning2015 dalam kontainer bernama ContosoUploads dengan menggunakan cmdlet **Get-AzStorageBlob** , lalu meneruskan hasilnya ke cmdlet saat ini dengan menggunakan operator alur.
Cmdlet **Get-AzStorageBlobCopyState** mendapatkan status salin untuk blob tersebut.

### Contoh 3: Dapatkan status salin untuk blob dalam kontainer dengan menggunakan alur
```
C:\PS>Get-AzStorageContainer -Name "ContosoUploads" | Get-AzStorageBlobCopyState -Blob "ContosoPlanning2015"
```

Perintah ini mendapatkan kontainer bernama dengan menggunakan cmdlet **Get-AzStorageBlob** , lalu meneruskan hasilnya ke cmdlet saat ini.
Cmdlet **Get-AzStorageContainer** mendapatkan status salin untuk blob bernama ContosoPlanning2015 dalam kontainer tersebut.

### Contoh 4: Mulai Salin dan alur untuk mendapatkan status penyalinan
```
C:\PS> $destBlob = Start-AzStorageBlobCopy -SrcContainer "contosouploads" -SrcBlob "ContosoPlanning2015" -DestContainer "contosouploads2" -DestBlob "ContosoPlanning2015_copy"

C:\PS> $destBlob | Get-AzStorageBlobCopyState
```

Perintah pertama mulai menyalin blob "ContosoPlanning2015" ke "ContosoPlanning2015_copy", dan menghasilkan objek blob destiansi. Perintah kedua menyalurkan objek blob destiansi ke Get-AzStorageBlobCopyState, untuk mendapatkan status salinan blob. 

## PARAMETERS

### -Blob
Menentukan nama blob.
Cmdlet ini mendapatkan status operasi salinan blob untuk blob Azure Storage yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: NamePipeline, ContainerPipeline
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientTimeoutPerRequest
Menentukan interval waktu habis sisi klien, dalam detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba kembali permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini mengembalikan kesalahan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ClientTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudBlob
Menentukan objek **CloudBlob** dari pustaka Klien Azure Storage.
Untuk mendapatkan objek **CloudBlob** , gunakan cmdlet Get-AzStorageBlob.

```yaml
Type: Microsoft.Azure.Storage.Blob.CloudBlob
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
Cmdlet ini mendapatkan status salinan blob dalam kontainer yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudBlobContainer** , gunakan cmdlet Get-AzStorageContainer.

```yaml
Type: Microsoft.Azure.Storage.Blob.CloudBlobContainer
Parameter Sets: ContainerPipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Menentukan panggilan jaringan bersamaan maksimum.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU dan bandwidth lokal dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah jumlah absolut dan tidak dikalikan dengan jumlah inti.
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
Menentukan nama kontainer.
Cmdlet ini mendapatkan status salin untuk blob dalam kontainer yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: NamePipeline
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
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

### -ServerTimeoutPerRequest
Menentukan interval waktu habis sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ServerTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForComplete
Menunjukkan bahwa cmdlet ini menunggu salinan selesai.
Jika Anda tidak menentukan parameter ini, cmdlet ini akan segera mengembalikan hasil.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure. Storage. Blob.CloudBlob

### Microsoft.Azure. Storage. Blob.CloudBlobContainer

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.Azure. Storage. Blob.CopyState

## NOTES

## RELATED LINKS

[Start-AzStorageBlobCopy](./Start-AzStorageBlobCopy.md)

[Stop-AzStorageBlobCopy](./Stop-AzStorageBlobCopy.md)


