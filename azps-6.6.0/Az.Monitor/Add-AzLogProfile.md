---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 18D5B95E-4CF1-4C79-AE8B-9F4DA49B46A9
online version: https://docs.microsoft.com/powershell/module/az.monitor/add-azlogprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Add-AzLogProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Add-AzLogProfile.md
ms.openlocfilehash: 72039317361f803bc554fab3d0c34debe7f6671f
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136365609"
---
# Add-AzLogProfile

## SYNOPSIS
Membuat profil log aktivitas baru. Profil ini digunakan untuk mengarsipkan log aktivitas ke akun penyimpanan Azure atau melakukan streaming ke hub aktivitas Azure dalam langganan yang sama. 

## SYNTAX

```
Add-AzLogProfile -Name <String> [-StorageAccountId <String>] [-ServiceBusRuleId <String>]
 [-RetentionInDays <Int32>] -Location <System.Collections.Generic.List`1[System.String]>
 [-Category <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzLogProfile** membuat profil log.
- **Storage Anda** - Hanya akun penyimpanan standar (akun penyimpanan premium tidak didukung) yang didukung. Dapat berupa tipe ARM atau Klasik. Jika log masuk ke akun penyimpanan, biaya penyimpanan log aktivitas ditagih sesuai tarif penyimpanan standar normal. Mungkin hanya ada satu profil log per langganan secara konsekuensial, hanya satu akun penyimpanan per langganan yang dapat digunakan untuk mengekspor log aktivitas. 
- **Hub Kejadian** - Hanya ada satu profil log per langganan secara konsekuensial, hanya satu hub acara per langganan yang dapat digunakan untuk mengekspor log aktivitas. Jika log aktivitas di-streaming ke hub acara, harga hub acara standar akan berlaku. Dalam log aktivitas, acara dapat terkait dengan kawasan atau dapat menjadi "Global". Global pada dasarnya berarti acara ini adalah agnostik kawasan dan terpisah dari kawasan, bahkan mayoritas acara termasuk dalam kategori ini. Jika profil log aktivitas diatur dari portal, profil secara implisit menambahkan "Global" bersama dengan kawasan lain yang dipilih dalam antarmuka pengguna. Saat menggunakan cmdlet, lokasi sebagai "Global" harus disebutkan secara eksplisit terlepas dari kawasan lain. 
**Catatan** :- **Gagal menetapkan "Global"** di lokasi akan mengakibatkan sebagian besar log aktivitas tidak diekspor. Cmdlet ini menerapkan pola ShouldProcess, misalnya meminta konfirmasi dari pengguna sebelum benar-benar membuat, mengubah, atau menghapus sumber daya.

## EXAMPLES

### Contoh 1: Menambahkan profil log baru untuk mengekspor log aktivitas yang sesuai dengan kondisi lokasi ke akun penyimpanan
```powershell
Add-AzLogProfile -Location "Global","West US" -Name ExportLogProfile -StorageAccountId /subscriptions/40gpe80s-9sb7-4f07-9042-b1b6a92ja9fk/resourceGroups/activitylogRG/providers/Microsoft.Storage/storageAccounts/activitylogstorageaccount
```

### Contoh 2

Membuat profil log aktivitas baru. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example --> 
Add-AzLogProfile -Location 'Global' -Name ExportLogProfile -RetentionInDays <Int32> -ServiceBusRuleId <String> -StorageAccountId /subscriptions/40gpe80s-9sb7-4f07-9042-b1b6a92ja9fk/resourceGroups/activitylogRG/providers/Microsoft.Storage/storageAccounts/activitylogstorageaccount
```

## PARAMETERS

### -Kategori
Menentukan daftar kategori.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Lokasi
Menentukan lokasi profil log.
Nilai yang valid: Jalankan di bawah cmdlet untuk mendapatkan daftar lokasi terbaru. Get-AzLocation | Pilih DisplayName

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama profil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionInDays
Menentukan kebijakan penyimpanan, dalam hari. Ini adalah jumlah hari log yang dipertahankan di akun penyimpanan yang ditentukan. Untuk mempertahankan data selamanya atur ke **0**. Jika tidak ditentukan, defaultnya adalah **0**. Tarif tagihan penyimpanan standar atau hub acara normal akan berlaku untuk penyimpanan data.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceBusRuleId
Menentukan ID aturan Bus Layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountId
Menentukan ID akun Storage Anda. ID adalah ID Sumber Daya yang sepenuhnya memenuhi syarat dari akun penyimpanan, misalnya  
/subscriptions/40gpe80s-9sb7-4f07-9042-b1b6a92ja9fk/resourceGroups/activitylogRG/providers/Microsoft. Storage/storageAccounts/activitylogstorageaccount

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Collections.Generic.List'1[[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSLogProfile

## CATATAN

## RELATED LINKS

[Get-AzLogProfile](./Get-AzLogProfile.md)

[Remove-AzLogProfile](./Remove-AzLogProfile.md)


