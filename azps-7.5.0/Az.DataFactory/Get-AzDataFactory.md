---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: ECE1F469-E3C3-4294-A288-8BAE851E8599
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactory.md
ms.openlocfilehash: 04508c196d147f12a02a79b9c08c4cf54171e1a8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144204492"
---
# Get-AzDataFactory

## SYNOPSIS
Mendapatkan informasi tentang Data Factory.

## SYNTAX

```
Get-AzDataFactory [[-Name] <String>] [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataFactory** mendapatkan informasi tentang pabrik data dalam grup sumber daya Azure.
Jika Anda menentukan nama pabrik data, cmdlet ini mendapatkan informasi tentang pabrik data tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua pabrik data dalam grup sumber daya Azure.

## EXAMPLES

### Contoh 1: Mendapatkan semua pabrik data
```powershell
Get-AzDataFactory -ResourceGroupName "ADF"
```

```output
DataFactoryName   : WikiADF
ResourceGroupName : ADF
Location          : WestUS
Tags              : {}
Properties        : Microsoft.WindowsAzure.Commands.Utilities.PSDataFactoryConfiguration

DataFactoryName   : WikiADF2
ResourceGroupName : ADF
Location          : westus
Tags              : {}
Properties        : Microsoft.WindowsAzure.Commands.Utilities.PSDataFactoryConfiguration
```

Perintah ini menampilkan informasi tentang semua pabrik data di langganan Azure.

### Contoh 2: Mendapatkan pabrik data tertentu
```powershell
$DataFactory = Get-AzDataFactory -ResourceGroupName "ADF" -Name "WikiADF"
```

```output
DataFactoryName   : WikiADF
ResourceGroupName : ADF
Location          : westus
Tags              : {}
Properties        : Microsoft.WindowsAzure.Commands.Utilities.PSDataFactoryConfiguration
```

Perintah ini menampilkan informasi tentang pabrik data bernama WikiADF dalam langganan untuk grup sumber daya bernama ADF, lalu menyimpannya dalam variabel $DataFactory.
Tentukan parameter *DataFactory* dalam cmdlet berikutnya untuk menggunakan pabrik data yang disimpan di $DataFactory.

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

### -Name
Menentukan nama pabrik data yang akan mendapatkan informasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure.
Cmdlet ini mendapatkan informasi tentang pabrik data yang termasuk dalam grup yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

## NOTES
* Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[New-AzDataFactory](./New-AzDataFactory.md)

[Remove-AzDataFactory](./Remove-AzDataFactory.md)


