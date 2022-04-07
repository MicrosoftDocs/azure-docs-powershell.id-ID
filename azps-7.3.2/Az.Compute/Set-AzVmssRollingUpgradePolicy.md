---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmssrollingupgradepolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssRollingUpgradePolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssRollingUpgradePolicy.md
ms.openlocfilehash: f110baa409222f699e3ee9cc44755d08adf8f1e9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140395283"
---
# Set-AzVmssRollingUpgradePolicy

## SYNOPSIS
Mengatur properti kebijakan pemutakhiran vmSS yang diluncurkan.

## SYNTAX

```
Set-AzVmssRollingUpgradePolicy [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet>
 [[-MaxBatchInstancePercent] <Int32>] [[-MaxUnhealthyInstancePercent] <Int32>]
 [[-MaxUnhealthyUpgradedInstancePercent] <Int32>] [-PauseTimeBetweenBatches <String>]
 [-EnableCrossZoneUpgrade <Boolean>] [-PrioritizeUnhealthyInstance <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengatur properti kebijakan pemutakhiran vmSS yang diluncurkan.

## EXAMPLES

### Contoh 1
```powershell
Set-AzVmssRollingUpgradePolicy -VirtualMachineScaleSet $vmss -VirtualMachineScaleSet $vmss -MaxBatchInstancePercent 40 -MaxUnhealthyInstancePercent 35 -MaxUnhealthyUpgradedInstancePercent 30 -PauseTimeBetweenBatches "PT30S"
```

Perintah ini mengatur 40 persen untuk MaxBatchInstance, 35 persen untuk MaxUnhealthyInstance, 30 persen untuk MaxUnhealthyUpgradedInstance, dan 30 detik waktu jeda antar kumpulan untuk objek lokal VMSS $vmss.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Izinkan VMSS untuk mengabaikan batas AZ ketika menyusun kumpulan pemutakhiran. Pertimbangkan Perbarui Domain dan maxBatchInstancePercent untuk menentukan ukuran kumpulan.

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
Persentase maksimum instans mesin virtual total yang akan dimutakhirkan secara bersamaan dengan pemutakhiran bertahap dalam satu kumpulan.
Karena ini adalah contoh maksimum yang tidak sehat pada kumpulan sebelumnya atau yang akan datang dapat menyebabkan persentase contoh dalam batch berkurang untuk memastikan keandalan yang lebih tinggi.
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
Persentase maksimum instans mesin virtual total dalam kumpulan skala yang dapat secara bersamaan tidak sehat, baik sebagai akibat pemutakhiran, atau dengan ditemukan dalam keadaan tidak sehat oleh pemeriksaan kesehatan mesin virtual sebelum peluncuran peningkatan.
Batasan ini akan dicentang sebelum memulai kumpulan apa pun.
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
Persentase maksimum dari mesin virtual yang dimutakhirkan yang dapat ditemukan dalam keadaan tidak sehat.
Pemeriksaan ini akan terjadi setelah setiap kumpulan ditakhirkan.
Jika persentase ini pernah melebihi, pembaruan diluncurkan pada pembaruan terkini.
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
Mutakhirkan semua instans yang tidak sehat dalam kumpulan skala sebelum setiap kejadian sehat.

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

### -VirtualMachinescaleSet
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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Int32

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS
