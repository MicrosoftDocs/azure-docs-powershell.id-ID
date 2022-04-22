---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 2B12BC19-EF8F-43F5-AF04-C570FEEA1AE6
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainer.md
ms.openlocfilehash: 6360ed6a8bee31ab5f787bb0e191493c09fc0343
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143057627"
---
# New-AzStorageContainer

## SYNOPSIS
Membuat wadah penyimpanan Azure.

## SYNTAX

### ContainerName (Default)
```
New-AzStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### EnkripsiScope
```
New-AzStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType>]
 -DefaultEncryptionScope <String> -PreventEncryptionScopeOverride <Boolean> [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageContainer** membuat wadah penyimpanan Azure.

## EXAMPLES

### Contoh 1: Membuat wadah penyimpanan Azure
```
PS C:\>New-AzStorageContainer -Name "ContainerName" -Permission Off
```

Perintah ini membuat wadah penyimpanan.

### Contoh 2: Membuat beberapa wadah penyimpanan Azure
```
PS C:\>"container1 container2 container3".split() | New-AzStorageContainer -Permission Container
```

Contoh ini membuat beberapa wadah penyimpanan.
Ini menggunakan metode **Split** dari kelas .NET **String** lalu meneruskan nama pada pipeline.

### Contoh 3: Membuat wadah penyimpanan Azure dengan Lingkup Enkripsi
```
PS C:\> $container = New-AzStorageContainer  -Name "mycontainer" -DefaultEncryptionScope "myencryptscope" -PreventEncryptionScopeOverride $true 

PS C:\> $container.BlobContainerProperties.DefaultEncryptionScope
myencryptscope

PS C:\> $container.BlobContainerProperties.PreventEncryptionScopeOverride
True
```

Perintah ini membuat wadah penyimpanan, dengan Lingkup Enkripsi default sebagai myencryptscope, dan mengawali unggahan blob dengan Lingkup Enkripsi yang berbeda ke wadah ini.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu habis pihak klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini akan mencoba kembali permintaan.
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

### -Konteks
Menentukan konteks untuk wadah baru.

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

### -DefaultEncryptionScope
Default wadah untuk menggunakan lingkup enkripsi yang ditentukan untuk semua tulisan.

```yaml
Type: System.String
Parameter Sets: EncryptionScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -Nama
Menentukan nama untuk wadah baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Container

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Izin
Menentukan tingkat akses publik ke wadah ini.
Secara default, wadah dan gumpalan apa pun di dalamnya hanya dapat diakses oleh pemilik akun penyimpanan.
Untuk memberikan izin baca pengguna anonim ke kontainer dan blobnya, Anda dapat mengatur izin kontainer untuk mengaktifkan akses publik.
Pengguna anonim dapat membaca gumpalan dalam wadah yang tersedia untuk umum tanpa mengautentikasi permintaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Wadah.
Menyediakan akses baca penuh ke wadah dan blob-nya.
Klien dapat menghitung blob dalam kontainer melalui permintaan anonim, tetapi tidak dapat menghitung kontainer dalam akun penyimpanan. 
- Gumpalan.
Menyediakan akses baca ke data blob di seluruh wadah melalui permintaan anonim, tetapi tidak menyediakan akses ke data kontainer.
Klien tidak dapat menghitung blob dalam kontainer menggunakan permintaan anonim. 
- Off.
Yang membatasi akses hanya ke pemilik akun penyimpanan.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Storage.Blob.BlobContainerPublicAccessType]
Parameter Sets: (All)
Aliases: PublicAccess
Accepted values: Off, Container, Blob, Unknown

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreventEncryptionScopeOverride
Blokir pengesampingan lingkup enkripsi dari kontainer default.

```yaml
Type: System.Boolean
Parameter Sets: EncryptionScope
Aliases:

Required: True
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
Aliases: ServerTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageContainer

## NOTES

## RELATED LINKS

[Get-AzStorageContainer](./Get-AzStorageContainer.md)

[Hapus-AzStorageContainer](./Remove-AzStorageContainer.md)

[Set-AzStorageContainerAcl](./Set-AzStorageContainerAcl.md)


