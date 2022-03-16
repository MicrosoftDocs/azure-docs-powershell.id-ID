---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Advisor.dll-Help.xml
Module Name: Az.Advisor
online version: https://docs.microsoft.com/powershell/module/az.advisor/set-azadvisorConfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Advisor/Advisor/help/Set-AzAdvisorConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Advisor/Advisor/help/Set-AzAdvisorConfiguration.md
ms.openlocfilehash: 5a4a6f232934cc10522a265edc056a77bfe08248
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140010644"
---
# Set-AzAdvisorConfiguration

## SYNOPSIS
Memperbarui atau membuat Konfigurasi Penasihat Azure.

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
Digunakan untuk memperbarui konfigurasi Azure Advisor. Dua tipe Konfigurasi ada: Konfigurasi tingkat langganan dan Konfigurasi tingkat Grup Sumber Daya. 

Konfigurasi tingkat langganan: Hanya bisa ada satu Konfigurasi untuk tipe ini untuk langganan. Properti LowCpuThreshold dan Exclude bisa diperbarui menggunakan cmdlet ini.
Konfigurasi tingkat Grup Sumber Daya: Hanya ada satu konfigurasi untuk setiap Grup Sumber Daya. Hanya properti Exclude yang dapat diperbarui menggunakan cmdlet ini.

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

Memperbarui configuration(lowCpuThreshold) untuk Konfigurasi tingkat langganan.

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

Memperbarui configuration(lowCpuThreshold, exclude) untuk Konfigurasi tingkat langganan dan dikecualikan dari rekomendasi pembuatan.

### Contoh 3
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

Pembaruan configuration(exclude) untuk resourceGroupName1 akan dikecualikan dalam pembuatan rekomendasi.

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

Memperbarui konfigurasi untuk rekomendasi tertentu yang disampaikan dari saluran.

## PARAMETERS

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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

### -Exclude
Kecualikan dalam pembuatan rekomendasi. Jika tidak ada properti pengecualian yang ditentukan akan diatur ke false.

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
Tipe objek powershell PsAzureAdvisorConfigurationData dikembalikan oleh Get-AzAdvisorConfiguration panggilan.

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
Nilai untuk ambang Cpu rendah.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorConfigurationData

## OUTPUTS

### Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorConfigurationData

## CATATAN

## RELATED LINKS
