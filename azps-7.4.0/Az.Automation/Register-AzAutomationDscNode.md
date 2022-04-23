---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 73E6DF02-7171-481B-966F-DECEC122A602
online version: https://docs.microsoft.com/powershell/module/az.automation/register-azautomationdscnode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Register-AzAutomationDscNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Register-AzAutomationDscNode.md
ms.openlocfilehash: 9d3ecc29c2228176d60eb4a587956828d7890127
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143319851"
---
# Register-AzAutomationDscNode

## SYNOPSIS
Mendaftarkan mesin virtual Azure yang menjalankan os Windows sebagai simpul DSC untuk akun Otomatisasi.

## SYNTAX

```
Register-AzAutomationDscNode -AzureVMName <String> [-NodeConfigurationName <String>]
 [-ConfigurationMode <String>] [-ConfigurationModeFrequencyMins <Int32>] [-RefreshFrequencyMins <Int32>]
 [-RebootNodeIfNeeded <Boolean>] [-ActionAfterReboot <String>] [-AllowModuleOverwrite <Boolean>]
 [-AzureVMResourceGroup <String>] [-AzureVMLocation <String>] [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Register-AzAutomationDscNode** mendaftarkan mesin virtual Azure sebagai node APS Desired State Configuration (DSC) dalam akun Azure Automation. Cmdlet ini hanya akan mendaftarkan VM yang menjalankan Windows OS sebagai Node DSC Otomatisasi untuk akun.

Jika Anda perlu mendaftarkan simpul ke akun otomatisasi dalam langganan yang berbeda, Anda harus menggunakan templat ARM daripada cmdlet. Lihat [dokumentasi](https://docs.microsoft.com/azure/automation/automation-dsc-onboarding#registering-virtual-machines-across-azure-subscriptions) Azure Automation untuk detail selengkapnya.

## EXAMPLES

### Contoh 1: Daftarkan mesin virtual Azure sebagai simpul DSC Azure
```
PS C:\>Register-AzAutomationDscNode -AutomationAccountName "Contoso17" -AzureVMName "VirtualMachine01" -ResourceGroupName "ResourceGroup01"-NodeConfigurationName "ContosoConfiguration.webserver"
```

Perintah ini mendaftarkan mesin virtual Azure bernama VirtualMachine01 sebagai simpul DSC di akun Otomatisasi bernama Contoso17.

## PARAMETERS

### -ActionAfterReboot
Menentukan aksi yang dilakukan mesin virtual setelah dimulai ulang.
Nilai yang valid adalah: 
- Lanjutkan Konfigurasi 
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
Menentukan apakah konfigurasi baru yang diunduh simpul DSC ini dari Azure Automation server tarik DSC menggantikan modul yang sudah ada pada simpul target.

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
Menentukan nama akun Otomatisasi tempat cmdlet ini mendaftarkan mesin virtual.

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
Nama mesin virtual Azure untuk mendaftar manajemen dengan Azure Automation DSC.

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
Nilai yang valid adalah: 
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
Menentukan frekuensi, dalam menit, di mana aplikasi latar belakang DSC berusaha menerapkan konfigurasi saat ini pada simpul target.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Menentukan nama konfigurasi simpul yang cmdlet ini mengonfigurasi mesin virtual untuk menarik dari Azure Automation DSC.

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
Menentukan apakah akan memulai ulang mesin maya, jika diperlukan.

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
Menentukan frekuensi, dalam menit, di mana Configuration Manager lokal menghubungi server tarik DSC Azure Automation untuk mengunduh konfigurasi simpul terbaru.

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
Akun Otomatisasi tempat cmdlet ini mendaftarkan mesin virtual milik grup sumber daya yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Int32

### System.Boolean

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzAutomationDscNode](./Get-AzAutomationDscNode.md)

[Set-AzAutomationDscNode](./Set-AzAutomationDscNode.md)

[Unregister-AzAutomationDscNode](./Unregister-AzAutomationDscNode.md)


