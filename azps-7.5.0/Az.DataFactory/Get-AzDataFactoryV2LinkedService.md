---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactoryV2.dll-Help.xml
Module Name: Az.DataFactory
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactoryv2linkedservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryV2LinkedService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryV2LinkedService.md
ms.openlocfilehash: b6fa397d97cc0c6e9a7ee36029406e178b633d4d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144204209"
---
# Get-AzDataFactoryV2LinkedService

## SYNOPSIS
Mendapatkan informasi tentang layanan tertaut di Data Factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzDataFactoryV2LinkedService [[-Name] <String>] [-ResourceGroupName] <String> [-DataFactoryName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzDataFactoryV2LinkedService [[-Name] <String>] [-DataFactory] <PSDataFactory>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceId
```
Get-AzDataFactoryV2LinkedService [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzDataFactoryV2LinkedService mendapatkan informasi tentang layanan tertaut di Azure Data Factory.
Jika Anda menentukan nama layanan tertaut, cmdlet ini mendapatkan informasi tentang layanan tertaut tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua layanan tertaut di pabrik data.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang semua layanan tertaut
```powershell
Get-AzDataFactoryV2LinkedService -ResourceGroupName "ADF" -DataFactoryName "WikiADF" | Format-List
```

```output
    LinkedServiceName : LinkedServiceCuratedWikiData
    ResourceGroupName : ADF
    DataFactoryName   : WikiADF
    Properties        : Microsoft.Azure.Management.DataFactory.Models.AzureStorageLinkedService

    LinkedServiceName : LinkedServiceHDIStorage
    ResourceGroupName : ADF
    DataFactoryName   : WikiADF
    Properties        : Microsoft.Azure.Management.DataFactory.Models.AzureStorageLinkedService

    LinkedServiceName : LinkedServiceWikipediaClickEvents
    ResourceGroupName : ADF
    DataFactoryName   : WikiADF
    Properties        : Microsoft.Azure.Management.DataFactory.Models.AzureStorageLinkedService
```

Perintah ini mendapatkan informasi tentang semua layanan tertaut di pabrik data bernama WikiADF, lalu meneruskan layanan tertaut ke cmdlet Format-List dengan menggunakan operator alur.
Cmdlet Windows PowerShell memformat hasilnya.
Untuk informasi selengkapnya, ketik Get-Help Format-List.
Anda bisa menggunakan salah satu cara berikut:

### Contoh 2: Mendapatkan informasi tentang layanan tertaut tertentu
```powershell
Get-AzDataFactoryV2LinkedService -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "LinkedServiceCuratedWikiData"
```

```output
    LinkedServiceName : LinkedServiceCuratedWikiData
    ResourceGroupName : ADF
    DataFactoryName   : WikiADF
    Properties        : Microsoft.Azure.Management.DataFactory.Models.AzureStorageLinkedService
```

Perintah ini mendapatkan informasi tentang layanan tertaut bernama LinkedServiceCuratedWikiData di pabrik data bernama WikiADF.

### Contoh 3: Mendapatkan informasi tentang layanan tertaut tertentu dengan menentukan parameter DataFactory
```powershell
$DataFactory = Get-AzDataFactoryV2 -ResourceGroupName "ADF" -Name "ContosoFactory"
Get-AzDataFactoryV2LinkedService -DataFactory $DataFactory | Format-Table -Property Name, DataFactoryName, ResourceGroupName
```

```output
     Name                          DataFactoryName ResourceGroupName
     ----                          --------------- -----------------
     LinkedServiceCuratedWikiData  ContosoFactory  ADF
```

Perintah pertama menggunakan cmdlet Get-AzDataFactoryV2 untuk mendapatkan pabrik data bernama ContosoFactory, lalu menyimpannya dalam variabel $DataFactory.
Perintah kedua mendapatkan informasi tentang layanan tertaut untuk pabrik data yang disimpan di $DataFactory, lalu meneruskan informasi tersebut ke cmdlet Format-Table dengan menggunakan operator alur.
Cmdlet Format-Table memformat output sebagai himpunan data dengan properti yang ditentukan sebagai kolom himpunan data.

## PARAMETERS

### -DataFactory
Menentukan objek PSDataFactory.
Cmdlet ini mendapatkan layanan tertaut milik pabrik data yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.DataFactoryV2.Models.PSDataFactory
Parameter Sets: ByFactoryObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DataFactoryName
Menentukan nama pabrik data.
Cmdlet ini mendapatkan layanan tertaut milik pabrik data yang ditentukan parameter ini.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan nama layanan tertaut yang akan mendapatkan informasi.

```yaml
Type: System.String
Parameter Sets: ByFactoryName, ByFactoryObject
Aliases: LinkedServiceName

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

### -ResourceId
ID sumber daya Azure.

```yaml
Type: System.String
Parameter Sets: ByResourceId
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

### Microsoft.Azure.Commands.DataFactoryV2.Models.PSDataFactory

## OUTPUTS

### Microsoft.Azure.Commands.DataFactoryV2.Models.PSLinkedService

## NOTES
Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[Set-AzDataFactoryV2LinkedService]()

[Remove-AzDataFactoryV2LinkedService]()
