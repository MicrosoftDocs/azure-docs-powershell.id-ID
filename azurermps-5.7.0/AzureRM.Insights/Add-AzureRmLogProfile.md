---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: 18D5B95E-4CF1-4C79-AE8B-9F4DA49B46A9
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.insights/add-azurermlogprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Add-AzureRmLogProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Add-AzureRmLogProfile.md
ms.openlocfilehash: 0ef53015b3e07eeb69cdcfd0ab70c67317ab92cd
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422639"
---
# Add-AzureRmLogProfile

## SYNOPSIS
Membuat profil log aktivitas baru. Profil ini digunakan untuk mengarsipkan log aktivitas ke akun penyimpanan Azure atau melakukan streaming ke hub aktivitas Azure dalam langganan yang sama. 

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmLogProfile -Name <String> [-StorageAccountId <String>] [-ServiceBusRuleId <String>]
 [-RetentionInDays <Int32>] -Location <System.Collections.Generic.List`1[System.String]>
 [-Category <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmLogProfile** membuat profil log.

- **Storage -** Hanya akun penyimpanan standar (akun penyimpanan premium tidak didukung) yang didukung. Dapat berupa tipe ARM atau Klasik. Jika log masuk ke akun penyimpanan, biaya penyimpanan log aktivitas ditagih sesuai tarif penyimpanan standar normal. Mungkin hanya ada satu profil log per langganan secara konsekuensial, hanya satu akun penyimpanan per langganan yang dapat digunakan untuk mengekspor log aktivitas. 

- **Hub Kejadian** - Hanya ada satu profil log per langganan secara konsekuensial, hanya satu hub acara per langganan yang dapat digunakan untuk mengekspor log aktivitas. Jika log aktivitas di-streaming ke hub acara, harga hub acara standar akan berlaku. 

Dalam log aktivitas, acara dapat terkait dengan kawasan atau dapat menjadi "Global". Global pada dasarnya berarti acara ini adalah agnostik kawasan dan terpisah oleh kawasan, bahkan mayoritas acara termasuk dalam kategori ini. Jika profil log aktivitas diatur dari portal, profil secara implisit menambahkan "Global" bersama dengan kawasan lain yang dipilih dalam antarmuka pengguna. Saat menggunakan cmdlet, lokasi sebagai "Global" harus disebutkan secara eksplisit terlepas dari kawasan lain. 

**Catatan** :- **Gagal menetapkan "Global"** di lokasi akan mengakibatkan sebagian besar log aktivitas tidak diekspor. 

Cmdlet ini menerapkan pola ShouldProcess, misalnya meminta konfirmasi dari pengguna sebelum benar-benar membuat, mengubah, atau menghapus sumber daya.

## EXAMPLES

### Contoh 1 : Menambahkan profil log baru untuk mengekspor log aktivitas yang sesuai dengan kondisi lokasi ke akun penyimpanan
```
Add-AzureRmLogProfile -Locations "Global","West US" -Name ExportLogProfile -StorageAccountId /subscriptions/40gpe80s-9sb7-4f07-9042-b1b6a92ja9fk/resourceGroups/activitylogRG/providers/Microsoft.Storage/storageAccounts/activitylogstorageaccount
```

## PARAMETERS

### -Kategori
Menentukan daftar kategori.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: Categories

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi profil log.
Nilai yang valid: Jalankan di bawah cmdlet untuk mendapatkan daftar lokasi terbaru. 

Get-AzureLocation | Pilih DisplayName

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: Locations

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama profil.

```yaml
Type: String
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
Type: Int32
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountId
Menentukan ID akun Storage anda. ID adalah ID Sumber Daya yang sepenuhnya memenuhi syarat dari akun penyimpanan, misalnya  

/subscriptions/40gpe80s-9sb7-4f07-9042-b1b6a92ja9fk/resourceGroups/activitylogRG/providers/Microsoft. Storage/storageAccounts/activitylogstorageaccount

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSLogProfile

## CATATAN

## RELATED LINKS

[Get-AzureRmLogProfile](./Get-AzureRmLogProfile.md)

[Remove-AzureRmLogProfile](./Remove-AzureRmLogProfile.md)


