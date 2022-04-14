---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmssrollingupgradepolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssRollingUpgradePolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssRollingUpgradePolicy.md
ms.openlocfilehash: f110baa409222f699e3ee9cc44755d08adf8f1e9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142180024"
---
# Set-AzVmssRollingUpgradePolicy

## SYNOPSIS
Mengatur properti kebijakan pemutakhiran bergulir VMSS.

## SYNTAX

```
Set-AzVmssRollingUpgradePolicy [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet>
 [[-MaxBatchInstancePercent] <Int32>] [[-MaxUnhealthyInstancePercent] <Int32>]
 [[-MaxUnhealthyUpgradedInstancePercent] <Int32>] [-PauseTimeBetweenBatches <String>]
 [-EnableCrossZoneUpgrade <Boolean>] [-PrioritizeUnhealthyInstance <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengatur properti kebijakan pemutakhiran bergulir VMSS.

## EXAMPLES

### Contoh 1
```powershell
Set-AzVmssRollingUpgradePolicy -VirtualMachineScaleSet $vmss -VirtualMachineScaleSet $vmss -MaxBatchInstancePercent 40 -MaxUnhealthyInstancePercent 35 -MaxUnhealthyUpgradedInstancePercent 30 -PauseTimeBetweenBatches "PT30S"
```

Perintah ini menetapkan 40 persen untuk MaxBatchInstance, 35 persen untuk MaxUnhealthyInstance, 30 persen untuk MaxUnhealthyUpgradedInstance dan 30 waktu jeda kedua antar kumpulan untuk objek lokal VMSS $vmss.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableCrossZoneUpgrade
Izinkan VMSS mengabaikan batas AZ saat menyusun kumpulan pemutakhiran. Pertimbangkan Perbarui Domain dan maxBatchInstancePercent untuk menentukan ukuran batch.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxBatchInstancePercent
Persen maksimum dari total instans mesin virtual yang akan dimutakhirkan secara bersamaan dengan pemutakhiran bergulir dalam satu batch.
Karena ini adalah instans maksimum yang tidak sehat dalam kumpulan sebelumnya atau yang akan datang dapat menyebabkan persentase instans dalam kumpulan berkurang untuk memastikan keandalan yang lebih tinggi.
Jika nilai tidak ditentukan, nilai diatur ke 20.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxUnhealthyInstancePercent
Persentase maksimum dari total instans mesin virtual dalam kumpulan skala yang bisa secara bersamaan tidak sehat, baik sebagai akibat dari dimutakhirkan, atau dengan ditemukan dalam keadaan tidak sehat oleh pemeriksaan kesehatan mesin virtual sebelum pemutakhiran bergulir dibatalkan.
Batasan ini akan diperiksa sebelum memulai kumpulan apa pun.
Jika nilai tidak ditentukan, nilai diatur ke 20.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxUnhealthyUpgradedInstancePercent
Persentase maksimum instans mesin virtual yang dimutakhirkan yang dapat ditemukan dalam keadaan tidak sehat.
Pemeriksaan ini akan terjadi setelah setiap kumpulan dimutakhirkan.
Jika persentase ini pernah melebihi, pembaruan bergulir akan dibatalkan.
Jika nilai tidak ditentukan, nilai diatur ke 20.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PauseTimeBetweenBatches
Waktu tunggu antara menyelesaikan pembaruan untuk semua mesin virtual dalam satu kumpulan dan memulai kumpulan berikutnya.
Durasi waktu harus ditentukan dalam format ISO 8601.
Nilai defaultnya adalah 0 detik (PT0S).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrioritizeUnhealthyInstance
Mutakhirkan semua instans yang tidak sehat dalam skala yang ditetapkan sebelum instans sehat apa pun.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet New-AzVmssConfig untuk membuat objek.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Int32

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS
