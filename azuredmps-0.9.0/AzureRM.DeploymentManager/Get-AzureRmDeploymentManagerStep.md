---
external help file: Microsoft.Azure.Commands.DeploymentManager.dll-Help.xml
Module Name: AzureRM.DeploymentManager
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.deploymentmanager/get-azurermdeploymentmanagerstep
schema: 2.0.0
ms.openlocfilehash: 2d1e10c8a54e0ee9da0aaec03833becdd6478c48da9ca802b65d8d1447903f1b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416154"
---
# Get-AzureRmDeploymentManagerStep

## SYNOPSIS
Mendapatkan langkah penggunaan.

## SYNTAX

### Interaktif (Default)
```
Get-AzureRmDeploymentManagerStep [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzureRmDeploymentManagerStep [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### InputObject
```
Get-AzureRmDeploymentManagerStep [-Step] <PSStepResource> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDeploymentManagerStep** mendapatkan langkah, dan mengembalikan objek yang mewakili langkah tersebut.
Tentukan langkah berdasarkan namanya dan nama grup sumber daya. Alternatifnya, Anda bisa menyediakan objek Langkah atau ResourceId.

Anda bisa mengubah objek ini secara lokal, lalu menerapkan perubahan ke sumber artifak dengan menggunakan cmdlet Set-AzureRmDeploymentManagerStep.

## EXAMPLES

### Contoh 1: Dapatkan langkah
```powershell
PS C:\> New-AzureRmDeploymentManagerStep -ResourceGroupName ContosoResourceGroup -Name ContosoService1WaitStep
```

Perintah ini mendapatkan langkah bernama ContosoService1WaitStep di ContosoResourceGroup.

### Contoh 2: Dapatkan langkah menggunakan pengidentifikasi sumber daya
```powershell
PS C:\> Get-AzureRmDeploymentManagerStep -ResourceId "/subscriptions/subscriptionId/resourcegroups/ContosoResourceGroup/providers/Microsoft.DeploymentManager/steps/ContosoService1WaitStep"
```

Perintah ini mendapatkan langkah bernama ContosoService1WaitStep di ContosoResourceGroup.

### Contoh 3: Mendapatkan langkah menggunakan objek yang dikembalikan oleh New-AzureRmDeploymentManagerStep
```powershell
PS C:\> Get-AzureRmDeploymentManagerStep -Step $stepObject
```

 Perintah ini mendapatkan langkah yang namanya dan Grup Sumber Dayanya sesuai dengan properti Nama dan ResourceGroupName $stepObject, secara berurutan.


## PARAMETERS

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
Nama langkah.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Langkah
Objek sumber daya langkah.

```yaml
Type: Microsoft.Azure.Commands.DeploymentManager.Models.PSStepResource
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### Microsoft.Azure.Commands.DeploymentManager.Models.PSStepResource

## OUTPUTS

### Microsoft.Azure.Commands.DeploymentManager.Models.PSStepResource

## CATATAN

## RELATED LINKS
