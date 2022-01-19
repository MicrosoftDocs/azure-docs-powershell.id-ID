---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/set-azscomputequota
schema: 2.0.0
ms.openlocfilehash: ceb478270e1d60a2bf045e8f3430eef7b953b2dd
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136576842"
---
# Set-AzsComputeQuota

## SYNOPSIS
Membuat atau Memperbarui Kuota Perhitungan dengan parameter kuota yang disediakan.

## SYNTAX

```
Set-AzsComputeQuota -NewQuota \<IQuota> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui Kuota Perhitungan dengan parameter kuota yang disediakan.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
$myComputeQuota = Get-AzsComputeQuota -Name MyComputeQuota
```

PS C: \\> $myComputeQuota.CoresLimit = 99; 

PS C: \\> Set-AzsComputeQuota -NewQuota $myComputeQuota

KetersediaanCount: 10 CoresLimit : 99 Id : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/northwest/quotas/MyComputeQuota Location : northwest Name : MyComputeQuota PremiumManagedDiskAndSnapshotSize : 2048 StandardManagedDiskAndSnapshotSize : 2048 Type : Microsoft.Compute.Admin/quotas  VMScaleSetCount : 0 VirtualMachineCount : 100

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

### -NewQuota
Menahan Informasi kuota Perhitungan yang digunakan untuk mengontrol alokasi sumber daya.
Untuk membangun, lihat bagian CATATAN untuk properti NEWQUOTA dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

