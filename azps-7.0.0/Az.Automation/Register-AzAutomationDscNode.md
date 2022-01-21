---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 73E6DF02-7171-481B-966F-DECEC122A602
online version: https://docs.microsoft.com/powershell/module/az.automation/register-azautomationdscnode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Register-AzAutomationDscNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Register-AzAutomationDscNode.md
ms.openlocfilehash: 9d3ecc29c2228176d60eb4a587956828d7890127
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136571645"
---
# Register-AzAutomationDscNode

## SYNOPSIS
Mendaftarkan mesin virtual Azure yang Windows OS sebagai node DSC untuk akun Otomatisasi.

## SYNTAX

```
Register-AzAutomationDscNode -AzureVMName <String> [-NodeConfigurationName <String>]
 [-ConfigurationMode <String>] [-ConfigurationModeFrequencyMins <Int32>] [-RefreshFrequencyMins <Int32>]
 [-RebootNodeIfNeeded <Boolean>] [-ActionAfterReboot <String>] [-AllowModuleOverwrite <Boolean>]
 [-AzureVMResourceGroup <String>] [-AzureVMLocation <String>] [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Register-AzAutomationDscNode** mendaftarkan mesin virtual Azure sebagai simpul KONFIGURASI Status yang Diinginkan (DSC, Desired State Configuration) APS dalam akun Otomatisasi Azure. Cmdlet ini hanya akan mendaftarkan VM yang Windows OS sebagai Node DSC Otomatisasi untuk akun.

Jika Anda perlu mendaftarkan simpul ke akun otomatisasi dalam langganan yang berbeda, Anda perlu menggunakan templat ARM, bukan cmdlet. Lihat dokumentasi Otomatisasi Azure [untuk](https://docs.microsoft.com/azure/automation/automation-dsc-onboarding#registering-virtual-machines-across-azure-subscriptions) detail selengkapnya.

## EXAMPLES

### Contoh 1: Mendaftarkan mesin virtual Azure sebagai node Azure DSC
```
PS C:\>Register-AzAutomationDscNode -AutomationAccountName "Contoso17" -AzureVMName "VirtualMachine01" -ResourceGroupName "ResourceGroup01"-NodeConfigurationName "ContosoConfiguration.webserver"
```

Perintah ini mendaftarkan mesin virtual Azure yang bernama VirtualMachine01 sebagai simpul DSC dalam akun Otomatisasi yang bernama Contoso17.

## PARAMETERS

### -ActionAfterReboot
Menentukan tindakan yang dilakukan mesin virtual setelah menghidupkan ulang.
Nilai valid adalah: 
- ContinueConfiguration 
- StopConfiguration

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ContinueConfiguration, StopConfiguration

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllowModuleOverwrite
Menentukan apakah konfigurasi baru yang diunduh simpul DSC ini dari server tarik DSC Azure Automation menggantikan modul yang sudah ada pada node target.

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

### -AutomationAccountName
Menentukan nama akun Otomatisasi di mana cmdlet ini mendaftarkan mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AzureVMLocation
Lokasi Azure VM.

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

### -AzureVMName
Nama mesin virtual Azure untuk mendaftar manajemen dengan DSC Otomatisasi Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AzureVMResourceGroup
Nama grup sumber daya Azure VM.

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

### -ConfigurationMode
Menentukan mode konfigurasi DSC.
Nilai valid adalah: 
- ApplyAndMonitor 
- ApplyAndAutocorrect 
- ApplyOnly

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ApplyAndMonitor, ApplyAndAutocorrect, ApplyOnly

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationModeFrequencyMins
Menentukan frekuensi, dalam menit, di mana aplikasi latar belakang DSC berusaha menerapkan konfigurasi saat ini pada node target.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -NodeConfigurationName
Menentukan nama konfigurasi node yang dikonfigurasi cmdlet ini untuk menarik dari DSC Otomatisasi Azure.

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

### -RebootNodeIfNeeded
Menentukan apakah akan memulai ulang mesin virtual, jika diperlukan.

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

### -RefreshFrequencyMins
Menentukan frekuensi, dalam menit, di mana Manajer Konfigurasi lokal menghubungi server tarik DSC Azure Automation untuk mengunduh konfigurasi node terbaru.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.
Akun Otomatisasi yang mendaftarkan komputer virtual milik grup sumber daya yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Int32

### System.Boolean

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzAutomationDscNode](./Get-AzAutomationDscNode.md)

[Set-AzAutomationDscNode](./Set-AzAutomationDscNode.md)

[Unregister-AzAutomationDscNode](./Unregister-AzAutomationDscNode.md)


