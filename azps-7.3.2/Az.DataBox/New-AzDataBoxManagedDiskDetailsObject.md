---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxManagedDiskDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxManagedDiskDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxManagedDiskDetailsObject.md
ms.openlocfilehash: 0a1bb7501e441b5faf61ab9f85ab6b5abb4ebb86
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142766512"
---
# New-AzDataBoxManagedDiskDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk ManagedDiskDetails.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databox/new-azdataboxmanageddiskdetailsobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataBoxManagedDiskDetailsObject -DataAccountType <DataAccountType> -ResourceGroupId <String>
 -StagingStorageAccountId <String> [-SharePassword <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ManagedDiskDetails.

## EXAMPLES

### Contoh 1: objek ManagedDisk 
```powershell
$managedDiskAccount=New-AzDataBoxManagedDiskDetailsObject -ResourceGroupId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName" -StagingStorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/stagingAccountName" -DataAccountType "ManagedDisk"
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
Id Grup Sumber Daya dari disk komputasi.

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
Kata sandi untuk semua pembagian yang akan dibuat di perangkat.
Tidak boleh dilewati untuk pekerjaan TransferType:ExportFromAzure.
Jika tidak lolos, layanan akan menghasilkan kata sandi itu sendiri.
Ini tidak akan dikembalikan di Dapatkan Panggilan.
Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter.
Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus.
Kata sandi tidak dapat memiliki karakter berikut: Kata sandi IilLoO0 hanya dapat memiliki alfabet, angka, dan karakter berikut : @#\-$%^!+=;:_()]+.

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
Id Sumber Daya dari akun penyimpanan yang dapat digunakan untuk menyalin vhd untuk pementasan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ManagedDiskDetails

## NOTES

ALIAS

## RELATED LINKS

