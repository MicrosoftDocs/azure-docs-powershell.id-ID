---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeployment.md
ms.openlocfilehash: 0c3675d4f3a8e41e416db83dbe3a88546da70074
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144230394"
---
# Get-AzDeployment

## SYNOPSIS
Mendapatkan penyebaran

## SYNTAX

### GetByDeploymentName (Default)
```
Get-AzDeployment [[-Name] <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByDeploymentId
```
Get-AzDeployment -Id <String> [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDeployment** mendapatkan penyebaran di cakupan langganan saat ini.
Tentukan parameter *Nama* atau *Id* untuk memfilter hasilnya.
Secara default, **Get-AzDeployment** mendapatkan semua penyebaran di cakupan langganan saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyebaran di cakupan langganan
```powershell
Get-AzDeployment
```

Perintah ini mendapatkan semua penyebaran pada cakupan langganan saat ini.

### Contoh 2: Mendapatkan penyebaran berdasarkan nama
```powershell
Get-AzDeployment -Name "DeployRoles01"
```

Perintah ini mendapatkan penyebaran DeployRoles01 di cakupan langganan saat ini.
Anda dapat menetapkan nama ke penyebaran saat membuatnya dengan menggunakan cmdlet **New-AzDeployment** .
Jika Anda tidak menetapkan nama, cmdlet menyediakan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

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

### -Id
Id sumber daya penyebaran yang sepenuhnya memenuhi syarat.
contoh: /subscriptions/{subId}/providers/Microsoft.Resources/deployments/{deploymentName}

```yaml
Type: System.String
Parameter Sets: GetByDeploymentId
Aliases: DeploymentId, ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama penyebaran.

```yaml
Type: System.String
Parameter Sets: GetByDeploymentName
Aliases: DeploymentName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pre
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API pra-rilis saat secara otomatis menentukan versi mana yang akan digunakan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment

## NOTES

## RELATED LINKS
