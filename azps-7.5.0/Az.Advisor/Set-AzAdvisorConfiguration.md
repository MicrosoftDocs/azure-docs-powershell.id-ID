---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Advisor.dll-Help.xml
Module Name: Az.Advisor
online version: https://docs.microsoft.com/powershell/module/az.advisor/set-azadvisorConfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Advisor/Advisor/help/Set-AzAdvisorConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Advisor/Advisor/help/Set-AzAdvisorConfiguration.md
ms.openlocfilehash: 8d7e6a246a08508f38e79f542b126e1035d4aba9
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145790578"
---
# Set-AzAdvisorConfiguration

## SYNOPSIS
Memperbarui atau membuat Konfigurasi Advisor Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.advisor/set-azadvisorconfiguration) untuk informasi terbaru.

## SYNTAX

### InputObjectRgExcludeParameterSet (Default)
```
Set-AzAdvisorConfiguration [-Exclude] [[-ResourceGroupName] <String>]
 [[-InputObject] <PsAzureAdvisorConfigurationData>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectLowCpuExcludeParameterSet 
```
Set-AzAdvisorConfiguration [-Exclude] [-LowCpuThreshold] <Int32>
 [[-InputObject] <PsAzureAdvisorConfigurationData>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Digunakan untuk memperbarui konfigurasi Advisor Azure. Ada dua jenis Konfigurasi: Konfigurasi tingkat langganan dan konfigurasi tingkat ResourceGroup. 

Konfigurasi tingkat langganan: Hanya ada satu Konfigurasi untuk jenis ini untuk langganan. Properti LowCpuThreshold dan Exclude dapat diperbarui menggunakan cmdlet ini.
Konfigurasi tingkat ResourceGroup: Hanya ada satu konfigurasi untuk setiap ResourceGroup. Hanya properti Kecualikan yang dapat diperbarui menggunakan cmdlet ini.

## EXAMPLES

###  Contoh 1
```powershell
Set-AzAdvisorConfiguration -LowCpuThreshold 10
```

```output
Id         : /subscriptions/{user_subscription}/resourceGroups/resourceGroupName1/providers/Microsoft.Advisor/configurations/{user_subscription}
Name       : {user_subscription}
Properties : additionalProperties : null
             exclude :  False
             lowCpuThreshold : 10

Type       : Microsoft.Advisor/Configurations
```

Memperbarui konfigurasi (lowCpuThreshold) untuk Konfigurasi tingkat langganan.

### Contoh 2
```powershell
Set-AzAdvisorConfiguration -LowCpuThreshold 15 -Exclude
```
 
```output
Id         : /subscriptions/{user_subscription}/resourceGroups/resourceGroupName1/providers/Microsoft.Advisor/configurations/{user_subscription}
Name       : {user_subscription}
Properties : additionalProperties : null
             exclude :  True
             lowCpuThreshold : 15

Type       : Microsoft.Advisor/Configurations
```

Memperbarui konfigurasi (lowCpuThreshold, kecualikan) untuk Konfigurasi tingkat langganan dan mengecualikan dari pembuatan rekomendasi.

### Contoh: 3
```powershell
Set-AzAdvisorConfiguration -ResourceGroupName resourceGroupName1 -Exclude
```

```output
Id         : /subscriptions/{user_subscription}/resourceGroups/resourceGroupName1/providers/Microsoft.Advisor/configurations/{user_subscription}-resourceGroupName1
Name       : {user_subscription}-resourceGroupName1
Properties : additionalProperties : null
             exclude :  True
             lowCpuThreshold : null

Type       : Microsoft.Advisor/Configurations
```

Memperbarui konfigurasi (kecualikan) agar resourceGroupName1 dikecualikan dalam pembuatan rekomendasi.

### Contoh 4
```powershell
Get-AzAdvisorConfiguration | Set-AzAdvisorConfiguration -LowCpuThreshold 20
```

```output
Id         : /subscriptions/{user_subscription}/resourceGroups/resourceGroupName1/providers/Microsoft.Advisor/configurations/{user_subscription}
Name       : {user_subscription}
Properties : additionalProperties : null
             exclude :  False
             lowCpuThreshold : 20

Type       : Microsoft.Advisor/Configurations
```

Memperbarui konfigurasi untuk rekomendasi yang diberikan yang diteruskan dari alur.

## PARAMETERS

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kecualikan
Kecualikan dari pembuatan rekomendasi. Jika tidak ditentukan, properti pengecualian akan diatur ke false.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Jenis objek powershell PsAzureAdvisorConfigurationData yang dikembalikan oleh panggilan Get-AzAdvisorConfiguration.

```yaml
Type: PsAzureAdvisorConfigurationData
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LowCpuThreshold
Nilai untuk ambang batas Cpu Rendah.

```yaml
Type: Int32
Parameter Sets: InputObjectLowCpuExcludeParameterSet
Aliases:
Accepted values: 0, 5, 10, 15, 20

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya untuk konfigurasi.

```yaml
Type: String
Parameter Sets: InputObjectRgExcludeParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands. Advisor. Cmdlets.Models.PsAzureAdvisorConfigurationData

## OUTPUTS

### Microsoft.Azure.Commands. Advisor. Cmdlets.Models.PsAzureAdvisorConfigurationData

## NOTES

## RELATED LINKS
