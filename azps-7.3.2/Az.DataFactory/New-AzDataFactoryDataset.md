---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: 352A4B94-E433-413B-91D1-6AA347563959
online version: https://docs.microsoft.com/powershell/module/az.datafactory/new-azdatafactorydataset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/New-AzDataFactoryDataset.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/New-AzDataFactoryDataset.md
ms.openlocfilehash: 4becdedaf9db853dae73ac449e77ff8f47ad243f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142702360"
---
# New-AzDataFactoryDataset

## SYNOPSIS
Membuat kumpulan data di Pabrik Data.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datafactory/new-azdatafactorydataset) untuk informasi terbaru.

## SYNTAX

### ByFactoryName (Default)
```
New-AzDataFactoryDataset [-DataFactoryName] <String> [[-Name] <String>] [-File] <String> [-Force]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByFactoryObject
```
New-AzDataFactoryDataset [-DataFactory] <PSDataFactory> [[-Name] <String>] [-File] <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDataFactoryDataset** membuat kumpulan data dalam Azure Data Factory.
Jika Anda menentukan nama untuk kumpulan data yang sudah ada, cmdlet ini meminta konfirmasi sebelum menggantikan kumpulan data.
Jika Anda menentukan parameter *Paksa* , cmdlet menggantikan kumpulan data yang sudah ada tanpa konfirmasi.
Lakukan operasi ini dalam urutan berikut: 
- Membuat pabrik data. 
- Membuat layanan tertaut. 
- Membuat kumpulan data. 
- Membuat saluran.
Jika kumpulan data dengan nama yang sama sudah ada di pabrik data, cmdlet ini meminta Anda untuk mengonfirmasi apakah akan menimpa kumpulan data yang sudah ada dengan kumpulan data baru.
Jika Anda mengonfirmasi untuk menimpa kumpulan data yang sudah ada, definisi kumpulan data juga diganti.

## EXAMPLES

### Contoh 1: Membuat kumpulan data
```
PS C:\>New-AzDataFactoryDataset -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "DAWikipediaClickEvents" -File "C:\\samples\\WikiSample\\DA_WikipediaClickEvents.json"
DatasetName         : DAWikipediaClickEvents
ResourceGroupName : ADF
DataFactoryName   : WikiADF
Availability      : Microsoft.DataFactories.Availability
Location          : Microsoft.DataFactories.AzureBlobLocation
Policy            : Microsoft.DataFactories.Policy
Structure         : {}
```

Perintah ini membuat kumpulan data bernama DA_WikipediaClickEvents di pabrik data bernama WikiADF.
Perintah mendasarkan kumpulan data pada informasi dalam file DAWikipediaClickEvents.json.

### Contoh 2: Menampilkan ketersediaan untuk kumpulan data baru
```
PS C:\>$Dataset = New-AzDataFactoryDataset -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "DAWikipediaClickEvents" -File "C:\\samples\\WikiSample\\DA_WikipediaClickEvents.json"
PS C:\> $Dataset.Availability
AnchorDateTime : 
Frequency      : Hour
Interval       : 1
Offset         : 
WaitOnExternal : Microsoft.DataFactories.WaitOnExternal
```

Perintah pertama membuat kumpulan data bernama DA_WikipediaClickEvents, seperti dalam contoh sebelumnya, lalu menetapkan kumpulan data tersebut ke variabel $Dataset.
Perintah kedua menggunakan notasi titik standar untuk menampilkan detail tentang properti Ketersediaan kumpulan data.

### Contoh 3: Menampilkan lokasi untuk kumpulan data baru
```
PS C:\>$Dataset = New-AzDataFactoryDataset -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "DAWikipediaClickEvents" -File "C:\\samples\\WikiSample\\DA_WikipediaClickEvents.json"
PS C:\> $Dataset.Location
BlobPath          : wikidatagateway/wikisampledatain/
FilenamePrefix    : 
Format            : 
LinkedServiceName : LinkedServiceWikipediaClickEvents
PartitionBy       : {}
```

Perintah pertama membuat kumpulan data bernama DA_WikipediaClickEvents, seperti dalam contoh sebelumnya, lalu menetapkan kumpulan data tersebut ke variabel $Dataset.
Perintah kedua menampilkan detail tentang properti Lokasi kumpulan data.

### Contoh 4: Menampilkan aturan validasi untuk kumpulan data baru
```
PS C:\>$Dataset = New-AzDataFactoryDataset -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "DAWikipediaClickEvents" -File "C:\\samples\\WikiSample\\DA_WikipediaClickEvents.json"
PS C:\> $Dataset.Policy.Validation | Format-List $dataset.Location
BlobPath          : wikidatagateway/wikisampledatain/
FilenamePrefix    : 
Format            : 
LinkedServiceName : LinkedServiceWikipediaClickEvents
PartitionBy       : {}

MinimumRows   : 
MinimumSizeMB : 1
```

Perintah pertama membuat kumpulan data bernama DA_WikipediaClickEvents, seperti dalam contoh sebelumnya, lalu menetapkan kumpulan data tersebut ke variabel $Dataset.
Perintah kedua mendapatkan detail tentang aturan validasi untuk kumpulan data, lalu mengirimkannya ke cmdlet Format-List menggunakan operator pipeline.
Cmdlet Windows PowerShell itu memformat hasil.
Untuk informasi selengkapnya, ketik .`Get-Help Format-List`

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini membuat kumpulan data di pabrik data yang ditentukan parameter ini.

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
Cmdlet ini membuat kumpulan data di pabrik data yang ditentukan parameter ini.

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

### -File
Menentukan jalur lengkap file JavaScript Object Notation (JSON) yang berisi deskripsi kumpulan data.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
Menunjukkan bahwa cmdlet ini menggantikan kumpulan data yang sudah ada tanpa meminta konfirmasi kepada Anda.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama kumpulan data yang akan dibuat.

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
Cmdlet ini membuat kumpulan data dalam grup yang ditentukan parameter ini.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataset

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[Get-AzDataFactoryDataset](./Get-AzDataFactoryDataset.md)

[Remove-AzDataFactoryDataset](./Remove-AzDataFactoryDataset.md)


