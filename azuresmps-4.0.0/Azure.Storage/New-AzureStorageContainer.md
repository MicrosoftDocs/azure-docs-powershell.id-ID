---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 2B12BC19-EF8F-43F5-AF04-C570FEEA1AE6
online version: ''
schema: 2.0.0
ms.openlocfilehash: aadaa080c6d9ebfb7e986aabef860c08094f64d6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422443"
---
# New-AzureStorageContainer

## SYNOPSIS
Membuat wadah penyimpanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageContainer** membuat wadah penyimpanan Azure.

## EXAMPLES

### Contoh 1: Membuat wadah penyimpanan Azure
```
PS C:\>New-AzureStorageContainer -Name "ContainerName" -Permission Off
```

Perintah ini akan membuat wadah penyimpanan.

### Contoh 2: Membuat beberapa wadah penyimpanan Azure
```
PS C:\>"container1 container2 container3".split() | New-AzureStorageContainer -Permission Container
```

Contoh ini membuat beberapa wadah penyimpanan.
Alur kerja **menggunakan** metode Terpisah dari kelas .NET **String** lalu melewati nama dalam saluran.

## PARAMETERS

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
Menentukan konteks untuk wadah baru.

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

### -Nama
Menentukan nama untuk wadah baru.

```yaml
Type: String
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
Type: BlobContainerPublicAccessType
Parameter Sets: (All)
Aliases: PublicAccess
Accepted values: Off, Container, Blob

Required: False
Position: 1
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureStorageContainer](./Get-AzureStorageContainer.md)

[Remove-AzureStorageContainer](./Remove-AzureStorageContainer.md)

[Set-AzureStorageContainerAcl](./Set-AzureStorageContainerAcl.md)


