---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: FD3A0013-4365-4E65-891C-5C50A9D5658C
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/get-azurestorageshare
schema: 2.0.0
ms.openlocfilehash: 7ddc117ca7f8af55fbfad6362d8b7a024369809e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143055330"
---
# Get-AzureStorageShare

## SYNOPSIS
Mendapatkan daftar berbagi file.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### MatchingPrefix (Default)
```
Get-AzureStorageShare [[-Prefix] <String>] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

### Tertentu
```
Get-AzureStorageShare [-Name] <String> [[-SnapshotTime] <DateTimeOffset>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageShare** mendapatkan daftar berbagi file untuk akun penyimpanan.

## EXAMPLES

### Contoh 1: Dapatkan berbagi file
```
PS C:\>Get-AzureStorageShare -Name "ContosoShare06"
```

Perintah ini mendapatkan berbagi file bernama ContosoShare06.

### Contoh 2: Dapatkan semua berbagi file yang dimulai dengan string
```
PS C:\>Get-AzureStorageShare -Prefix "Contoso"
```

Perintah ini mendapatkan semua berbagi file yang memiliki nama yang dimulai dengan Contoso.

### Contoh 3: Mendapatkan semua berbagi file dalam konteks tertentu
```
PS C:\>$Context = New-AzureStorageContext -Local
PS C:\> Get-AzureStorageShare -Context $Context
```

Perintah pertama menggunakan cmdlet **New-AzureStorageContext** untuk membuat konteks menggunakan parameter *Lokal* , lalu menyimpan objek konteks tersebut dalam variabel $Context.
Perintah kedua akan membagikan file untuk objek konteks yang disimpan di $Context.

### Contoh 4: Dapatkan snapshot berbagi file dengan nama berbagi tertentu dan SnapshotTime
```
PS C:\>Get-AzureStorageShare -Name "ContosoShare06" -SnapshotTime "6/16/2017 9:48:41 AM +00:00"
```

Perintah ini mendapatkan snapshot berbagi file dengan nama berbagi tertentu dan SnapshotTime.

## PARAMETERS

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
Menentukan konteks Azure Storage.
Untuk mendapatkan konteks, gunakan cmdlet [New-AzureStorageContext](./New-AzureStorageContext.md) .

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

### -Nama
Menentukan nama file yang dibagikan.
Cmdlet ini mendapatkan berbagi file yang ditentukan parameter ini, atau tidak ada apa-apa jika Anda menentukan nama berbagi file yang tidak ada.

```yaml
Type: System.String
Parameter Sets: Specific
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefiks
Menentukan prefiks untuk berbagi file.
Cmdlet ini mendapatkan berbagi file yang cocok dengan prefiks yang ditentukan parameter ini, atau tidak ada file yang dibagikan jika tidak ada file yang sama dengan prefiks yang ditentukan.

```yaml
Type: System.String
Parameter Sets: MatchingPrefix
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan lamanya periode batas waktu untuk bagian server dari permintaan.

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

### -SnapshotTime
SnapshotTime dari snapshot berbagi file yang akan diterima.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: Specific
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure. Storage. File.CloudFileShare

## NOTES

## RELATED LINKS

[AzureStorageShare baru](./New-AzureStorageShare.md)

[Hapus-AzureStorageShare](./Remove-AzureStorageShare.md)
