---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
Module Name: AzureRM.DataFactories
ms.assetid: 5224BDF5-D492-4160-893E-4BB5F76C22F3
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.datafactories/get-azurermdatafactorypipeline
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/Get-AzureRmDataFactoryPipeline.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/Get-AzureRmDataFactoryPipeline.md
ms.openlocfilehash: a22e38e03d1a754823675abbac7a847d91762d54
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142065115"
---
# Get-AzureRmDataFactoryPipeline

## SYNOPSIS
Mendapatkan informasi tentang saluran di Azure Data Factory.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureRmDataFactoryPipeline [[-Name] <String>] [-DataFactoryName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureRmDataFactoryPipeline [[-Name] <String>] [-DataFactory] <PSDataFactory>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDataFactoryPipeline** mendapatkan informasi tentang saluran di Azure Data Factory.
Jika Anda menentukan nama pipeline, cmdlet ini akan mendapatkan informasi tentang pipeline tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua pipeline di pabrik data.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua saluran
```
PS C:\>Get-AzureRmDataFactoryPipeline -ResourceGroupName "ADF" -DataFactoryName "WikiADF"
```

Perintah ini mendapatkan informasi tentang semua pipeline di pabrik data bernama WikiADF.
Anda bisa salah satu dari contoh perintah berikut ini.
Yang kedua menggunakan objek **DataFactory** sebagai parameter.

### Contoh 2: Mendapatkan informasi tentang saluran tertentu
```
PS C:\>Get-AzureRmDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF" | Format-List
PipelineName      : DPWikisample
ResourceGroupName : ADF
DataFactoryName   : WikiADF
Properties        : Microsoft.DataFactories.PipelineProperties
```

Perintah ini mendapatkan informasi tentang pipeline bernama DPWikisample di pabrik data bernama WikiADF.
Perintah akan meneruskan informasi tersebut ke cmdlet Format-List menggunakan operator pipeline.
Cmdlet itu memformat hasil.
Untuk informasi selengkapnya, ketik .`Get-Help Format-List`

### Contoh 3: Dapatkan properti untuk pipeline tertentu
```
PS C:\> (Get-AzureRmDataFactoryPipeline -ResourceGroupName "ADF" -Name DPWikisample -DataFactoryName "WikiADF").Properties
Activities  : {WikiHiveActivity, BlobToSqlCopyActivity}
Description : DP Wikipedia Sample Pipelines
End         : 6/6/2014 8:00:00 AM
IsPaused    : 
RuntimeInfo : Microsoft.DataFactories.PipelineRuntimeInfo
Start       : 6/5/2014 8:00:00 PM
```

Perintah ini mendapatkan informasi untuk pipeline bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk menampilkan properti **Properti** yang terkait dengan saluran tersebut.

### Contoh 4: Mendapatkan aktivitas untuk pipeline tertentu
```
PS C:\>(Get-AzureRmDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF").Properties.Activities
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

Perintah ini mendapatkan informasi untuk saluran bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk menampilkan properti **Aktivitas** yang terkait dengan saluran tersebut.

### Contoh 5: Mendapatkan informasi runtime untuk pipeline tertentu
```
PS C:\>(Get-AzureRmDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF").Properties.RuntimeInfo
DeploymentTime
--------------
6/5/2014 10:36:46 PM
```

Perintah ini mendapatkan informasi untuk pipeline bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk menampilkan properti **RuntimeInfo** yang terkait dengan pipeline tersebut.

### Contoh 6: Dapatkan informasi tentang input untuk aktivitas pertama
```
PS C:\>(Get-AzureRmDataFactoryPipeline -ResourceGroupName "ADF" -Name "DPWikisample" -DataFactoryName "WikiADF11").Properties.Activities[0].Inputs | Format-List
EndTime   : 
Length    : 
Name      : DAWikipediaClickEvents
StartTime :
```

Perintah ini mendapatkan informasi untuk saluran bernama DPWikisample di pabrik data bernama WikiADF, lalu menggunakan notasi titik standar untuk menampilkan properti **Aktivitas** yang terkait dengan saluran tersebut.
Perintah menampilkan properti **Input** dari elemen pertama array **Aktivitas** menggunakan **Format-List**.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini mendapatkan pipeline yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mendapatkan pipeline yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mendapatkan pipeline yang termasuk dalam grup yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSPipeline

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[AzureRmDataFactoryPipeline baru](./New-AzureRmDataFactoryPipeline.md)

[Hapus-AzureRmDataFactoryPipeline](./Remove-AzureRmDataFactoryPipeline.md)

[Resume-AzureRmDataFactoryPipeline](./Resume-AzureRmDataFactoryPipeline.md)

[Set-AzureRmDataFactoryPipelineActivePeriod](./Set-AzureRmDataFactoryPipelineActivePeriod.md)

[Suspend-AzureRmDataFactoryPipeline](./Suspend-AzureRmDataFactoryPipeline.md)


