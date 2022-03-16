---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/get-azedgeorderconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderConfiguration.md
ms.openlocfilehash: 76f5771745e6ae563646946592843ac62effe60c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140004006"
---
# Get-AzEdgeOrderConfiguration

## SYNOPSIS
Metode ini menyediakan daftar konfigurasi untuk keluarga produk, lini produk, dan produk tertentu di bawah langganan.

## SYNTAX

```
Get-AzEdgeOrderConfiguration -ConfigurationFilter <IConfigurationFilters[]> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Metode ini menyediakan daftar konfigurasi untuk keluarga produk, lini produk, dan produk tertentu di bawah langganan.

## EXAMPLES

### Contoh 1: Dapatkan detail konfigurasi
```powershell
PS C:\> $configuration = Get-AzEdgeOrderConfiguration -SubscriptionId SubscriptionId -ConfigurationFilter @(@{"HierarchyInformation"=$HierarchyInformation; "FilterableProperty"= @($filterableProperty)})
PS C:\> $filterableProperty = New-AzEdgeOrderFilterablePropertyObject -Type "ShipToCountries" -SupportedValue @("US")
PS C:\> $HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
PS C:\> $configuration = Get-AzEdgeOrderConfiguration -SubscriptionId SubscriptionId -ConfigurationFilter @(@{"HierarchyInformation"=$HierarchyInformation; "FilterableProperty"= @($filterableProperty)})
PS C:\> $configuration

AvailabilityInformationAvailabilityStage     : Available
AvailabilityInformationDisabledReason        : None
AvailabilityInformationDisabledReasonMessage :
CostInformationBillingInfoUrl                : https://aka.ms/edgeHWcenter-pricinglink-custom
CostInformationBillingMeterDetail            : {RentalFee, ShippingFee}
DescriptionAttribute                         : {}
DescriptionKeyword                           : {GPU}
DescriptionLink                              : {}
DescriptionLongDescription                   :
DescriptionShortDescription                  :
DescriptionType                              : Base
DimensionDepth                               : 2
DimensionHeight                              : 15
DimensionLength                              : 50
DimensionLengthHeightUnit                    : IN
DimensionWeight                              : 50
DimensionWeightUnit                          : LBS
DimensionWidth                               : 5
DisplayName                                  : Azure Stack Edge Pro - 2 GPU
FilterableProperty                           : {Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.FilterableProperty}
HierarchyInformation                         : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.HierarchyInformation
ImageInformation                             : {}
Specification                                : {Usable compute, Usable memory, Usable storage}
```

Perintah ini mendapatkan wawasan tentang konfigurasi yang dipilih.
Pastikan Anda menjalankan registerProvider di Microsoft.EdgeOrder sebelum menjalankan perintah ini.

## PARAMETERS

### -ConfigurationFilter
Berisi detail tentang informasi hierarki produk dan properti yang dapat difilter.
Untuk membuat, lihat bagian CATATAN untuk properti CONFIGURATIONFILTER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IConfigurationFilters[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IConfiguration

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONFIGURATIONFILTER <IConfigurationFilters[]>: Berisi detail tentang informasi hierarki produk dan properti yang dapat difilter.
  - `HierarchyInformation <IHierarchyInformation>`: Informasi hierarki produk
    - `[ConfigurationName <String>]`: Mewakili nama konfigurasi yang mengidentifikasi konfigurasi secara unik
    - `[ProductFamilyName <String>]`: Mewakili nama produk keluarga yang mengidentifikasi keluarga produk secara unik
    - `[ProductLineName <String>]`: Mewakili nama baris produk yang mengidentifikasi lini produk secara unik
    - `[ProductName <String>]`: Mewakili nama produk yang mengidentifikasi produk secara unik
  - `[FilterableProperty <IFilterableProperty[]>]`: Memfilter khusus produk
    - `SupportedValue <String[]>`: Nilai yang akan difilter.
    - `Type <SupportedFilterTypes>`: Tipe filter produk.

CUSTOMERSUBSCRIPTIONDETAIL <ICustomerSubscriptionDetails>: Properti langganan pelanggan. Klien dapat menampilkan produk yang tersedia untuk pelanggan yang tidak terdaftar dengan memberikan detail langganan secara eksplisit
  - `QuotaId <String>`: ID kuota langganan
  - `[LocationPlacementId <String>]`: Id penempatan lokasi langganan
  - `[RegisteredFeature <ICustomerSubscriptionRegisteredFeatures[]>]`: Daftar bendera fitur terdaftar untuk langganan
    - `[Name <String>]`: Nama fitur langganan terdaftar
    - `[State <String>]`: Status fitur langganan terdaftar

## RELATED LINKS

