---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: B07FE1A2-732D-4CCF-A0DF-3CF6B91FB3F3
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactoryhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryHub.md
ms.openlocfilehash: 456a008c81a8f401dd4834f4c53d5aa993faab72
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142842274"
---
# Get-AzDataFactoryHub

## SYNOPSIS
Mendapatkan informasi tentang hub di Azure Data Factory.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datafactory/get-azdatafactoryhub) untuk informasi terbaru.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzDataFactoryHub [[-Name] <String>] [-DataFactoryName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzDataFactoryHub [[-Name] <String>] [-DataFactory] <PSDataFactory>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataFactoryHub** mendapatkan informasi tentang hub di Azure Data Factory.
Jika Anda menentukan nama hub, cmdlet ini akan mendapatkan informasi tentang hub tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua hub dalam pabrik data.

## EXAMPLES

### Contoh 1: Dapatkan semua hub data
```
PS C:\>Get-AzDataFactoryHub -ResourceGroupName "ADFResourceGroup" -DataFactoryName "ADFDataFactory"
```

Perintah ini mendapatkan semua hub data dalam grup sumber daya Azure bernama ADFResourceGroup dan pabrik data bernama ADFDataFactory.

### Contoh 2: Mendapatkan hub data tertentu
```
PS C:\>Get-AzDataFactoryHub -ResourceGroupName "ADFResourceGroup" -DataFactoryName "ADFDataFactory" -Name "MyDataHub"
```

Perintah ini mendapatkan informasi tentang hub bernama MyDataHub dalam grup sumber daya Azure bernama ADFResourceGroup dan pabrik data bernama ADFDataFactory.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini mendapatkan informasi tentang hub di pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mendapatkan informasi tentang hub di pabrik data yang ditentukan parameter ini.

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

### -Nama
Menentukan nama hub yang akan mendapatkan informasi.

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
Cmdlet ini mendapatkan informasi tentang hub yang termasuk dalam grup yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSHub

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[New-AzDataFactoryHub](./New-AzDataFactoryHub.md)

[Remove-AzDataFactoryHub](./Remove-AzDataFactoryHub.md)


