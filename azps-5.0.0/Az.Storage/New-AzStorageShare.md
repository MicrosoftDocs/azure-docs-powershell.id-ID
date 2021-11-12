---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: FCDCEF0B-6E2C-480E-9841-EF4E64D61D54
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/new-azstorageshare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/New-AzStorageShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/New-AzStorageShare.md
ms.openlocfilehash: 4fa89a13f9b4124232d9459d7d3eff54a6f55a5c
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409903"
---
# New-AzStorageShare

## SYNOPSIS
Membuat berbagi file.

## SINTAKS

```
New-AzStorageShare [-Name] <String> [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzStorageShare** membuat berbagi file.

## CONTOH

### Contoh 1: Membuat berbagi file
```
PS C:\>New-AzStorageShare -Name "ContosoShare06"
```

Perintah ini membuat berbagi file bernama ContosoShare06.

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
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet [New-AzStorageContext.](./New-AzStorageContext.md)

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

### -Nama
Menentukan nama berbagi file.
Cmdlet ini membuat berbagi file yang memiliki nama yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan lamanya periode waktu habis untuk bagian server dari permintaan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUT

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageFileShare

## CATATAN

## LINK TERKAIT

[Get-AzStorageShare](./Get-AzStorageShare.md)

[New-AzStorageContext](./New-AzStorageContext.md)

[Remove-AzStorageShare](./Remove-AzStorageShare.md)
