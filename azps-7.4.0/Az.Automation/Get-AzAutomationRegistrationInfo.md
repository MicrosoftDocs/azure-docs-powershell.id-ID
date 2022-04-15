---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 09823BE3-A98B-42EF-B6F4-99F95F2B342E
online version: https://docs.microsoft.com/powershell/module/az.automation/get-azautomationregistrationinfo
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationRegistrationInfo.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationRegistrationInfo.md
ms.openlocfilehash: 47dcfa27e1708d0375d2925f89a69c519092571b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142428557"
---
# Get-AzAutomationRegistrationInfo

## SYNOPSIS
Mendapatkan informasi pendaftaran untuk onboarding simpul DSC atau pekerja hibrid ke Otomatisasi.

## SYNTAX

```
Get-AzAutomationRegistrationInfo [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAutomationRegistrationInfo** mendapatkan titik akhir dan kunci yang diperlukan untuk mengintegrasikan node Desired State Configuration (DSC) atau pekerja hibrid ke akun Azure Automation.

## EXAMPLES

### Contoh 1: Dapatkan informasi registrasi
```
PS C:\>Get-AzAutomationRegistrationInfo -ResourceGroupName "ResourceGroup01" -AutomationAccountName "AutomationAccount01"
```

Perintah ini mendapatkan informasi pendaftaran untuk akun Otomatisasi bernama AutomationAccount01 dalam Grup Sumber Daya bernama ResourceGroup01.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi tempat cmdlet ini mendapatkan informasi registrasi.

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

### -ResourceGroupName
Menentukan nama grup sumber daya.
Cmdlet ini mendapatkan informasi pendaftaran untuk grup sumber daya yang ditentukan parameter ini.

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

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.AgentRegistration

## CATATAN

## RELATED LINKS

[Get-AzAutomationAccount](./Get-AzAutomationAccount.md)

[Get-AzAutomationDscNode](./Get-AzAutomationDscNode.md)

[New-AzAutomationKey](./New-AzAutomationKey.md)


