---
external help file: ''
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/set-azscomputequota
schema: 2.0.0
ms.openlocfilehash: ceb478270e1d60a2bf045e8f3430eef7b953b2dd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142650142"
---
# Set-AzsComputeQuota

## SYNOPSIS
Membuat atau Memperbarui Kuota Komputasi dengan parameter kuota yang disediakan.

## SYNTAX

```
Set-AzsComputeQuota -NewQuota \<IQuota> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui Kuota Komputasi dengan parameter kuota yang disediakan.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```powershell
$myComputeQuota = Get-AzsComputeQuota -Name MyComputeQuota
```

PS C:\\> $myComputeQuota.CoresLimit = 99; 

PS C:\\> Set-AzsComputeQuota -NewQuota $myComputeQuota

AvailabilitySetCount : 10 CoresLimit : 99 Id : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/northwest/quotAs/MyComputeQuota Lokasi : northwest Name : MyComputeQuota PremiumManagedDiskAndSnapshotSize : 2048 StandardManagedDiskAndSnapshotSize : 2048 Type : Microsoft.Compute.Admin/quotas  VMScaleSetCount : 0 VirtualMachineCount : 100

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
Menyimpan informasi kuota komputasi yang digunakan untuk mengontrol alokasi sumber daya.
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
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NEWQUOTA \<IQuota>: Menyimpan informasi kuota komputasi yang digunakan untuk mengontrol alokasi sumber daya.
  - `[Location <String>]`: Lokasi sumber daya.
  - `[AvailabilitySetCount \<Int32?>]`: Jumlah maksimal set ketersediaan yang diperbolehkan.
  - `[CoresLimit \<Int32?>]`: Jumlah maksimum inti yang diperbolehkan.
  - `[DdagpuCount \<Int32?>]`: Jumlah maksimal gpus dda yang diperbolehkan.
  - `[PartitionedGpuCount \<Int32?>]`: Jumlah maksimum gpus partisi yang diperbolehkan.
  - `[PremiumManagedDiskAndSnapshotSize \<Int32?>]`: Jumlah maksimal disk terkelola dan snapshot tipe premium yang diperbolehkan.
  - `[StandardManagedDiskAndSnapshotSize \<Int32?>]`: Jumlah maksimal disk terkelola dan snapshot tipe standar yang diperbolehkan.
  - `[VMScaleSetCount \<Int32?>]`: Jumlah maksimal kumpulan skala yang diperbolehkan.
  - `[VirtualMachineCount \<Int32?>]`: Jumlah maksimal mesin virtual yang diperbolehkan.

## RELATED LINKS

