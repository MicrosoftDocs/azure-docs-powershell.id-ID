---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: 1D07222C-17D1-421C-8C9B-37043CBCF517
online version: https://docs.microsoft.com/en-us/powershell/module/az.datafactory/set-azdatafactoryslicestatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataFactory/DataFactoryV2/help/Set-AzDataFactorySliceStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataFactory/DataFactoryV2/help/Set-AzDataFactorySliceStatus.md
ms.openlocfilehash: 8b2c55a069463120b861f1ea928ac0163a4c37df
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132411523"
---
# Set-AzDataFactorySliceStatus

## SYNOPSIS
Mengatur status potongan untuk kumpulan data di Azure Data Factory.

## SINTAKS

### ByFactoryName (Default)
```
Set-AzDataFactorySliceStatus [[-EndDateTime] <DateTime>] [-Status] <String> [[-UpdateType] <String>]
 [-DataFactoryName] <String> [-DatasetName] <String> [-StartDateTime] <DateTime> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Set-AzDataFactorySliceStatus [[-EndDateTime] <DateTime>] [-Status] <String> [[-UpdateType] <String>]
 [-DataFactory] <PSDataFactory> [-DatasetName] <String> [-StartDateTime] <DateTime>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Set-AzDataFactorySgroupStatus** mengatur status potongan untuk kumpulan data di Azure Data Factory.

## CONTOH

### Contoh 1: Atur status dari semua potongan
```
PS C:\>Set-AzDataFactorySliceStatus -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -DatasetName "DAWikiAggregatedData" -StartDateTime 2014-05-21T16:00:00Z -EndDateTime 2014-05-21T20:00:00Z -Status "Waiting" -UpdateType "UpstreamInPipeline"
True
```

Perintah ini mengatur status semua potongan untuk kumpulan data yang bernama DAWikiAggregatedData menjadi Menunggu di pabrik data bernama WikiADF.
Parameter *UpdateType* memiliki nilai UpstreamInPipeline, sehingga perintah mengatur status setiap potongan untuk kumpulan data dan semua kumpulan data dependen.
Set data dependen digunakan sebagai set data input untuk aktivitas dalam saluran.
Perintah ini mengembalikan nilai $True.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory.**
Cmdlet ini mengubah status potongan yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mengubah status potongan yang termasuk dalam pabrik data yang ditentukan parameter ini.

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

### -DatasetName
Menentukan nama set data yang akan digunakan cmdlet ini untuk memodifikasi potongan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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

### -EndDateTime
Menentukan akhir periode waktu sebagai objek **DateTime.**
Kali ini adalah akhir dari potongan data.
Untuk informasi selengkapnya tentang **objek DateTime,** ketik `Get-Help Get-Date` .
*EndDateTime* harus ditentukan dalam format ISO8601 seperti dalam contoh berikut: 2015-01-01Z 2015-01-01T00:00:00Z 2015-01- 01T00:00:00.000Z (UTC) 2015-01-01T00:00:00-08:00 (Waktu Standar Pasifik) Penanda zona waktu default adalah UTC.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure.
Cmdlet ini mengubah status potongan yang termasuk dalam grup yang ditentukan parameter ini.

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

### -StartDateTime
Menentukan awal periode waktu sebagai objek **DateTime.**
Kali ini adalah awal dari potongan data.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status untuk ditetapkan ke potongan data.
Nilai yang dapat diterima untuk parameter ini adalah:
- Menunggu.
Potongan data menunggu validasi terhadap kebijakan validasi sebelum diproses. 
- Siap.
Pemrosesan data telah selesai dan potongan data siap.
- InProgress.
Pemrosesan data sedang berlangsung. 
- Gagal.
Pemrosesan data gagal.
- Terlewatkan.
Melewatkan pemrosesan potongan data.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Failed, InProgress, Ready, Skipped, Waiting

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateType
Menentukan tipe pembaruan ke potongan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Individual.
Mengatur status setiap potongan untuk kumpulan data dalam rentang waktu yang ditentukan. 
- UpstreamInPipeline.
Mengatur status setiap potongan untuk kumpulan data dan semua kumpulan data dependen, yang digunakan sebagai kumpulan data input untuk aktivitas dalam saluran.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Individual, UpstreamInPipeline

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUT

### System.Boolean

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, data, factories

## LINK TERKAIT

[Get-AzDataFactorySfactory](./Get-AzDataFactorySlice.md)


