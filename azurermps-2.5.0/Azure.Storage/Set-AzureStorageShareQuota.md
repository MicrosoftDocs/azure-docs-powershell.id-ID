---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: 176294FA-BB08-4A63-AD45-1E6C6D67A5D8
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/set-azurestoragesharequota
schema: 2.0.0
ms.openlocfilehash: 3d2fd2ae65ff343bbe5faeece41194c768bec8c9
ms.sourcegitcommit: ea4f0db405efec935ac72601b51807dbb45674c9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/28/2022
ms.locfileid: "140851626"
---
# Set-AzureStorageShareQuota

## SYNOPSIS
Mengatur kapasitas penyimpanan untuk sebuah berbagi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ShareName
```
Set-AzureStorageShareQuota [-ShareName] <String> [-Quota] <Int32> [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### Bagikan
```
Set-AzureStorageShareQuota [-Share] <CloudFileShare> [-Quota] <Int32> [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorageShareQuota** mengatur kapasitas penyimpanan untuk berbagi tertentu.

## EXAMPLES

### Contoh 1: Mengatur kapasitas penyimpanan berbagi
```
PS C:\>Set-AzureStorageShareQuota -ShareName "ContosoShare01" -Quota 1024
```

Perintah ini mengatur kapasitas penyimpanan untuk berbagi bernama ContosoShare01 menjadi 1024 GB.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet [New-AzureStorageContext](./New-AzureStorageContext.md) .

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: ShareName
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

### -Quota
Menentukan nilai kuota dalam gigabyte (GB).
Lihat batasan kuota dalam https://docs.microsoft.com/en-us/azure/azure-subscription-service-limits#azure-files-limits. 

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan lamanya periode waktu habis untuk bagian server dari permintaan.

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

### -Bagikan
Menentukan objek **CloudFileShare** untuk mewakili berbagi di mana cmdlet ini menetapkan kuota.
Untuk mendapatkan objek **CloudFileShare** , gunakan cmdlet Get-AzureStorageShare tersebut.

```yaml
Type: Microsoft.WindowsAzure.Storage.File.CloudFileShare
Parameter Sets: Share
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ShareName
Menentukan nama berbagi file yang akan ditetapkan kuotanya.

```yaml
Type: System.String
Parameter Sets: ShareName
Aliases: N, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.WindowsAzure. Storage. File.CloudFileShare
Parameter: Berbagi (ByValue)

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure. Storage. File.FileShareProperties

## CATATAN

## RELATED LINKS

[Get-AzureStorageFileContent](./Get-AzureStorageFileContent.md)

[Get-AzureStorageShare](./Get-AzureStorageShare.md)

[New-AzureStorageContext](./New-AzureStorageContext.md)
