---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-aztenantdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzTenantDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzTenantDeployment.md
ms.openlocfilehash: d92ec2ba015a2f10fbc2ff2f0bc27d272f47fc72
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142317641"
---
# Get-AzTenantDeployment

## SYNOPSIS
Dapatkan penggunaan di lingkup penyewa

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-aztenantdeployment) untuk informasi terbaru.

## SYNTAX

### GetByDeploymentName (Default)
```
Get-AzTenantDeployment [[-Name] <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByDeploymentId
```
Get-AzTenantDeployment -Id <String> [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzTenantDeployment** mendapatkan penyebaran di lingkup penyewa.
Tentukan parameter *Nama* atau *Id* untuk memfilter hasil.
Secara default, **Get-AzTenantDeployment** mendapatkan semua penyebaran di lingkup penyewa.

## EXAMPLES

### Contoh 1: Dapatkan semua penyebaran di lingkup penyewa
```
PS C:\>Get-AzTenantDeployment
```

Perintah ini mendapatkan semua penyebaran pada lingkup penyewa saat ini.

### Contoh 2: Mendapatkan penyebaran berdasarkan nama
```
PS C:\>Get-AzDeployment -Name "Deploy01"
```

Perintah ini mendapatkan penyebaran "Deploy01" di lingkup penyewa saat ini.
Anda dapat menetapkan nama untuk penyebaran saat membuatnya menggunakan cmdlet **New-AzTenantDeployment** .
Jika Anda tidak menetapkan nama, cmdlet menyediakan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

### Contoh 3: Dapatkan penyebaran menurut ID
```
PS C:\>Get-AzDeployment -Id "/providers/Microsoft.Resources/deployments/Deploy01"
```

Perintah ini mendapatkan penyebaran "Deploy01" di lingkup penyewa.

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
contoh: /providers/Microsoft.Resources/deployments/{deploymentName}

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

## CATATAN

## RELATED LINKS
