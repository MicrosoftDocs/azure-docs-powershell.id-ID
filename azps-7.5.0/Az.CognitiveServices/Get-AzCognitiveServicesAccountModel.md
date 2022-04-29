---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CognitiveServices.dll-Help.xml
Module Name: Az.CognitiveServices
online version: https://docs.microsoft.com/powershell/module/az.cognitiveservices/get-azcognitiveservicesaccountmodel
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Get-AzCognitiveServicesAccountModel.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Get-AzCognitiveServicesAccountModel.md
ms.openlocfilehash: 47ccee9ff047f1c499d764bf8db0877b769b73c2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144240124"
---
# Get-AzCognitiveServicesAccountModel

## SYNOPSIS
Mendapatkan Model yang tersedia untuk akun Cognitive Services

## SYNTAX

### DefaultParameterSet (Default)
```
Get-AzCognitiveServicesAccountModel [[-ResourceGroupName] <String>] [-AccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzCognitiveServicesAccountModel [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan Model yang tersedia untuk akun Cognitive Services

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCognitiveServicesAccountModel -ResourceGroupName cognitive-services-resource-group -AccountName resource-name

BaseModel    :
MaxCapacity  : 3
Capabilities : {[fineTune, true]}
Deprecation  : Microsoft.Azure.Management.CognitiveServices.Models.ModelDeprecationInfo
SystemData   : Microsoft.Azure.Management.CognitiveServices.Models.SystemData
Format       : OpenAI
Name         : ada
Version      : 1

BaseModel    :
MaxCapacity  : 3
Capabilities : {[fineTune, true]}
Deprecation  : Microsoft.Azure.Management.CognitiveServices.Models.ModelDeprecationInfo
SystemData   : Microsoft.Azure.Management.CognitiveServices.Models.SystemData
Format       : OpenAI
Name         : davinci
Version      : 1
```

Mendapatkan Model yang tersedia untuk akun Cognitive Services

## PARAMETERS

### -AccountName
Nama Akun Cognitive Services.

```yaml
Type: String
Parameter Sets: DefaultParameterSet
Aliases: CognitiveServicesAccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya.

```yaml
Type: String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.CognitiveServices.Models.AccountModel

## NOTES

## RELATED LINKS

[New-AzCognitiveServicesAccountDeployment](./New-AzCognitiveServicesAccountDeployment)
