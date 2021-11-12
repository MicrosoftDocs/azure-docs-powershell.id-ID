---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
Module Name: AzureRM.Automation
ms.assetid: 73E6DF02-7171-481B-966F-DECEC122A602
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.automation/register-azurermautomationdscnode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Register-AzureRmAutomationDscNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Register-AzureRmAutomationDscNode.md
ms.openlocfilehash: 614e954f4e8ec37d24495e766a139eb8a961c743
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420063"
---
# Register-AzureRmAutomationDscNode

## SYNOPSIS
Mendaftarkan mesin virtual Azure sebagai simpul DSC untuk akun Otomatisasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Register-AzureRmAutomationDscNode -AzureVMName <String> [-NodeConfigurationName <String>]
 [-ConfigurationMode <String>] [-ConfigurationModeFrequencyMins <Int32>] [-RefreshFrequencyMins <Int32>]
 [-RebootNodeIfNeeded <Boolean>] [-ActionAfterReboot <String>] [-AllowModuleOverwrite <Boolean>]
 [-AzureVMResourceGroup <String>] [-AzureVMLocation <String>] [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Register-AzureRmAutomationDscNode** mendaftarkan mesin virtual Azure sebagai node APS Desired State Configuration (DSC) dalam akun Otomatisasi Azure.

## EXAMPLES

### Contoh 1: Mendaftarkan mesin virtual Azure sebagai node Azure DSC
```
PS C:\>Register-AzureRmAutomationDscNode -AutomationAccountName "Contoso17" -AzureVMName "VirtualMachine01" -ResourceGroupName "ResourceGroup01"-NodeConfigurationName "ContosoConfiguration.webserver"
```

Perintah ini mendaftarkan mesin virtual Azure yang bernama VirtualMachine01 sebagai simpul DSC dalam akun Otomatisasi yang bernama Contoso17.

## PARAMETERS

### -ActionAfterReboot
Menentukan tindakan yang dilakukan mesin virtual setelah menghidupkan ulang.
Nilai valid adalah: 

- ContinueConfiguration 
- StopConfiguration

```yaml
Type: String
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
Type: Boolean
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AzureVMLocation
Menentukan lokasi di mana cmdlet ini mendaftarkan komputer virtual.
Untuk mendapatkan lokasi yang valid, gunakan Get-AzureRMLocation cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AzureVMName
Menentukan nama komputer virtual Azure yang didaftarkan cmdlet ini untuk manajemen.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AzureVMResourceGroup
Menentukan nama grup sumber daya komputer virtual Azure yang didaftarkan cmdlet ini.

```yaml
Type: String
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
Type: String
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
Type: Int32
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeConfigurationName
Menentukan nama konfigurasi node yang dikonfigurasi cmdlet ini untuk menarik dari DSC Otomatisasi Azure.

```yaml
Type: String
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
Type: Boolean
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
Type: Int32
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmAutomationDscNode](./Get-AzureRmAutomationDscNode.md)

[Set-AzureRmAutomationDscNode](./Set-AzureRmAutomationDscNode.md)

[Pisahkan-AzureRmAutomationDscNode](./Unregister-AzureRmAutomationDscNode.md)


