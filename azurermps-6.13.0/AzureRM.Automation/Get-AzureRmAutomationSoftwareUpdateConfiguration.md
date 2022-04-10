---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
Module Name: AzureRM.Automation
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.automation/get-azurermautomationsoftwareupdateconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Get-AzureRmAutomationSoftwareUpdateConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Get-AzureRmAutomationSoftwareUpdateConfiguration.md
ms.openlocfilehash: f2702318f59cd585e0893fda68a728d60402678c85621b3998176c93e0701f40
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140856062"
---
# Get-AzureRmAutomationSoftwareUpdateConfiguration

## SYNOPSIS
Mendapatkan daftar konfigurasi pembaruan perangkat lunak otomatisasi Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SecaraSemua (Default)
```
Get-AzureRmAutomationSoftwareUpdateConfiguration [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzureRmAutomationSoftwareUpdateConfiguration -Name <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByVMId
```
Get-AzureRmAutomationSoftwareUpdateConfiguration -AzureVMResourceId <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Opsi Get-AzureRmAutomationSoftwareUpdateConfiguration mengembalikan daftar konfigurasi pembaruan perangkat lunak. Untuk mendapatkan konfigurasi pembaruan perangkat lunak tertentu, tentukan parameter nama. Anda juga bisa mencantumkan konfigurasi pembaruan perangkat lunak yang menargetkan komputer virtual Azure tertentu dengan menentukan Id sumber daya azure untuk komputer virtual ini.

## EXAMPLES

### Contoh 1
Dapatkan konfigurasi pembaruan perangkat lunak otomatisasi Azure berdasarkan nama.

```powershell
PS C:\> Get-AzureRmAutomationSoftwareUpdateConfiguration -ResourceGroupName "mygroup" -AutomationAccountName "myaccount" -Name "MyWeeklySchedule"

UpdateConfiguration   : Microsoft.Azure.Commands.Automation.Model.UpdateManagement.UpdateConfiguration
ScheduleConfiguration : Microsoft.Azure.Commands.Automation.Model.Schedule
ProvisioningState     : Succeeded
ErrorInfo             :
ResourceGroupName     : mygroup
AutomationAccountName : myaccount
Name                  : MyWeeklySchedule
CreationTime          : 9/14/2018 3:53:27 AM +00:00
LastModifiedTime      : 9/14/2018 3:53:37 AM +00:00
Description           :
```

## PARAMETERS

### -AutomationAccountName
Nama akun otomatisasi.

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

### -AzureVMResourceId
Id sumber daya Azure komputer virtual.

```yaml
Type: System.String
Parameter Sets: ByVMId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama konfigurasi pembaruan perangkat lunak.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.UpdateManagement.SoftwareUpdateConfiguration

## CATATAN

## RELATED LINKS
