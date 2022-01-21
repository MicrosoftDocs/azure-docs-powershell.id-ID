---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxStorageAccountDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxStorageAccountDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxStorageAccountDetailsObject.md
ms.openlocfilehash: 0383c2e0000b7b6316cc7ed3cd197e90a9e09d16
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136583744"
---
# New-AzDataBoxStorageAccountDetailsObject

## SYNOPSIS
Buat objek dalam memori untuk StorageAccountDetails.

## SYNTAX

```
New-AzDataBoxStorageAccountDetailsObject -DataAccountType <DataAccountType> -StorageAccountId <String>
 [-SharePassword <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk StorageAccountDetails.

## EXAMPLES

### Contoh 1: Storage objek dalam memori akun 
```powershell
PS C:\> $dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
PS C:\> $dataAccount

DataAccountType SharePassword StorageAccountId
--------------- ------------- ----------------
StorageAccount                /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName
```

Storage objek dalam memori

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

