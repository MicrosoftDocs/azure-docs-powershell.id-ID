---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeployment.md
ms.openlocfilehash: 49c7d0bcc68e8f9e6a2d045ab06917779a2cd231
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140460407"
---
# Get-AzDeployment

## SYNOPSIS
Mendapatkan penggunaan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/get-azdeployment) untuk informasi terkini.

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
Cmdlet **Get-AzDeployment** mendapatkan penyebaran di lingkup langganan saat ini.
Tentukan parameter *Nama* *atau Id* untuk memfilter hasilnya.
Secara default, **Get-AzDeployment** mendapatkan semua penyebaran di lingkup langganan saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyebaran di lingkup langganan
```
PS C:\>Get-AzDeployment
```

Perintah ini mendapatkan semua penyebaran pada lingkup langganan saat ini.

### Contoh 2: Mendapatkan penyebaran menurut nama
```
PS C:\>Get-AzDeployment -Name "DeployRoles01"
```

Perintah ini menerapkan DeployRoles01 pada lingkup langganan saat ini.
Anda bisa menetapkan nama untuk penyebaran saat Anda membuatnya dengan menggunakan cmdlet **New-AzDeployment** .
Jika Anda tidak memberi nama, cmdlet memberikan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

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
Saat diatur, cmdlet harus menggunakan versi API prari tamu ketika menentukan versi mana yang akan digunakan secara otomatis.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment

## CATATAN

## RELATED LINKS
