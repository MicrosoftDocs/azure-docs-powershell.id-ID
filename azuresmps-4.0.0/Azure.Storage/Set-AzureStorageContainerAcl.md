---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: BDEEF1EA-A785-4E17-9887-C2000BDFCF57
online version: ''
schema: 2.0.0
ms.openlocfilehash: d75ab7078ba6a1a620f8e539a079d25d9cbf078b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915247"
---
# Set-AzureStorageContainerAcl

## SYNOPSIS
Mengatur izin akses publik ke wadah penyimpanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureStorageContainerAcl [-Name] <String> [-Permission] <BlobContainerPublicAccessType> [-PassThru]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorageContainerAcl** mengatur izin akses publik ke wadah penyimpanan tertentu di Azure.

## EXAMPLES

### Contoh 1: Atur wadah penyimpanan azure ACL menurut nama
```
PS C:\>Set-AzureStorageContainerAcl -Container "Container01" -Permission Off -PassThru
```

Perintah ini membuat wadah yang tidak memiliki akses publik.

### Contoh 2: Atur wadah penyimpanan azure ACL dengan menggunakan saluran
```
PS C:\>Get-AzureStorageContainer container* | Set-AzureStorageContainerAcl -Permission Blob -PassThru
```

Perintah ini mendapatkan semua wadah penyimpanan yang namanya dimulai dengan kontainer lalu meneruskan hasil pada pipeline untuk mengatur izin bagi mereka semua ke akses Blob.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu habis pihak klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini akan mencoba kembali permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini mengembalikan kesalahan.

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
Menentukan maksimum panggilan jaringan serentak.
Anda bisa menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini dapat membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth rendah, seperti 100 kilobit per detik.
Nilai defaultnya adalah 10.

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
Anda dapat membuatnya menggunakan cmdlet New-AzureStorageContext.

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
Menentukan nama wadah.

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

### -PassThru
Mengembalikan objek yang mewakili item tempat Anda bekerja.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -Izin
Menentukan tingkat akses publik ke wadah ini.
Secara default, wadah dan gumpalan apa pun di dalamnya hanya dapat diakses oleh pemilik akun penyimpanan.
Untuk memberikan izin baca pengguna anonim ke kontainer dan blobnya, Anda dapat mengatur izin kontainer untuk mengaktifkan akses publik.
Pengguna anonim dapat membaca gumpalan dalam wadah yang tersedia untuk umum tanpa mengautentikasi permintaan.
Nilai yang dapat diterima untuk parameter ini adalah:

-Kontainer.
Menyediakan akses baca penuh ke wadah dan blob-nya.
Klien dapat menghitung blob dalam kontainer melalui permintaan anonim, tetapi tidak dapat menghitung kontainer dalam akun penyimpanan. -Blob.
Menyediakan akses baca ke data blob dalam wadah melalui permintaan anonim, tetapi tidak menyediakan akses ke data kontainer.
Klien tidak dapat menghitung blob dalam kontainer menggunakan permintaan anonim. -Off.
Membatasi akses hanya ke pemilik akun penyimpanan.

```yaml
Type: BlobContainerPublicAccessType
Parameter Sets: (All)
Aliases: PublicAccess
Accepted values: Off, Container, Blob

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval batas waktu sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.
Waktu sisi server habis untuk setiap permintaan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageContainer](./Get-AzureStorageContainer.md)

[AzureStorageContainer baru](./New-AzureStorageContainer.md)

[Hapus-AzureStorageContainer](./Remove-AzureStorageContainer.md)


