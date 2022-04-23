---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 793037C4-8FE5-4799-B59B-94C1605D9F4E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 433ef847864a799614c6cb1def5e2fa82d303a86
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143042576"
---
# New-AzureStoreAddOn

## SYNOPSIS
Membeli contoh add-on baru.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStoreAddOn -Name <String> -AddOn <String> -Plan <String> -Location <String> [-PromotionCode <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Membeli instans add-on baru dari Azure Store.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzureStoreAddOn -Name MyAddOn -AddOn AddonId -Plan PlanId -Location "West US"
```

Contoh ini membeli add-on bernama MyAddOn dengan PlanId di lokasi AS Barat.

### Contoh 2
```
PS C:\> New-AzureStoreAddOn -Name MyAddOn -AddOn AddonId -Plan PlanId -Location "West US" -PromotionCode MyPromoCode
```

Contoh ini menggunakan kode promosi untuk membeli add-on.

## PARAMETERS

### -Add-On
Menentukan ID add-on.

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

### -Lokasi
Menentukan lokasi instans add-on.

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

### -Nama
Menentukan nama instans add-on.

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

### -Rencana
Menentukan ID rencana.

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

### -PromotionCode
Menentukan kode promosi untuk diterapkan pada pembelian.

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

## RELATED LINKS

[Get-AzureStoreAddOn](./Get-AzureStoreAddOn.md)

[Hapus-AzureStoreAddOn](./Remove-AzureStoreAddOn.md)

[Set-AzureStoreAddOn](./Set-AzureStoreAddOn.md)


