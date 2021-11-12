---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/en-us/powershell/module/az.machinelearning/new-azmlcommitmentplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/MachineLearning/MachineLearning/help/New-AzMlCommitmentPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/MachineLearning/MachineLearning/help/New-AzMlCommitmentPlan.md
ms.openlocfilehash: 7d3d65e10864848cb1564b7137321c911c153ce0
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409484"
---
# New-AzMlCommitmentPlan

## SYNOPSIS
Membuat rencana komitmen baru.

## SINTAKS

```
New-AzMlCommitmentPlan -ResourceGroupName <String> -Location <String> -Name <String> -SkuName <String>
 -SkuTier <String> [-SkuCapacity <Int32>] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Membuat rencana Azure Machine Learning komitmen dalam grup sumber daya yang ada.
Jika rencana komitmen dengan nama yang sama terdapat di grup sumber daya, panggilan bertindak sebagai operasi pembaruan dan rencana komitmen yang ada ditimpa.

## CONTOH

### Contoh 1: Membuat rencana komitmen baru
```
New-AzMlCommitmentPlan -ResourceGroupName "MyResourceGroup" -Name "MyCommitmentPlanName" -Location "South Central US" -SkuName DevTest -SkuTier Standard -SkuCapacity 1
```

Membuat rencana Azure Machine Learning baru bernama "MyCommitmentPlanName" di grup "MyResourceGroup" dan kawasan AS Pusat Selatan. Dalam contoh ini, SKU DevTest/Standard digunakan, yang berarti sumber daya yang disediakan oleh rencana komitmen akan ditentukan oleh batas DevTest/Standard. Kota SkuCapacity dalam contoh ini adalah 1, artinya biaya paket adalah 1x biaya DevTest, dan sumber daya yang terdapat dalam paket adalah 1x yang diberikan DevTest.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Force
Jangan minta konfirmasi.

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

### -Lokasi
Lokasi paket komitmen ML Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama paket komitmen ML Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya untuk Rencana ML Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuCapacity
Kapasitas SKU yang akan digunakan ketika menyediakan paket komitmen ML Azure.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Nama SKU yang akan digunakan ketika menyediakan paket komitmen ML Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuTier
Tingkatan SKU yang akan digunakan ketika menyediakan paket komitmen ML Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Management.MachineLearning.CommitmentPlans.Models.CommitmentPlan

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## LINK TERKAIT
