---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeployment.md
ms.openlocfilehash: 49c7d0bcc68e8f9e6a2d045ab06917779a2cd231
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143086031"
---
# Get-AzDeployment

## SYNOPSIS
Dapatkan penyebaran

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azdeployment) untuk informasi terbaru.

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
Cmdlet **Get-AzDeployment** mendapatkan penyebaran pada lingkup langganan saat ini.
Tentukan parameter *Nama* atau *Id* untuk memfilter hasil.
Secara default, **Get-AzDeployment** mendapatkan semua penyebaran pada lingkup langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan semua penyebaran di lingkup langganan
```
PS C:\>Get-AzDeployment
```

Perintah ini mendapatkan semua penyebaran pada lingkup langganan saat ini.

### Contoh 2: Mendapatkan penyebaran berdasarkan nama
```
PS C:\>Get-AzDeployment -Name "DeployRoles01"
```

Perintah ini mendapatkan penyebaran DeployRoles01 pada lingkup langganan saat ini.
Anda dapat menetapkan nama untuk penyebaran saat membuatnya menggunakan cmdlet **New-AzDeployment** .
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
Id sumber daya yang sepenuhnya memenuhi syarat dari penyebaran.
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

### -Nama
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

### -Pra
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API prarilis saat menentukan versi mana yang akan digunakan secara otomatis.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment

## NOTES

## RELATED LINKS
