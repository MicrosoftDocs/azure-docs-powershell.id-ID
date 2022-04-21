---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/disable-azscomputeusersubscriptionfeature
schema: 2.0.0
ms.openlocfilehash: 596203012986a1c92448b58175c8ba91ba3ee727
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142783954"
---
# Disable-AzsComputeUserSubscriptionFeature

## SYNOPSIS
Nonaktifkan fitur langganan penyewa.

## SYNTAX

### DisableExpanded (Default)
```
Disable-AzsComputeUserSubscriptionFeature -FeatureName <String> [-Location <String>]
 [-SubscriptionId <String>] [-TenantSubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Menonaktifkan
```
Disable-AzsComputeUserSubscriptionFeature -FeatureName <String>
 -TenantSubscriptionFeatureSetting \<ITenantSubscriptionFeatureSettings> [-Location <String>]
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DisableViaIdentity
```
Disable-AzsComputeUserSubscriptionFeature -INPUTOBJECT \<IComputeAdminIdentity>
 -TenantSubscriptionFeatureSetting \<ITenantSubscriptionFeatureSettings> [-DefaultProfile <PSObject>]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DisableViaIdentityExpanded
```
Disable-AzsComputeUserSubscriptionFeature -INPUTOBJECT \<IComputeAdminIdentity>
 [-TenantSubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Nonaktifkan fitur langganan penyewa.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
Disable-AzsComputeUserSubscriptionFeature -TenantSubscriptionId 4d105157-d6b2-42db-a3a3-56da6674183a -FeatureName Microsoft.Compute.EmergencyVMAccess -Location local
```



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

### -FeatureName
Nama fitur.

```yaml
Type: System.String
Parameter Sets: Disable, DisableExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity
Parameter Sets: DisableViaIdentity, DisableViaIdentityExpanded
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
Parameter Sets: Disable, DisableExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: Disable, DisableExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantSubscriptionFeatureSetting
Pengaturan fitur untuk langganan penyewa.
Untuk membangun, lihat bagian CATATAN untuk properti TENANTSUBSCRIPTIONFEATURESETTING dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20201101.ITenantSubscriptionFeatureSettings
Parameter Sets: Disable, DisableViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TenantSubscriptionId
Pengidentifikasi langganan penyewa.

```yaml
Type: System.String
Parameter Sets: DisableExpanded, DisableViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20201101.ITenantSubscriptionFeatureSettings

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IComputeAdminIdentity>: Parameter Identitas
  - `[DiskId <String>]`: Disk memandu sebagai identitas.
  - `[FeatureName <String>]`: Nama fitur.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya.
  - `[MigrationId <String>]`: Nama panduan pekerjaan migrasi.
  - `[Offer <String>]`: Nama penawaran.
  - `[Publisher <String>]`: Nama penerbit.
  - `[QuotaName <String>]`: Nama kuota.
  - `[ScaleUnitName <String>]`: Nama unit skala.
  - `[Sku <String>]`: Nama SKU.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.
  - `[Type <String>]`: Jenis ekstensi.
  - `[Version <String>]`: Versi sumber daya.

TENANTSUBSCRIPTIONFEATURESETTING \<ITenantSubscriptionFeatureSettings>: Pengaturan fitur untuk langganan penyewa.
  - `[TenantSubscriptionId <String>]`: Pengidentifikasi langganan penyewa.

## RELATED LINKS

