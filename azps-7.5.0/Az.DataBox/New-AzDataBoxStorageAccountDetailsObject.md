---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxStorageAccountDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxStorageAccountDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxStorageAccountDetailsObject.md
ms.openlocfilehash: 203058b2785e2d6c36d9f310caebfd5123a6585d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205055"
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
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$dataAccount
```

```output
DataAccountType SharePassword StorageAccountId
--------------- ------------- ----------------
StorageAccount                /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName
```

Storage objek dalam memori akun

## PARAMETERS

### -DataAccountType
Jenis Akun data yang akan ditransfer.

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
Kata sandi untuk semua berbagi yang akan dibuat pada perangkat.
Tidak boleh diteruskan untuk pekerjaan TransferType:ExportFromAzure.
Jika ini tidak diteruskan, layanan akan menghasilkan kata sandi itu sendiri.
Ini tidak akan dikembalikan di Dapatkan Panggilan.
Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimum 64 karakter.
Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus.
Kata sandi tidak boleh memiliki karakter berikut : Kata Sandi IilLoO0 hanya boleh memiliki alfabet, angka dan karakter ini : @#\-$%^!+=;:_()]+.

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
id Sumber Daya Akun Storage.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.StorageAccountDetails

## NOTES

ALIAS

## RELATED LINKS

