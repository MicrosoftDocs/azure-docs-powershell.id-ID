---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxStorageAccountDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxStorageAccountDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxStorageAccountDetailsObject.md
ms.openlocfilehash: 2cdf8c95b71beb47daa2d452a4a97ca6ca512e6b
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136347261"
---
# New-AzDataBoxStorageAccountDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk StorageAccountDetails

## SYNTAX

```
New-AzDataBoxStorageAccountDetailsObject -DataAccountType <DataAccountType> -StorageAccountId <String>
 [-SharePassword <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk StorageAccountDetails

## EXAMPLES

### Contoh 1: {{ {Storage account in-memory object }}
```powershell
PS C:\> $dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
PS C:\> $dataAccount

DataAccountType SharePassword StorageAccountId
--------------- ------------- ----------------
StorageAccount                /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName
```

{{ Storage objek dalam memori }}

## PARAMETERS

### -DataAccountType
Tipe Akun data yang akan ditransfer.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.DataAccountType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePassword
Kata sandi untuk semua berbagi akan dibuat pada perangkat.
Tidak dapat dialihkan untuk pekerjaan TransferType:ExportFromAzure.
Jika ini tidak lolos, layanan akan membuat kata sandi itu sendiri.
Ini tidak akan dikembalikan di Dapatkan Panggilan.
Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter.
Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu nomor dan satu karakter khusus.
Password tidak bisa memiliki karakter berikut: IilLoO0 Password hanya bisa memiliki alfabet, angka dan karakter ini: @# \- $%^!+=;:_()]+.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountId
Storage Sumber Daya Akun.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.StorageAccountDetails

## CATATAN

ALIAS

## RELATED LINKS

