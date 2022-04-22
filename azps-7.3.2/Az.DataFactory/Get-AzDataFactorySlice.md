---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: C102232A-C9C8-4CEE-8535-7C7A70057B06
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-azdatafactoryslice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactorySlice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactorySlice.md
ms.openlocfilehash: f1952f348983373daf3fadde3d5e5f12a9e78869
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142891846"
---
# Get-AzDataFactorySlice

## SYNOPSIS
Mendapatkan irisan data untuk kumpulan data dalam Azure Data Factory.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datafactory/get-azdatafactoryslice) untuk informasi terbaru.

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
Cmdlet **Get-AzDataFactorySlice** mendapatkan irisan data untuk kumpulan data di Azure Data Factory.
Tentukan waktu mulai dan waktu akhir untuk menentukan rentang irisan data untuk ditampilkan.
Status pemangkasan data adalah salah satu nilai berikut ini: 
- PendingExecution.
Pemrosesan data belum dimulai. 
- InProgress.
Pemrosesan data sedang berlangsung. 
- Siap.
Pemrosesan data selesai.
Irisan data siap untuk irisan dependen untuk mengkonsumsinya. 
- Gagal.
Pelarian yang menghasilkan iringan gagal. 
- Melewatkan.
Pabrik Data melewatkan pemrosesan potong. 
- Pengulangan.
Pabrik Data mencoba kembali proses yang menghasilkan ikatan. 
- Waktu Habis. Pemrosesan data telah kehabisan waktu. 
- TertundaValidasi.
Pemisah data menunggu validasi sebelum diproses. 
- Coba lagi Validasi.
Pabrik Data mencoba kembali validasi dari potong. 
- Validasi Gagal.
Validasi dari iringan gagal.
Untuk setiap irisan, Anda dapat melihat informasi selengkapnya tentang lari yang menghasilkan irisan menggunakan cmdlet Get-AzDataFactoryRun.

## EXAMPLES

### Contoh 1: Dapatkan irisan data untuk kumpulan data
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

Perintah ini mendapatkan semua irisan data untuk kumpulan data bernama WikiAggregatedData di pabrik data bernama WikiADF.
Perintah mendapatkan irisan yang dihasilkan setelah waktu yang ditentukan parameter StartDateTime.
Kode contoh berikut mengatur ketersediaan untuk kumpulan data ini setiap jam dalam file JavaScript Object Notation (JSON).
ketersediaan: { period: "Hour", periodMultiplier: 1 } Beberapa hasil siap dan lainnya adalah PendingExecution.
Irisan siap telah dijalankan.
Irisan tertunda menunggu untuk dijalankan pada akhir setiap jam dalam interval yang ditentukan cmdlet Set-AzDataFactoryPipelineActivePeriod.
Dalam contoh ini, baik periode mulai maupun akhir untuk pipeline dan iringan memiliki nilai satu hari (24 jam).

### Contoh 2

Mendapatkan irisan data untuk kumpulan data dalam Azure Data Factory. (autogenerasi)

```powershell <!-- Aladdin Generated Example --> 
Get-AzDataFactorySlice -DataFactoryName 'WikiADF' -DatasetName 'DAWikiAggregatedData' -EndDateTime 2014-05-22T16:00:00Z -ResourceGroupName 'ADF' -StartDateTime 2014-05-20T10:00:00Z
```

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini mendapatkan irisan yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Cmdlet ini mendapatkan irisan yang termasuk dalam pabrik data yang ditentukan parameter ini.

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
Menentukan nama kumpulan data tempat cmdlet ini mendapatkan irisan.

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

### -EndDateTime
Menentukan akhir periode waktu sebagai objek **DateTime** .
Cmdlet ini mendapatkan irisan yang dihasilkan sebelum waktu yang ditentukan parameter ini.
Untuk informasi selengkapnya tentang objek **DateTime**, ketik .`Get-Help Get-Date`
*EndDateTime* harus ditentukan dalam format ISO8601 seperti dalam contoh berikut: 2015-01-01Z 2015-01-01T00:00:00Z 2015-01-01-0101T00:00:00.000Z (UTC) 2015-01-01T00:00:00-08:00 (Waktu Standar Pasifik) Pendesain zona waktu default adalah UTC.

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
Cmdlet ini mendapatkan irisan yang termasuk dalam grup yang ditentukan parameter ini.

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
Menentukan awal periode waktu sebagai objek **DateTime** .
Cmdlet ini mendapatkan irisan yang dihasilkan setelah waktu yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataSlice

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[Set-AzDataFactorySliceStatus](./Set-AzDataFactorySliceStatus.md)

[Get-AzDataFactoryRun](./Get-AzDataFactoryRun.md)

[Set-AzDataFactoryPipelineActivePeriod](./Set-AzDataFactoryPipelineActivePeriod.md)


