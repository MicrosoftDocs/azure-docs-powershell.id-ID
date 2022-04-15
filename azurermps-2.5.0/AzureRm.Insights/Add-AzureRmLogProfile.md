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
ms.lasthandoff: 04/14/2022
ms.locfileid: "142362563"
---
# Add-AzureRmLogProfile

## SYNOPSIS
Membuat profil log aktivitas baru. Profil ini digunakan untuk mengarsipkan log aktivitas ke akun penyimpanan Azure atau streaming ke hub kejadian Azure dalam langganan yang sama. 

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
- **akun Storage** - Hanya akun penyimpanan standar (akun penyimpanan premium tidak didukung) yang didukung. Ini bisa berupa tipe ARM atau Classic. Jika log masuk ke akun penyimpanan, biaya penyimpanan log aktivitas akan ditagih dengan tarif penyimpanan standar normal. Mungkin hanya ada satu profil log per langganan yang mungkin hanya satu akun penyimpanan per langganan yang dapat digunakan untuk mengekspor log aktivitas. 
- **Hub Kejadian** - Mungkin hanya ada satu profil log per langganan secara bertahap hanya satu hub kejadian per langganan yang dapat digunakan untuk mengekspor log aktivitas. Jika log aktivitas di-streaming ke hub kejadian, harga hub kejadian standar akan berlaku. Dalam log aktivitas, kejadian dapat berkaitan dengan kawasan atau dapat berupa "Global". Global pada dasarnya berarti acara ini adalah agnostik kawasan dan independen dari kawasan, pada kenyataannya mayoritas acara termasuk dalam kategori ini. Jika profil log aktivitas diatur dari portal, profil log aktivitas secara implisit menambahkan "Global" bersama dengan kawasan lain yang dipilih di antarmuka pengguna. Ketika menggunakan cmdlet, lokasi sebagai "Global" harus secara eksplisit disebutkan selain dari kawasan lain. 
**Catatan** :- **Gagal mengatur "Global" di lokasi akan mengakibatkan sebagian besar log aktivitas tidak diekspor.** Cmdlet ini menerapkan pola ShouldProcess, yaitu mungkin meminta konfirmasi dari pengguna sebelum benar-benar membuat, mengubah, atau menghapus sumber daya.

## EXAMPLES

### Contoh 1 : Menambahkan profil log baru untuk mengekspor log aktivitas yang sesuai dengan kondisi lokasi ke akun penyimpanan
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
Menentukan kebijakan penyimpanan, dalam hari. Ini adalah jumlah hari log dipertahankan dalam akun penyimpanan yang ditentukan. Untuk mempertahankan data yang selamanya diatur ke **0**. Jika tidak ditentukan, defaultnya adalah **0**. Tarif penagihan hub aktivitas atau penyimpanan standar normal akan berlaku untuk penyimpanan data.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSLogProfile

## CATATAN

## RELATED LINKS

[Get-AzureRmLogProfile](./Get-AzureRmLogProfile.md)

[Hapus-AzureRmLogProfile](./Remove-AzureRmLogProfile.md)


