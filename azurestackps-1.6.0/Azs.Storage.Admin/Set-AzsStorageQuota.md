---
external help file: Azs.Storage.Admin-help.xml
Module Name: Azs.Storage.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 53978a97aae55c61fb0ec314175ad18f9ef8792564a3f591a3b752d7d9e4eb07
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416080"
---
# Set-AzsStorageQuota

## SYNOPSIS
Buat atau perbarui kuota penyimpanan yang sudah ada.

## SYNTAX

### Pembaruan (Default)
```
Set-AzsStorageQuota -Name <String> [-CapacityInGb <Int32>] [-NumberOfStorageAccounts <Int32>]
 [-Location <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
Set-AzsStorageQuota [-CapacityInGb <Int32>] [-NumberOfStorageAccounts <Int32>] -ResourceId <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-AzsStorageQuota [-CapacityInGb <Int32>] [-NumberOfStorageAccounts <Int32>] -InputObject <StorageQuota>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Buat atau perbarui kuota penyimpanan yang sudah ada.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Set-AzsStorageQuota -Name 'TestUpdateStorageQuota' -CapacityInGb 123 -NumberOfStorageAccounts 10
```

Memperbarui kuota penyimpanan yang sudah ada.

## PARAMETERS

### -CapacityInGb
Kapasitas maxium (GB).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Kuota penyimpanan yang dimodifikasi posbbily dikembalikan oleh Get-AzsStorageQuota.

```yaml
Type: StorageQuota
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

```yaml
Type: String
Parameter Sets: Update
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kuota penyimpanan.

```yaml
Type: String
Parameter Sets: Update
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfStorageAccounts
Total jumlah akun penyimpanan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: String
Parameter Sets: ResourceId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management. Storage. Admin.Models.StorageQuota

## CATATAN

## RELATED LINKS

