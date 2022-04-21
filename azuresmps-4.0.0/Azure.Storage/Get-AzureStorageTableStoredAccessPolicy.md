---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: BF5526C1-11B9-47A8-A5A6-CB275B470A9E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 94d19dcd4ebafa7a72b6d43ee42483c7a9cdd61c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142653603"
---
# Get-AzureStorageTableStoredAccessPolicy

## SYNOPSIS
Mendapatkan kebijakan atau kebijakan akses yang disimpan untuk tabel penyimpanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorageTableStoredAccessPolicy [-Table] <String> [[-Policy] <String>] [-Context <IStorageContext>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageTableStoredAccessPolicy** mencantumkan kebijakan atau kebijakan akses yang disimpan untuk tabel penyimpanan Azure.

## EXAMPLES

### Contoh 1: Mendapatkan kebijakan akses yang disimpan dalam tabel penyimpanan
```
PS C:\>Get-AzureStorageTableStoredAccessPolicy -Table "Table02" -Policy "Policy50"
```

Perintah ini mendapatkan kebijakan akses bernama Policy50 dalam tabel penyimpanan bernama Table02.

### Contoh 2: Dapatkan semua kebijakan akses yang disimpan dalam tabel penyimpanan
```
PS C:\>Get-AzureStorageTableStoredAccessPolicy -Table "Table02"
```

Perintah ini mendapatkan semua kebijakan akses dalam tabel bernama Table02.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzureStorageContext.

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

### -Kebijakan
Menentukan kebijakan akses yang disimpan, yang menyertakan izin untuk token Tanda Tangan Akses Bersama (SAS) ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Table
Menentukan nama tabel penyimpanan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageTableStoredAccessPolicy](./New-AzureStorageTableStoredAccessPolicy.md)

[Remove-AzureStorageTableStoredAccessPolicy](./Remove-AzureStorageTableStoredAccessPolicy.md)

[Set-AzureStorageTableStoredAccessPolicy](./Set-AzureStorageTableStoredAccessPolicy.md)

[AzureStorageContext baru](./New-AzureStorageContext.md)


