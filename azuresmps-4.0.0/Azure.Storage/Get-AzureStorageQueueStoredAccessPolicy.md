---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: F1EC601C-3ADD-402A-A5F7-84A95D312187
online version: ''
schema: 2.0.0
ms.openlocfilehash: 20115f704707a47e564228efe838a3e7e7d7d426
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142786744"
---
# Get-AzureStorageQueueStoredAccessPolicy

## SYNOPSIS
Mendapatkan kebijakan atau kebijakan akses yang disimpan untuk antrean penyimpanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorageQueueStoredAccessPolicy [-Queue] <String> [[-Policy] <String>] [-Context <IStorageContext>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageQueueStoredAccessPolicy** mencantumkan kebijakan atau kebijakan akses yang disimpan untuk antrean penyimpanan Azure.

## EXAMPLES

### Contoh 1: Dapatkan kebijakan akses yang disimpan dalam antrean
```
PS C:\>Get-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue" -Policy "Policy12"
```

Perintah ini mendapatkan kebijakan akses bernama Policy12 dalam antrean penyimpanan bernama Antrean Saya.

### Contoh 2: Dapatkan semua kebijakan akses yang disimpan dalam antrean
```
PS C:\>Get-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue"
```

Perintah ini mendapatkan semua kebijakan akses yang disimpan dalam antrean bernama Antrean Saya.

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

### -Antrean
Menentukan nama antrean penyimpanan Azure.

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

[New-AzureStorageQueueStoredAccessPolicy](./New-AzureStorageQueueStoredAccessPolicy.md)

[Remove-AzureStorageQueueStoredAccessPolicy](./Remove-AzureStorageQueueStoredAccessPolicy.md)

[Set-AzureStorageQueueStoredAccessPolicy](./Set-AzureStorageQueueStoredAccessPolicy.md)

[AzureStorageContext baru](./New-AzureStorageContext.md)


