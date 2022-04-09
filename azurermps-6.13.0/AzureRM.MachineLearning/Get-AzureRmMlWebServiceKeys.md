---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
Module Name: AzureRM.MachineLearning
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.machinelearning/get-azurermmlwebservicekeys
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/MachineLearning/Commands.MachineLearning/help/Get-AzureRmMlWebServiceKeys.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/MachineLearning/Commands.MachineLearning/help/Get-AzureRmMlWebServiceKeys.md
ms.openlocfilehash: 194ee5a6a8526aff060f359ff86a7c50421825bc755551f9472146626928e04c
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140851377"
---
# Get-AzureRmMlWebServiceKeys

## SYNOPSIS
Mengambil kunci layanan web.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByNameAndResourceGroup
```
Get-AzureRmMlWebServiceKeys -ResourceGroupName <String> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByInstance
```
Get-AzureRmMlWebServiceKeys -MlWebService <WebService> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan tombol akses untuk API runtime Azure Machine Learning web service.

## EXAMPLES

### Contoh 1 - Mendapatkan kunci untuk layanan web yang ditentukan oleh grup dan nama sumber daya
```
Get-AzureRmMlWebServiceKeys -ResourceGroupName "myresourcegroup" -Name "mywebservicename"
```

### Contoh 2 - Dapatkan kunci untuk instans layanan web
```
Get-AzureRmMlWebServiceKeys -MlWebService $mlService
```

$mlService merupakan objek tipe Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -MlWebService
Nama layanan web tempat kunci akses diambil.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService
Parameter Sets: GetByInstance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama layanan web tempat kunci akses diambil.

```yaml
Type: System.String
Parameter Sets: GetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya untuk layanan web.

```yaml
Type: System.String
Parameter Sets: GetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService
Parameter: MlWebService (ByValue)

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebServiceKeys

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS
