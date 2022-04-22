---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: 18D5B95E-4CF1-4C79-AE8B-9F4DA49B46A9
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.insights/add-azurermlogprofile
schema: 2.0.0
ms.openlocfilehash: 4302aa7dbc0cf31b9a7aa61678d871e9da140d51
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143053694"
---
# Add-AzureRmLogProfile

## SYNOPSIS
Membuat profil log aktivitas baru. Profil ini digunakan untuk mengarsipkan log aktivitas ke akun penyimpanan Azure atau mengalirkannya ke hub peristiwa Azure dalam langganan yang sama. 

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmLogProfile -Name <String> [-StorageAccountId <String>] [-ServiceBusRuleId <String>]
 [-RetentionInDays <Int32>] -Location <System.Collections.Generic.List`1[System.String]>
 [-Category <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmLogProfile** membuat profil log.
- **Akun Storage** - Hanya akun penyimpanan standar (akun penyimpanan premium yang tidak didukung) yang didukung. Ini bisa berjenis ARM atau Klasik. Jika dicatat ke akun penyimpanan, biaya penyimpanan log aktivitas ditagih dengan tarif penyimpanan standar normal. Mungkin hanya ada satu profil log per langganan akibatnya hanya satu akun penyimpanan per langganan yang dapat digunakan untuk mengekspor log aktivitas. 
- **Pusat Aktivitas** - Mungkin hanya ada satu profil log per langganan akibatnya hanya satu hub peristiwa per langganan yang dapat digunakan untuk mengekspor log aktivitas. Jika log aktivitas dialirkan ke pusat aktivitas, harga pusat aktivitas standar akan berlaku. Dalam log aktivitas, peristiwa dapat berkaitan dengan suatu wilayah atau dapat berupa "Global". Global pada dasarnya berarti peristiwa ini adalah agnostik wilayah dan independen dari wilayah, pada kenyataannya sebagian besar peristiwa termasuk dalam kategori ini. Jika profil log aktivitas diatur dari portal, profil tersebut secara implisit menambahkan "Global" bersama dengan wilayah lain yang dipilih di antarmuka pengguna. Saat menggunakan cmdlet , lokasi sebagai "Global" harus secara eksplisit disebutkan selain dari wilayah lain. 
**Catatan** :- **Gagal mengatur "Global" di lokasi akan mengakibatkan sebagian besar log aktivitas tidak diekspor.** Cmdlet ini mengimplementasikan pola ShouldProcess, yaitu mungkin meminta konfirmasi dari pengguna sebelum benar-benar membuat, memodifikasi, atau menghapus sumber daya.

## EXAMPLES

### Contoh 1 : Tambahkan profil log baru untuk mengekspor log aktivitas yang cocok dengan kondisi lokasi ke akun penyimpanan
```
Add-AzureRmLogProfile -Location "Global","West US" -Name ExportLogProfile -StorageAccountId /subscriptions/40gpe80s-9sb7-4f07-9042-b1b6a92ja9fk/resourceGroups/activitylogRG/providers/Microsoft.Storage/storageAccounts/activitylogstorageaccount
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
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
Nilai yang valid: Jalankan cmdlet di bawah ini untuk mendapatkan daftar lokasi terbaru. Get-AzureLocation | Pilih DisplayName

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

### -Name
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
Menentukan kebijakan penyimpanan, dalam hari. Ini adalah jumlah hari log dipertahankan di akun penyimpanan yang ditentukan. Untuk menyimpan data selamanya, atur ini ke **0**. Jika tidak ditentukan, maka defaultnya adalah **0**. Tarif penagihan penyimpanan standar atau hub peristiwa normal akan berlaku untuk retensi data.

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
Menentukan ID akun Storage. ID adalah ID Sumber Daya yang sepenuhnya memenuhi syarat dari akun penyimpanan misalnya  
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSLogProfile

## NOTES

## RELATED LINKS

[Get-AzureRmLogProfile](./Get-AzureRmLogProfile.md)

[Remove-AzureRmLogProfile](./Remove-AzureRmLogProfile.md)


