---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxManagedDiskDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxManagedDiskDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxManagedDiskDetailsObject.md
ms.openlocfilehash: a8183e75d3486f4aa2fa82d4becdfc87ae4361d4
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136560952"
---
# New-AzDataBoxManagedDiskDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk ManagedDiskDetails.

## SYNTAX

```
New-AzDataBoxManagedDiskDetailsObject -DataAccountType <DataAccountType> -ResourceGroupId <String>
 -StagingStorageAccountId <String> [-SharePassword <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ManagedDiskDetails.

## EXAMPLES

### Contoh 1: Objek ManagedDisk 
```powershell
PS C:\> $managedDiskAccount=New-AzDataBoxManagedDiskDetailsObject -ResourceGroupId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName" -StagingStorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/stagingAccountName" -DataAccountType "ManagedDisk"
```

Membuat objek disk yang dikelola dalam memori

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

### -ResourceGroupId
Id Grup Sumber Daya dari disk perhitungan.

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

### -StagingStorageAccountId
Id Sumber Daya dari akun penyimpanan yang bisa digunakan untuk menyalin vhd untuk pengembangan.

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

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ManagedDiskDetails

## CATATAN

ALIAS

## RELATED LINKS

