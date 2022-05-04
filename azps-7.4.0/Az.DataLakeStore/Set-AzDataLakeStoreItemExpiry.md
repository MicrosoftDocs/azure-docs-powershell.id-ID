---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeStore.dll-Help.xml
Module Name: Az.DataLakeStore
online version: https://docs.microsoft.com/powershell/module/az.datalakestore/set-azdatalakestoreitemexpiry
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Set-AzDataLakeStoreItemExpiry.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Set-AzDataLakeStoreItemExpiry.md
ms.openlocfilehash: a35df4aeb304f28f066d3e931822213804190361
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144585632"
---
# Set-AzDataLakeStoreItemExpiry

## SYNOPSIS
Mengatur atau menghapus waktu kedaluwarsa untuk file di akun Azure Data Lake Store.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datalakestore/set-azdatalakestoreitemexpiry) untuk informasi terbaru.

## SYNTAX

### SetAbsoluteNeverExpireExpiry (Default)
```
Set-AzDataLakeStoreItemExpiry [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [[-Expiration] <DateTimeOffset>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetRelativeExpiry
```
Set-AzDataLakeStoreItemExpiry [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-RelativeFileExpiryOption] <PathRelativeExpiryOptions> [[-RelativeTime] <Int64>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzDataLakeStoreItemExpiry** mengatur atau menghapus waktu kedaluwarsa untuk file di akun Azure Data Lake Store.

## EXAMPLES

### Contoh 1: Mengatur waktu kedaluwarsa untuk file
```powershell
Set-AzDataLakeStoreItemExpiry -AccountName "ContosoADL" -Path /myfile.txt -Expiration [DateTimeOffset]::Now.AddHours(2)
```

Mengatur kedaluwarsa pada file myfile.txt di akun ContosoADL menjadi dua jam dari sekarang.
Ini akan menyebabkan file kedaluwarsa (ditandai untuk dihapus) dalam dua jam.

### Contoh 2: Menghapus kedaluwarsa pada file
```powershell
Set-AzDataLakeStoreItemExpiry -AccountName "ContosoADL" -Path /myfile.txt
```

Menghapus kedaluwarsa yang sebelumnya diatur pada file 'myfile.txt' di akun 'ContosoADL'.
Ini berarti file tidak akan kedaluwarsa secara otomatis (ditandai untuk dihapus) dan harus dihapus secara manual atau diatur untuk kedaluwarsa lagi.

### Contoh 3: Mengatur waktu kedaluwarsa untuk file relatif terhadap sekarang
```powershell
Set-AzDataLakeStoreItemExpiry -Account "ContosoADL" -path /myfile.txt -RelativeFileExpiryOption RelativeToNow -RelativeTime 240000
Set-AzDataLakeStoreItemExpiry -Account "ContosoADL" -path /myfile.txt -RelativeFileExpiryOption RelativeToCreationDate -RelativeTime 240000
```

Perintah pertama mengatur waktu kedaluwarsa file /myfile.txt 240 detik relatif terhadap waktu saat ini di server.
Perintah kedua mengatur waktu kedaluwarsa file /myfile.txt 240 detik relatif terhadap waktu pembuatan di server.

## PARAMETERS

### -Akun
Menentukan nama akun Data Lake Store.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kedaluwarsa
Waktu kedaluwarsa absolut untuk file yang ditentukan.
Jika tidak ada nilai atau diatur ke MaxValue, file tidak akan pernah kedaluwarsa.

```yaml
Type: System.DateTimeOffset
Parameter Sets: SetAbsoluteNeverExpireExpiry
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur Data Lake Store dari item file yang akan diatur atau dihapus kedaluwarsanya.

```yaml
Type: Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RelativeFileExpiryOption
Opsi kedaluwarsa relatif. RelativeToNow atau RelativeToCreationDate adalah opsi saat ini

```yaml
Type: Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreEnums+PathRelativeExpiryOptions
Parameter Sets: SetRelativeExpiry
Aliases:
Accepted values: RelativeToNow, RelativeToCreationDate

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RelativeTime
Waktu relatif dalam milidetik sehubungan dengan sekarang atau waktu pembuatan

```yaml
Type: System.Int64
Parameter Sets: SetRelativeExpiry
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance

### System.DateTimeOffset

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreEnums+PathRelativeExpiryOptions

### System.Int64

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreItem

## NOTES
Alias: Set-AdlStoreItemExpiry

## RELATED LINKS

[Get-AzDataLakeStoreItem](./Get-AzDataLakeStoreItem.md)

