---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D0A2B454-7BFF-4D4D-8A85-FDB47249758F
online version: ''
schema: 2.0.0
ms.openlocfilehash: 858506bfe1178d1c858a38eb71ed6462e7f5d115
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426257"
---
# Set-AzureServiceProject

## SYNOPSIS
Mengatur lokasi default, langganan, slot, dan akun penyimpanan untuk layanan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Set-AzureServiceProject [-Location <String>] [-Slot <String>] [-Storage <String>] [-PassThru]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureServiceProject** mengatur lokasi penyebaran, slot, akun penyimpanan, dan langganan untuk layanan saat ini.
Nilai ini digunakan setiap kali layanan diterbitkan ke awan.

## EXAMPLES

### Contoh 1: Pengaturan dasar
```
PS C:\> Set-AzureServiceProject -Location "North Central US" -Slot Production -Storage myStorageAccount -Subscription myAzureSubscription
```

Mengatur lokasi penyebaran untuk layanan ke kawasan Amerika Tengah Utara.
Mengatur slot penyebaran ke Produksi. Mengatur akun penyimpanan yang akan digunakan untuk menentukan definisi layanan pada myStorageAccount.
Mengatur langganan yang akan menghosting layanan ke langganan langganan saya.
Setiap kali diterbitkan ke awan, layanan akan dihosting di pusat data di kawasan AS Tengah Utara, aplikasi akan memperbarui slot penyebaran, dan akan menggunakan akun langganan dan penyimpanan yang ditentukan.

## PARAMETERS

### -Lokasi
Kawasan tempat layanan akan dihosting.
Nilai ini digunakan setiap kali layanan diterbitkan ke awan.
Nilai yang memungkinkan adalah: Asia Anywhere, Anywhere Europe, Anywhere US, Asia Timur, AS Timur, AS Tengah Utara, Eropa Utara, AS Tengah Selatan, Asia Tenggara, Eropa Barat, AS Barat.

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

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan objek yang mewakili item tempat operasinya.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Slot (produksi atau peresnjang) tempat layanan akan dihosting.
Nilai ini digunakan setiap kali layanan diterbitkan ke awan.
Nilai yang mungkin adalah: Produksi, Pementasan.

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

### -Storage
Akun penyimpanan yang akan digunakan saat mengunggah paket layanan ke cloud.
Jika akun penyimpanan tidak ada, akun akan dibuat saat layanan diterbitkan ke awan.

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

## OUTPUTS

## CATATAN
* node-dev, php-dev, python-dev

## RELATED LINKS

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Publish-AzureServiceProject](./Publish-AzureServiceProject.md)

[Set-AzureServiceProjectRole](./Set-AzureServiceProjectRole.md)


