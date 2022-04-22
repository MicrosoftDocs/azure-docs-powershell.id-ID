---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/powershell/module/az.machinelearning/import-azmlwebservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Import-AzMlWebService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Import-AzMlWebService.md
ms.openlocfilehash: 741dcbe81aaee804943c0517a2985e503fbc25df
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142964729"
---
# Import-AzMlWebService

## SYNOPSIS
Mengimpor objek JSON ke dalam definisi layanan web.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.machinelearning/import-azmlwebservice) untuk informasi terbaru.

## SYNTAX

### ImporFromJSONFile
```
Import-AzMlWebService -InputFile <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ImporFromJSONString.
```
Import-AzMlWebService -JsonString <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Import-AzMlWebService mengimpor , ditentukan baik secara langsung atau dalam file yang dirujuk, dan membuat objek definisi layanan web yang bisa diteruskan ke cmdlet New-AzMlWebService.

## EXAMPLES

### Contoh 1: Mengimpor dari string
```
Import-AzMlWebService -JsonString $jsonDefinition
```

### Contoh 2: Mengimpor dari jalur file
```
Import-AzMlWebService -InputFile "C:\mlservice.json"
```

## PARAMETERS

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

### -InputFile
Jalur ke file yang berisi definisi layanan web untuk diimpor.

```yaml
Type: System.String
Parameter Sets: ImportFromJSONFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
String yang diformat JSON berisi definisi layanan web untuk diimpor.

```yaml
Type: System.String
Parameter Sets: ImportFromJSONString.
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## NOTES
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, mesin, pembelajaran mesin, azureml

## RELATED LINKS
