---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/save-azlabserviceslabplanimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Save-AzLabServicesLabPlanImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Save-AzLabServicesLabPlanImage.md
ms.openlocfilehash: a99819271d37719d4e33bcea872c54d01c45cecf
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138163108"
---
# Save-AzLabServicesLabPlanImage

## SYNOPSIS
Menyimpan gambar dari lab VM ke galeri gambar bersama yang dilampirkan.

## SYNTAX

```
Save-AzLabServicesLabPlanImage -LabPlanName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-LabVirtualMachineId <String>] [-Name <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menyimpan gambar dari lab VM ke galeri gambar bersama yang dilampirkan.

## EXAMPLES

### Contoh 1: Menyimpan gambar VM ke Galeri Gambar Bersama.
```powershell
PS C:\> Save-AzLabServicesLabPlanImage -ResourceGroupName "Group Name" -LabName "Lab Name" -Name "New Image Name" -LabVirtualMachineId "/subscriptions/<subscription Id>/resourceGroups/<group name>/providers/Microsoft.LabServices/labs/labName/virtualMachines/<vm name>"

```

Ini akan membuat gambar baru di Galeri Gambar Bersama.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -LabPlanName
Nama rencana lab yang mengidentifikasinya secara unik di dalam grup sumber daya.
Digunakan dalam URI sumber daya dan dalam UI.

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

### -LabVirtualMachineId
ID mesin virtual lab tempat Anda ingin menyimpan gambar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama untuk gambar yang kami buat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -SubscriptionId
ID langganan target.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS

