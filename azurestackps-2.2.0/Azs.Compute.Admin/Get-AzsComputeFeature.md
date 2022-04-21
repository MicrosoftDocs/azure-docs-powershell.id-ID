---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/get-azscomputefeature
schema: 2.0.0
ms.openlocfilehash: 3e6a8b6bce970862bd7884e15842609ec0888154
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142721980"
---
# Get-AzsComputeFeature

## SYNOPSIS
Dapatkan fitur yang sudah ada.

## SYNTAX

### Daftar (Default)
```
Get-AzsComputeFeature [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzsComputeFeature -Name <String> [-Location <String>] [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsComputeFeature -INPUTOBJECT \<IComputeAdminIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan fitur yang sudah ada.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
Get-AzsComputeFeature -Location local -Name Microsoft.Compute.EmergencyVMAccess | ConvertTo-Json
```

{ "EnabledTenantSubscriptionId": [ "e9f233f4-6251-441e-a8e4-5e0165a5ff84", "a6293671-ca91-4040-8edc-5a5bc8bb10f2", "77df6e8d-c86b-4184-a7da-35217afdb7e8", "078fcd45-e064-4f1b-a546-f2873757c7c0", "88e0ade6-f94a-4a75-8b32-b8f07daf2ad0", "22c12f96-7352-4165-a7e4-ccebd1257f15", "a40a4cdf-0054-4b41-8692-0c0de49958b5", "d23289dc-887a-4e68-8c84-8a0e4d8dec51", "3f843028-3d49-4ae9-8185-148745b4a231" ], "FeatureName": "Microsoft.Compute.EmergencyVMAccess", " GlobalFeatureSettingGlobalFeatureState": {

                                               },
    "Id":  "/subscriptions/52cc3943-24b0-45bc-8403-466ccf5775a3/providers/Microsoft.Compute.Admin/locations/local/features/Microsoft.Compute.EmergencyVMAccess",
    "Location":  "local",
    "Name":  "Microsoft.Compute.EmergencyVMAccess",
    "Type":  "Microsoft.Compute.Admin/locations/features"
}

## PARAMETERS

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity
Parameter Sets: GetViaIdentity
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
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama fitur.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: FeatureName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20201101.IFeature

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IComputeAdminIdentity>: Parameter Identitas
  - `[DiskId <String>]`: Guid disk sebagai identitas.
  - `[FeatureName <String>]`: Nama fitur.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya.
  - `[MigrationId <String>]`: Nama panduan pekerjaan migrasi.
  - `[Offer <String>]`: Nama penawaran.
  - `[Publisher <String>]`: Nama penerbit.
  - `[QuotaName <String>]`: Nama kuota.
  - `[ScaleUnitName <String>]`: Nama unit skala.
  - `[Sku <String>]`: Nama SKU.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[Type <String>]`: Jenis ekstensi.
  - `[Version <String>]`: Versi sumber daya.

## RELATED LINKS

