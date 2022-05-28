---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: BDEEF1EA-A785-4E17-9887-C2000BDFCF57
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstoragecontaineracl
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageContainerAcl.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageContainerAcl.md
ms.openlocfilehash: b5ee44cb9ff810e9f6bfb3207598902abe1cc05a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500076"
---
# Set-AzStorageContainerAcl

## SYNOPSIS
Mengatur izin akses publik ke kontainer penyimpanan.

## SYNTAX

```
Set-AzStorageContainerAcl [-Name] <String> [-Permission] <BlobContainerPublicAccessType> [-PassThru]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageContainerAcl** mengatur izin akses publik ke kontainer penyimpanan yang ditentukan di Azure.

## EXAMPLES

### Contoh 1: Mengatur ACL kontainer penyimpanan azure berdasarkan nama
```
PS C:\>Set-AzStorageContainerAcl -Container "Container01" -Permission Off -PassThru
```

Perintah ini membuat kontainer yang tidak memiliki akses publik.

### Contoh 2: Mengatur ACL kontainer penyimpanan azure dengan menggunakan alur
```
PS C:\>Get-AzStorageContainer container* | Set-AzStorageContainerAcl -Permission Blob -PassThru
```

Perintah ini mendapatkan semua kontainer penyimpanan yang namanya dimulai dengan kontainer dan kemudian meneruskan hasilnya pada alur untuk mengatur izin untuk mereka semua ke akses Blob.

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
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya dengan menggunakan cmdlet New-AzStorageContext.

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

### -Name
Menentukan nama kontainer.

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

### -PassThru
Mengembalikan objek yang mewakili item tempat Anda bekerja.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -Izin
Menentukan tingkat akses publik ke kontainer ini.
Secara default, kontainer dan blob apa pun di dalamnya hanya dapat diakses oleh pemilik akun penyimpanan.
Untuk memberikan izin baca pengguna anonim ke kontainer dan blobnya, Anda dapat mengatur izin kontainer untuk mengaktifkan akses publik.
Pengguna anonim dapat membaca blob dalam kontainer yang tersedia untuk umum tanpa mengautentikasi permintaan.
Nilai yang dapat diterima untuk parameter ini adalah: --Container.
Menyediakan akses baca penuh ke kontainer dan blobnya.
Klien dapat menghitung blob dalam kontainer melalui permintaan anonim, tetapi tidak dapat menghitung kontainer di akun penyimpanan. --Blob.
Menyediakan akses baca ke data blob dalam kontainer melalui permintaan anonim, tetapi tidak menyediakan akses ke data kontainer.
Klien tidak dapat menghitung blob dalam kontainer dengan menggunakan permintaan anonim. -Off.
Membatasi akses hanya ke pemilik akun penyimpanan.

```yaml
Type: Microsoft.Azure.Storage.Blob.BlobContainerPublicAccessType
Parameter Sets: (All)
Aliases: PublicAccess
Accepted values: Off, Container, Blob, Unknown

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval waktu habis sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.
Waktu sisi server habis untuk setiap permintaan.

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

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageContainer

## NOTES

## RELATED LINKS

[Dapatkan-AzStorageContainer](./Get-AzStorageContainer.md)

[New-AzStorageContainer](./New-AzStorageContainer.md)

[Hapus-AzStorageContainer](./Remove-AzStorageContainer.md)


