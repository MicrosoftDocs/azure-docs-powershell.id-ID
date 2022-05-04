---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 2B12BC19-EF8F-43F5-AF04-C570FEEA1AE6
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainer.md
ms.openlocfilehash: 98f46741f34575023dbc58d00aa5a91d2e0fefc6
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144621174"
---
# New-AzStorageContainer

## SYNOPSIS
Membuat kontainer penyimpanan Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/new-azstoragecontainer) untuk informasi terbaru.

## SYNTAX

### ContainerName (Default)
```
New-AzStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### Cakupan Enkripsi
```
New-AzStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType>]
 -DefaultEncryptionScope <String> -PreventEncryptionScopeOverride <Boolean> [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageContainer membuat kontainer** penyimpanan Azure.

## EXAMPLES

### Contoh 1: Membuat kontainer penyimpanan Azure
```
PS C:\>New-AzStorageContainer -Name "ContainerName" -Permission Off
```

Perintah ini membuat kontainer penyimpanan.

### Contoh 2: Membuat beberapa kontainer penyimpanan Azure
```
PS C:\>"container1 container2 container3".split() | New-AzStorageContainer -Permission Container
```

Contoh ini membuat beberapa kontainer penyimpanan.
Ini menggunakan metode **Split** dari kelas .NET **String** dan kemudian meneruskan nama pada alur.

### Contoh 3: Membuat kontainer penyimpanan Azure dengan Cakupan Enkripsi
```
PS C:\> $container = New-AzStorageContainer  -Name "mycontainer" -DefaultEncryptionScope "myencryptscope" -PreventEncryptionScopeOverride $true 

PS C:\> $container.BlobContainerProperties.DefaultEncryptionScope
myencryptscope

PS C:\> $container.BlobContainerProperties.PreventEncryptionScopeOverride
True
```

Perintah ini membuat kontainer penyimpanan, dengan Cakupan Enkripsi default sebagai myencryptscope, dan mengawali pengunggahan blob dengan Cakupan Enkripsi yang berbeda ke kontainer ini.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu habis sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
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

### -Context
Menentukan konteks untuk kontainer baru.

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
Default kontainer untuk menggunakan cakupan enkripsi tertentu untuk semua penulisan.

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

### -Name
Menentukan nama untuk kontainer baru.

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
Menentukan tingkat akses publik ke kontainer ini.
Secara default, kontainer dan blob apa pun di dalamnya hanya dapat diakses oleh pemilik akun penyimpanan.
Untuk memberikan izin baca pengguna anonim ke kontainer dan blobnya, Anda dapat mengatur izin kontainer untuk mengaktifkan akses publik.
Pengguna anonim dapat membaca blob dalam kontainer yang tersedia untuk umum tanpa mengautentikasi permintaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Wadah.
Menyediakan akses baca penuh ke kontainer dan blobnya.
Klien dapat menghitung blob dalam kontainer melalui permintaan anonim, tetapi tidak dapat menghitung kontainer di akun penyimpanan. 
- Gumpalan.
Menyediakan akses baca ke data blob di seluruh kontainer melalui permintaan anonim, tetapi tidak menyediakan akses ke data kontainer.
Klien tidak dapat menghitung blob dalam kontainer dengan menggunakan permintaan anonim. 
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
Penimpaan blok cakupan enkripsi dari default kontainer.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageContainer

## NOTES

## RELATED LINKS

[Dapatkan-AzStorageContainer](./Get-AzStorageContainer.md)

[Hapus-AzStorageContainer](./Remove-AzStorageContainer.md)

[Set-AzStorageContainerAcl](./Set-AzStorageContainerAcl.md)


