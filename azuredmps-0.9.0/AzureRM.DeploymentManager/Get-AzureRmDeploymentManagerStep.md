---
external help file: Microsoft.Azure.Commands.DeploymentManager.dll-Help.xml
Module Name: AzureRM.DeploymentManager
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.deploymentmanager/get-azurermdeploymentmanagerstep
schema: 2.0.0
ms.openlocfilehash: bd17ee5dd653ee66daf014c57661b3787c04b06f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141930921"
---
# Get-AzureRmDeploymentManagerStep

## SYNOPSIS
Mendapatkan langkah penyebaran.

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
Tentukan langkah menurut nama dan nama grup sumber dayanya. Alternatifnya, Anda bisa menyediakan objek Langkah atau ResourceId.

Anda dapat mengubah objek ini secara lokal, lalu menerapkan perubahan ke sumber artefak menggunakan cmdlet Set-AzureRmDeploymentManagerStep.

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

 Perintah ini mendapatkan langkah yang namanya dan ResourceGroup masing-masing cocok dengan properti Name and ResourceGroupName dari $stepObject.


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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DeploymentManager.Models.PSStepResource

## OUTPUTS

### Microsoft.Azure.Commands.DeploymentManager.Models.PSStepResource

## CATATAN

## RELATED LINKS
