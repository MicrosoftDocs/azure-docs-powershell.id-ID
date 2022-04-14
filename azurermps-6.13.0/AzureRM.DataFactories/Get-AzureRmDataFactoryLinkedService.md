---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
Module Name: AzureRM.DataFactories
ms.assetid: DFA41A2B-7C8A-42CB-B0B6-5E6FF853EFEE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.datafactories/get-azurermdatafactorylinkedservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/Get-AzureRmDataFactoryLinkedService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/Get-AzureRmDataFactoryLinkedService.md
ms.openlocfilehash: 8a6553547bd75aeaaca8e96a85c9697d00ee65a1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142099240"
---
# Get-AzureRmDataFactoryLinkedService

## SYNOPSIS
Mendapatkan informasi tentang layanan tertaut di Azure Data Factory.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureRmDataFactoryLinkedService [-DataFactoryName] <String> [[-Name] <String>]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureRmDataFactoryLinkedService [-DataFactory] <PSDataFactory> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDataFactoryLinkedService** mendapatkan informasi tentang layanan tertaut di Azure Data Factory.
Jika Anda menentukan nama layanan yang ditautkan, cmdlet ini akan mendapatkan informasi tentang layanan tertaut tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua layanan yang ditautkan di pabrik data.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua layanan tertaut
```
PS C:\>Get-AzureRmDataFactoryLinkedService -ResourceGroupName "ADF" -DataFactoryName "WikiADF" | Format-List
```

Perintah ini mendapatkan informasi tentang semua layanan tertaut di pabrik data bernama WikiADF, lalu mengirimkan layanan tertaut ke cmdlet Format-List dengan menggunakan operator pipeline.
Cmdlet itu memformat hasil.
Untuk informasi selengkapnya, ketik .`Get-Help Format-List`

### Contoh 2: Dapatkan informasi tentang layanan tertaut tertentu
```
PS C:\>Get-AzureRmDataFactoryLinkedService -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "HDILinkedService"
LinkedServiceName   ResourceGroupName     DataFactoryName              Properties
-----------------   -----------------     ---------------              ----------
HDILinkedService    ADF                   WikiADF                      Microsoft.DataFactories.HDInsightBYOCAsset
```

Perintah ini mendapatkan informasi tentang layanan tertaut bernama HDILinkedService di pabrik data bernama WikiADF.

### Contoh 3: Dapatkan informasi tentang layanan tertaut tertentu dengan menentukan parameter DataFactory
```
PS C:\>$DataFactory = Get-AzureRmDataFactory -ResourceGroupName "ADF" -Name "ContosoFactory"
PS C:\> Get-AzureRmDataFactoryLinkedService -DataFactory $DataFactory | Format-Table -Property LinkedServiceName, DataFactoryName, ResourceGroupName
```

Perintah pertama menggunakan cmdlet Get-AzureRmDataFactory untuk mendapatkan pabrik data bernama ContosoFactory, lalu menyimpannya dalam variabel $DataFactory.
Perintah kedua mendapatkan informasi tentang layanan tertaut untuk pabrik data yang disimpan di $DataFactory, lalu mengirimkan informasi tersebut ke cmdlet Format-Table dengan menggunakan operator pipeline.
**Format-Tabel** memformat output sebagai kumpulan data dengan properti tertentu sebagai kolom kumpulan data.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini mendapatkan layanan tertaut milik pabrik data yang ditentukan parameter ini.

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
Menentukan nama layanan yang ditautkan tentang mana yang akan mendapatkan informasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSLinkedService

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[New-AzureRmDataFactoryLinkedService](./New-AzureRmDataFactoryLinkedService.md)

[Hapus-AzureRmDataFactoryLinkedService](./Remove-AzureRmDataFactoryLinkedService.md)


