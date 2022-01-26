---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: DFA41A2B-7C8A-42CB-B0B6-5E6FF853EFEE
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactorylinkedservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryLinkedService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryLinkedService.md
ms.openlocfilehash: 1bf02d4ce96489a5c2fc14fce10ebcad2bc76cc7
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136706599"
---
# Get-AzDataFactoryLinkedService

## SYNOPSIS
Mendapatkan informasi tentang layanan tertaut di Azure Data Factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzDataFactoryLinkedService [-DataFactoryName] <String> [[-Name] <String>] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzDataFactoryLinkedService [-DataFactory] <PSDataFactory> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataFactoryLinkedService mendapatkan** informasi tentang layanan yang ditautkan di Azure Data Factory.
Jika Anda menentukan nama layanan tertaut, cmdlet ini mendapatkan informasi tentang layanan tertaut tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua layanan yang ditautkan di pabrik data.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang semua layanan tertaut
```
PS C:\>Get-AzDataFactoryLinkedService -ResourceGroupName "ADF" -DataFactoryName "WikiADF" | Format-List
```

Perintah ini mendapatkan informasi tentang semua layanan yang ditautkan di pabrik data yang bernama WikiADF, lalu meneruskan layanan tertaut ke cmdlet Format-List dengan menggunakan operator pipeline.
Cmdlet tersebut memformat hasilnya.
Untuk informasi selengkapnya, ketik `Get-Help Format-List` .

### Contoh 2: Mendapatkan informasi tentang layanan tertaut tertentu
```
PS C:\>Get-AzDataFactoryLinkedService -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "HDILinkedService"
LinkedServiceName   ResourceGroupName     DataFactoryName              Properties
-----------------   -----------------     ---------------              ----------
HDILinkedService    ADF                   WikiADF                      Microsoft.DataFactories.HDInsightBYOCAsset
```

Perintah ini mendapatkan informasi tentang layanan tertaut yang bernama HDILinkedService di pabrik data bernama WikiADF.

### Contoh 3: Dapatkan informasi tentang layanan tertaut tertentu dengan menentukan parameter DataFactory
```
PS C:\>$DataFactory = Get-AzDataFactory -ResourceGroupName "ADF" -Name "ContosoFactory"
PS C:\> Get-AzDataFactoryLinkedService -DataFactory $DataFactory | Format-Table -Property LinkedServiceName, DataFactoryName, ResourceGroupName
```

Perintah pertama menggunakan cmdlet Get-AzDataFactory cmdlet untuk mendapatkan pabrik data bernama ContosoFactory, lalu menyimpannya di $DataFactory lain.
Perintah kedua mendapatkan informasi tentang layanan yang ditautkan untuk pabrik data yang disimpan di $DataFactory, lalu meneruskan informasi itu ke cmdlet Format-Table dengan menggunakan operator pipeline.
**Format-Tabel** memformat output sebagai set data dengan properti yang ditentukan sebagai kolom set data.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory.**
Cmdlet ini mendapatkan layanan tertaut yang termasuk dalam pabrik data yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory
Parameter Sets: ByFactoryObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataFactoryName
Menentukan nama pabrik data.
Cmdlet ini mendapatkan layanan tertaut yang termasuk dalam pabrik data yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: ByFactoryName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Menentukan nama layanan tertaut yang akan mendapatkan informasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure.
Cmdlet ini mendapatkan layanan tertaut yang termasuk dalam grup yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: ByFactoryName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSLinkedService

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, data, factories

## RELATED LINKS

[New-AzDataFactoryLinkedService](./New-AzDataFactoryLinkedService.md)

[Remove-AzDataFactoryLinkedService](./Remove-AzDataFactoryLinkedService.md)


