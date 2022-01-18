---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: C102232A-C9C8-4CEE-8535-7C7A70057B06
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactoryslice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactorySlice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactorySlice.md
ms.openlocfilehash: 49de35283d65aa17f465e12dfbf4109f368cd015
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136172505"
---
# Get-AzDataFactorySlice

## SYNOPSIS
Mendapatkan potongan data untuk set data di Azure Data Factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzDataFactorySlice [[-EndDateTime] <DateTime>] [-DataFactoryName] <String> [-DatasetName] <String>
 [-StartDateTime] <DateTime> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzDataFactorySlice [[-EndDateTime] <DateTime>] [-DataFactory] <PSDataFactory> [-DatasetName] <String>
 [-StartDateTime] <DateTime> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataFactoryS cmdlet** mendapatkan potongan data untuk set data di Azure Data Factory.
Tentukan waktu mulai dan waktu akhir untuk menentukan rentang potongan data untuk dilihat.
Status potongan data adalah salah satu nilai berikut: 
- PendingExecution.
Pemrosesan data belum dimulai. 
- InProgress.
Pemrosesan data sedang berlangsung. 
- Siap.
Pemrosesan data selesai.
Potongan data siap untuk irisan dependen untuk menggunakannya. 
- Gagal.
Proses yang menghasilkan potongan gagal. 
- Lewati.
Data Factory melewatkan pemrosesan potongan. 
- Coba lagi.
Data Factoryretries the run yang menghasilkan potongan. 
- Waktu Habis. Pemrosesan data telah waktunya habis. 
- PendingValidation.
Potongan data menunggu validasi sebelum diproses. 
- Coba Validasi Lagi.
Data Factoryretries the validation of the slice. 
- Validasi Gagal.
Validasi potongan gagal.
Untuk setiap irisan, Anda bisa melihat informasi selengkapnya tentang proses yang menghasilkan potongan dengan menggunakan cmdlet Get-AzDataFactoryRun.

## EXAMPLES

### Contoh 1: Mendapatkan potongan data untuk set data
```powershell
PS C:\>Get-AzDataFactorySlice -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -DatasetName "DAWikiAggregatedData" -StartDateTime 2014-05-20T10:00:00Z
ResourceGroupName : ADF
DataFactoryName   : WikiADF
DatasetName         : DAWikiAggregatedData
Start             : 5/21/2014 1:00:00 AM
End               : 5/21/2014 2:00:00 AM
RetryCount        : 0
Status            : Ready

ResourceGroupName : ADF
DataFactoryName   : WikiADF
DatasetName         : DAWikiAggregatedData
Start             : 5/21/2014 2:00:00 AM
End               : 5/21/2014 3:00:00 AM
RetryCount        : 0
Status            : Ready

. . . 

ResourceGroupName : ADF
DataFactoryName   : WikiADF
DatasetName         : DAWikiAggregatedData
Start             : 5/21/2014 8:00:00 PM
End               : 5/21/2014 9:00:00 PM
RetryCount        : 0
Status            : PendingExecution

ResourceGroupName : ADF
DataFactoryName   : WikiADF
DatasetName         : DAWikiAggregatedData
Start             : 5/21/2014 9:00:00 PM
End               : 5/21/2014 10:00:00 PM
RetryCount        : 0
Status            : PendingExecution

. . .
```

Perintah ini mendapatkan semua potongan data untuk set data bernama WikiAggregatedData di pabrik data yang bernama WikiADF.
Perintah akan menghasilkan potongan setelah waktu yang ditentukan oleh parameter StartDateTime.
Contoh kode berikut mengatur ketersediaan untuk kumpulan data ini setiap jam dalam file JavaScript Object Notation (JSON).
ketersediaan: { periode: "Hour", periodMultiplier: 1 } Beberapa hasilnya Ready dan yang lain pendingexecution.
Potongan yang siap pun sudah berjalan.
Potongan yang tertunda menunggu untuk dijalankan pada akhir setiap jam dalam interval yang ditentukan cmdlet Set-AzDataFactoryPipelineActivePeriod.
Dalam contoh ini, periode mulai dan akhir untuk saluran dan potongan memiliki nilai satu hari (24 jam).

### Contoh 2

Mendapatkan potongan data untuk set data di Azure Data Factory. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example --> 
Get-AzDataFactorySlice -DataFactoryName 'WikiADF' -DatasetName 'DAWikiAggregatedData' -EndDateTime 2014-05-22T16:00:00Z -ResourceGroupName 'ADF' -StartDateTime 2014-05-20T10:00:00Z
```

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory.**
Cmdlet ini mendapatkan potongan yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mendapatkan potongan yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Menentukan nama set data tempat cmdlet ini mendapatkan potongan.

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
Cmdlet ini akan menghasilkan potongan sebelum waktu yang ditentukan parameter ini.
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
Cmdlet ini mendapatkan potongan yang termasuk dalam grup yang ditentukan parameter ini.

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
Cmdlet ini akan menghasilkan potongan setelah waktu yang ditentukan parameter ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataS azure

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, data, factories

## RELATED LINKS

[Set-AzDataFactorySstatus](./Set-AzDataFactorySliceStatus.md)

[Get-AzDataFactoryRun](./Get-AzDataFactoryRun.md)

[Set-AzDataFactoryPipelineActivePeriod](./Set-AzDataFactoryPipelineActivePeriod.md)


