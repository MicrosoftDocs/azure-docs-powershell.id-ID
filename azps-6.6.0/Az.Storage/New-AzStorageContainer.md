---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 2B12BC19-EF8F-43F5-AF04-C570FEEA1AE6
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageContainer.md
ms.openlocfilehash: d5c769075fa58444daa03dbd59f52dc1efa108bc
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140130723"
---
# New-AzStorageContainer

## SYNOPSIS
Membuat wadah penyimpanan Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storage/new-azstoragecontainer) untuk informasi terkini.

## SYNTAX

### ContainerName (Default)
```
New-AzStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### EncryptionScope
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

Perintah ini akan membuat wadah penyimpanan.

### Contoh 2: Membuat beberapa wadah penyimpanan Azure
```
PS C:\>"container1 container2 container3".split() | New-AzStorageContainer -Permission Container
```

Contoh ini membuat beberapa wadah penyimpanan.
Alur kerja **menggunakan** metode Terpisah dari kelas .NET **String** lalu melewati nama dalam saluran.

### Contoh 3: Membuat wadah penyimpanan Azure dengan Lingkup Enkripsi
```
PS C:\> $container = New-AzStorageContainer  -Name "mycontainer" -DefaultEncryptionScope "myencryptscope" -PreventEncryptionScopeOverride $true 

PS C:\> $container.BlobContainerProperties.DefaultEncryptionScope
myencryptscope

PS C:\> $container.BlobContainerProperties.PreventEncryptionScopeOverride
True
```

Perintah ini akan membuat wadah penyimpanan, dengan Lingkup Enkripsi default sebagai myencryptscope, dan menginversi unggahan blob dengan Lingkup Enkripsi berbeda ke wadah ini.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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
Menentukan jumlah maksimum panggilan jaringan bersama.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi guna membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini bisa membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth yang rendah, seperti 100 kilobit per detik.
Nilai default adalah 10.

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
Default wadah untuk menggunakan lingkup enkripsi tertentu untuk semua tulisan.

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

### -Permission
Menentukan tingkat akses publik ke wadah ini.
Secara default, wadah dan blob di dalamnya hanya dapat diakses oleh pemilik akun penyimpanan.
Untuk memberi pengguna anonim izin membaca ke wadah dan blob-nya, Anda bisa mengatur izin wadah untuk mengaktifkan akses publik.
Pengguna anonim bisa membaca blob di wadah yang tersedia secara publik tanpa mengotentikan permintaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Kontainer.
Menyediakan akses baca penuh ke wadah dan blobnya.
Klien dapat menghitung blob dalam wadah melalui permintaan anonim, tetapi tidak dapat menghitung wadah dalam akun penyimpanan. 
- Blob.
Menyediakan akses baca ke data blob di seluruh wadah melalui permintaan anonim, tapi tidak menyediakan akses ke data wadah.
Klien tidak bisa menghitung blob dalam wadah dengan menggunakan permintaan anonim. 
- Nonaktif.
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
Blokir menimpa lingkup enkripsi dari wadah default.

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
Menentukan interval waktu habis di sisi layanan, dalam detik, untuk permintaan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageContainer

## CATATAN

## RELATED LINKS

[Get-AzStorageContainer](./Get-AzStorageContainer.md)

[Remove-AzStorageContainer](./Remove-AzStorageContainer.md)

[Set-AzStorageContainerAcl](./Set-AzStorageContainerAcl.md)


