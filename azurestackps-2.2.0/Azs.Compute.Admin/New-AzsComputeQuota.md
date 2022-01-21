---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/new-azscomputequota
schema: 2.0.0
ms.openlocfilehash: 816cab18ce30848e6c0b70772d93e91a74db8bbb
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136579558"
---
# New-AzsComputeQuota

## SYNOPSIS
Membuat atau Memperbarui Kuota Perhitungan dengan parameter kuota yang disediakan.

## SYNTAX

### CreateExpanded (Default)
```
New-AzsComputeQuota -Name <String> [-Location <String>] [-SubscriptionId <String>]
 [-AvailabilitySetCount \<Int32>] [-CoresCount \<Int32>] [-Location1 <String>]
 [-PremiumManagedDiskAndSnapshotSize \<Int32>] [-StandardManagedDiskAndSnapshotSize \<Int32>]
 [-VirtualMachineCount \<Int32>] [-VMScaleSetCount \<Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Buat
```
New-AzsComputeQuota -Name <String> -NewQuota \<IQuota> [-Location <String>] [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui Kuota Perhitungan dengan parameter kuota yang disediakan.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
New-AzsComputeQuota -Name ExampleComputeQuotaWithDefaultParameters
```

KetersediaanCount : 10 CoresLimit : 100 Id : /subscriptions/3ae476e5-83d3-429d-a450-2f4f2fc67c5e/providers/Microsoft.Compute.Ad min/locations/local/quotas/ExampleComputeQuotaWithDefaultParameters Location : local Name : ExampleComputeQuotaWithDefaultParameters PremiumManagedDiskAndSnapshotSize : 2048 StandardManagedDiskAndSnapshotSize : 2048 Type                               : Microsoft.Compute.Admin/quotas VMScaleSetCount : 0 VirtualMachineCount : 100

### -------------------------- CONTOH 2 --------------------------
```powershell
New-AzsComputeQuota -Name ExampleComputeQuotaWithCustomParameters -Location local -AvailabilitySetCount 9 -CoresCount 99 -PremiumManagedDiskAndSnapshotSize 1024 -StandardManagedDiskAndSnapshotSize 1024 -VirtualMachineCount 99 -VMScaleSetCount 2
```

AvailabilitySetCount : 9 CoresLimit : 99 Id : /subscriptions/3ae476e5-83d3-429d-a450-2f4f2fc67c5e/providers/Microsoft.Compute.Admin/locat ion/local/quotas/ExampleComputeQuotaWithCustomParameters Location : local Name : ExampleComputeQuotaWithCustomParameters PremiumManagedDiskAndSnapshotSize : 1024 StandardManagedDiskAndSnapshotSize : Tipe 1024                               : Microsoft.Compute.Admin/quotas VMScaleSetCount : 2 VirtualMachineCount : 99

## PARAMETERS

### -AvailabilitySetCount
Jumlah maksimum kumpulan ketersediaan yang diperbolehkan.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -CoresCount
Jumlah maksimum inti yang diperbolehkan.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases: CoresLimit

Required: False
Position: Named
Default value: 100
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

### -Lokasi
Lokasi sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi1
Lokasi sumber daya.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kuota.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: QuotaName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewQuota
Menahan Informasi kuota Perhitungan yang digunakan untuk mengontrol alokasi sumber daya.
Untuk membangun, lihat bagian CATATAN untuk properti NEWQUOTA dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota
Parameter Sets: Create
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PremiumManagedDiskAndSnapshotSize
Jumlah maksimum disk dan jepretan layar tipe premium yang diizinkan.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: 2048
Accept pipeline input: False
Accept wildcard characters: False
```

### -StandardManagedDiskAndSnapshotSize
Jumlah maksimum disk terkelola dan snapshot tipe standar yang diperbolehkan.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: 2048
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineCount
Jumlah maksimum mesin virtual yang diperbolehkan.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMScaleSetCount
Jumlah maksimum kumpulan skala yang diperbolehkan.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NEWQUOTA \<IQuota> : Menyimpan Informasi kuota perhitungan yang digunakan untuk mengontrol alokasi sumber daya.
  - `[Location <String>]`: Lokasi sumber daya.
  - `[AvailabilitySetCount \<Int32?>]`: Jumlah maksimum kumpulan ketersediaan yang diperbolehkan.
  - `[CoresLimit \<Int32?>]`: Jumlah maksimum inti yang diperbolehkan.
  - `[DdagpuCount \<Int32?>]`: Jumlah maksimum gpu dda yang diperbolehkan.
  - `[PartitionedGpuCount \<Int32?>]`: Jumlah maksimum gpu yang dipartisi diperbolehkan.
  - `[PremiumManagedDiskAndSnapshotSize \<Int32?>]`: Jumlah maksimum disk dan jepretan layar tipe premium yang diizinkan.
  - `[StandardManagedDiskAndSnapshotSize \<Int32?>]`: Jumlah maksimum disk terkelola dan snapshot tipe standar yang diperbolehkan.
  - `[VMScaleSetCount \<Int32?>]`: Jumlah maksimum kumpulan skala yang diperbolehkan.
  - `[VirtualMachineCount \<Int32?>]`: Jumlah maksimum mesin virtual yang diperbolehkan.

## RELATED LINKS

