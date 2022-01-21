---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/update-azscomputeglobalfeaturesetting
schema: 2.0.0
ms.openlocfilehash: 1ce2f2aa0f0694d78c781d57398a3261219c43f7
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136580818"
---
# Update-AzsComputeGlobalFeatureSetting

## SYNOPSIS
Perbarui pengaturan fitur.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzsComputeGlobalFeatureSetting -FeatureName <String> [-Location <String>] [-SubscriptionId <String>]
 [-GlobalFeatureState <GlobalFeatureState>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Perbarui
```
Update-AzsComputeGlobalFeatureSetting -FeatureName <String> -GlobalFeatureSetting \<IGlobalFeatureSettings>
 [-Location <String>] [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentity
```
Update-AzsComputeGlobalFeatureSetting -INPUTOBJECT \<IComputeAdminIdentity>
 -GlobalFeatureSetting \<IGlobalFeatureSettings> [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzsComputeGlobalFeatureSetting -INPUTOBJECT \<IComputeAdminIdentity>
 [-GlobalFeatureState <GlobalFeatureState>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Perbarui pengaturan fitur.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
Update-AzsComputeGlobalFeatureSetting -FeatureName Microsoft.Compute.EmergencyVMAccess -GlobalFeatureState Enabled -Location local
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
Parameter Sets: Update, UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalFeatureSetting
Bendera fitur global prioritas lebih tinggi.
Untuk membuat, lihat bagian CATATAN untuk properti GLOBALFEATURESETTING dan membuat tabel hash.

Kemungkinan nilai string Dari GlobalFeatureSetting diaktifkan, Dinonaktifkan, dan TenantSubscriptionLevel. Diaktifkan/Dinonaktifkan akan menimpa fitur yang diaktifkan dengan ID langganan penyewa. TenantSubscriptionLevel akan menunda diaktifkannya fitur untuk per ID langganan penyewa.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20201101.IGlobalFeatureSettings
Parameter Sets: Update, UpdateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GlobalFeatureState
Status fitur global.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Support.GlobalFeatureState
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity
Parameter Sets: UpdateViaIdentity, UpdateViaIdentityExpanded
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
Parameter Sets: Update, UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: Update, UpdateExpanded
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20201101.IGlobalFeatureSettings

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


GLOBALFEATURESETTING \<IGlobalFeatureSettings> : Bendera fitur global dengan prioritas lebih tinggi.
  - `[GlobalFeatureState <GlobalFeatureState?>]`: Status fitur global.

INPUTOBJECT \<IComputeAdminIdentity> : Parameter Identitas
  - `[DiskId <String>]`: Disk guid sebagai identitas.
  - `[FeatureName <String>]`: Nama fitur.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya.
  - `[MigrationId <String>]`: Nama guid pekerjaan migrasi.
  - `[Offer <String>]`: Nama penawaran.
  - `[Publisher <String>]`: Nama penerbit.
  - `[QuotaName <String>]`: Nama kuota.
  - `[ScaleUnitName <String>]`: Nama unit skala.
  - `[Sku <String>]`: Nama SKU.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[Type <String>]`: Tipe ekstensi.
  - `[Version <String>]`: Versi sumber daya.

## RELATED LINKS

