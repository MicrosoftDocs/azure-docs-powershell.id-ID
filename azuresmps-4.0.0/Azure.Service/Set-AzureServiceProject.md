---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D0A2B454-7BFF-4D4D-8A85-FDB47249758F
online version: ''
schema: 2.0.0
ms.openlocfilehash: 858506bfe1178d1c858a38eb71ed6462e7f5d115
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915733"
---
# Set-AzureServiceProject

## SYNOPSIS
Mengatur akun lokasi, langganan, slot, dan penyimpanan default untuk layanan saat ini.

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

Mengatur lokasi penyebaran untuk layanan ke kawasan North Central US.
Mengatur slot penyebaran ke Produksi. Mengatur akun penyimpanan yang akan digunakan untuk tahap definisi layanan ke myStorageAccount.
Mengatur langganan yang akan menghosting layanan ke mySubscription.
Setiap kali layanan diterbitkan ke awan, layanan akan dihosting di pusat data di kawasan North Central US, layanan akan memperbarui slot penyebaran, dan akan menggunakan akun langganan dan penyimpanan yang ditentukan.

## PARAMETERS

### -Lokasi
Kawasan tempat layanan akan dihosting.
Nilai ini digunakan setiap kali layanan diterbitkan ke awan.
Nilai yang memungkinkan adalah: Di mana saja Asia, Di mana saja Eropa, Di mana saja AS, Asia Timur, AS Timur, Amerika Tengah Utara, Eropa Utara, AS Tengah Selatan, Asia Tenggara, Eropa Barat, AS Barat.

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
Menunjukkan bahwa cmdlet ini mengembalikan objek yang mewakili item tempatnya beroperasi.
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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Slot (produksi atau pementasan) tempat layanan akan dihosting.
Nilai ini digunakan setiap kali layanan diterbitkan ke awan.
Nilai yang memungkinkan adalah: Produksi, Pementasan.

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
Akun penyimpanan yang akan digunakan saat mengunggah paket layanan ke awan.
Jika akun penyimpanan tidak ada, akun penyimpanan akan dibuat saat layanan diterbitkan ke awan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* node-dev, php-dev, python-dev

## RELATED LINKS

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Publish-AzureServiceProject](./Publish-AzureServiceProject.md)

[Set-AzureServiceProjectRole](./Set-AzureServiceProjectRole.md)


