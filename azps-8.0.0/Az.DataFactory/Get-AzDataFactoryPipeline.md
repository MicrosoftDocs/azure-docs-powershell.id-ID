---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: 5224BDF5-D492-4160-893E-4BB5F76C22F3
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactorypipeline
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryPipeline.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryPipeline.md
ms.openlocfilehash: fc5f1470aff36f4136b9a2f798928f4ef2e64955
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145619515"
---
# Get-AzDataFactoryPipeline

## SYNOPSIS
Mendapatkan informasi tentang alur di Azure Data Factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzDataFactoryPipeline [[-Name] <String>] [-DataFactoryName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzDataFactoryPipeline [[-Name] <String>] [-DataFactory] <PSDataFactory>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataFactoryPipeline** mendapatkan informasi tentang alur di Azure Data Factory.
Jika Anda menentukan nama alur, cmdlet ini mendapatkan informasi tentang alur tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua alur di pabrik data.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang semua alur
```powershell
Get-AzDataFactoryPipeline -ResourceGroupName "ADF" -DataFactoryName "WikiADF"
```

Perintah ini mendapatkan informasi tentang semua alur di pabrik data bernama WikiADF.
Anda dapat salah satu dari contoh perintah berikut.
Yang kedua menggunakan objek **DataFactory** sebagai parameter.

### Contoh 2: Mendapatkan informasi tentang alur tertentu
```powershell
Get-AzDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF" | Format-List
```

```output
PipelineName      : DPWikisample
ResourceGroupName : ADF
DataFactoryName   : WikiADF
Properties        : Microsoft.DataFactories.PipelineProperties
```

Perintah ini mendapatkan informasi tentang alur bernama DPWikisample di pabrik data bernama WikiADF.
Perintah meneruskan informasi tersebut ke cmdlet Format-List dengan menggunakan operator alur.
Cmdlet tersebut memformat hasilnya.
Untuk informasi selengkapnya, ketik `Get-Help Format-List`.

### Contoh 3: Mendapatkan properti untuk alur tertentu
```powershell
(Get-AzDataFactoryPipeline -ResourceGroupName "ADF" -Name DPWikisample -DataFactoryName "WikiADF").Properties
```

```output
Activities  : {WikiHiveActivity, BlobToSqlCopyActivity}
Description : DP Wikipedia Sample Pipelines
End         : 6/6/2014 8:00:00 AM
IsPaused    : 
RuntimeInfo : Microsoft.DataFactories.PipelineRuntimeInfo
Start       : 6/5/2014 8:00:00 PM
```

Perintah ini mendapatkan informasi untuk alur bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk melihat properti **Properti** yang terkait dengan alur tersebut.

### Contoh 4: Mendapatkan aktivitas untuk alur tertentu
```powershell
(Get-AzDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF").Properties.Activities
```

```output
Transformation    : Microsoft.DataFactories.HDInsightActivityProperties
Description       : 
Inputs            : {DAWikipediaClickEvents}
LinkedServiceName : HDILinkedService
Name              : WikiHiveActivity
Outputs           : {DACuratedWikiData}
Policy            : Microsoft.DataFactories.ActivityPolicy

Transformation    : Microsoft.DataFactories.CopyActivityProperties
Description       : 
Inputs            : {DACuratedWikiData}
LinkedServiceName : HDILinkedService
Name              : BlobToSqlCopyActivity
Outputs           : {DAWikiAggregatedData}
Policy            : Microsoft.DataFactories.ActivityPolicy
```

Perintah ini mendapatkan informasi untuk alur bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk melihat properti **Aktivitas** yang terkait dengan alur tersebut.

### Contoh 5: Mendapatkan informasi runtime untuk alur tertentu
```powershell
(Get-AzDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF").Properties.RuntimeInfo
```

```output
DeploymentTime
--------------
6/5/2014 10:36:46 PM
```

Perintah ini mendapatkan informasi untuk alur bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk melihat properti **RuntimeInfo** yang terkait dengan alur tersebut.

### Contoh 6: Mendapatkan informasi tentang input untuk aktivitas pertama
```powershell
(Get-AzDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF11").Properties.Activities[0].Inputs | Format-List
```

```output
EndTime   : 
Length    : 
Name      : DAWikipediaClickEvents
StartTime :
```

Perintah ini mendapatkan informasi untuk alur bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk melihat properti **Aktivitas** yang terkait dengan alur tersebut.
Perintah menampilkan properti **Input** dari elemen pertama dari array **Aktivitas** dengan menggunakan **Format-List**.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini mendapatkan alur milik pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mendapatkan alur milik pabrik data yang ditentukan parameter ini.

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
Menentukan nama alur untuk mendapatkan informasi.

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
Cmdlet ini mendapatkan alur yang termasuk dalam grup yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSPipeline

## NOTES
* Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[New-AzDataFactoryPipeline](./New-AzDataFactoryPipeline.md)

[Remove-AzDataFactoryPipeline](./Remove-AzDataFactoryPipeline.md)

[Resume-AzDataFactoryPipeline](./Resume-AzDataFactoryPipeline.md)

[Set-AzDataFactoryPipelineActivePeriod](./Set-AzDataFactoryPipelineActivePeriod.md)

[Suspensi-AzDataFactoryPipeline](./Suspend-AzDataFactoryPipeline.md)


