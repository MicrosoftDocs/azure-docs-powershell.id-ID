---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 10D5B7E0-242B-4DC0-A527-8F6388E72E0A
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragecontainerstoredaccesspolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageContainerStoredAccessPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageContainerStoredAccessPolicy.md
ms.openlocfilehash: 4a2c4603679b86853fa9c6f0c6bdb2cddb1e2fff
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144668608"
---
# Get-AzStorageContainerStoredAccessPolicy

## SYNOPSIS
Mendapatkan kebijakan atau kebijakan akses tersimpan untuk kontainer penyimpanan Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/get-azstoragecontainerstoredaccesspolicy) untuk informasi terbaru.

## SYNTAX

```
Get-AzStorageContainerStoredAccessPolicy [-Container] <String> [[-Policy] <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageContainerStoredAccessPolicy** mencantumkan kebijakan atau kebijakan akses tersimpan untuk kontainer penyimpanan Azure.

## EXAMPLES

### Contoh 1: Mendapatkan kebijakan akses tersimpan dalam kontainer penyimpanan
```
PS C:\>Get-AzStorageContainerStoredAccessPolicy -Container "Container07" -Policy "Policy22"
```

Perintah ini mendapatkan kebijakan akses bernama Policy22 dalam kontainer penyimpanan bernama Container07.

### Contoh 2: Mendapatkan semua kebijakan akses tersimpan dalam kontainer penyimpanan
```
PS C:\>Get-AzStorageContainerStoredAccessPolicy -Container "Container07"
```

Perintah ini mendapatkan semua kebijakan akses dalam kontainer penyimpanan bernama Container07.

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

### -Kontainer
Menentukan nama kontainer penyimpanan Azure Anda.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Context
Menentukan konteks penyimpanan Azure.

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

### -Kebijakan
Menentukan kebijakan akses tersimpan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.Azure. Storage. Blob.SharedAccessBlobPolicy

## NOTES

## RELATED LINKS

[New-AzStorageContainerStoredAccessPolicy](./New-AzStorageContainerStoredAccessPolicy.md)

[Remove-AzStorageContainerStoredAccessPolicy](./Remove-AzStorageContainerStoredAccessPolicy.md)

[Set-AzStorageContainerStoredAccessPolicy](./Set-AzStorageContainerStoredAccessPolicy.md)


