---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: 5490BB24-127E-4C21-B85F-B70D817B659A
online version: https://docs.microsoft.com/powershell/module/az.datafactory/save-azdatafactorylog
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Save-AzDataFactoryLog.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Save-AzDataFactoryLog.md
ms.openlocfilehash: fb48507bf955e1dae7a5a480769f395079911118
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145785232"
---
# Save-AzDataFactoryLog

## SYNOPSIS
Mengunduh file log dari pemrosesan Azure HDInsight.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datafactory/save-azdatafactorylog) untuk informasi terbaru.

## SYNTAX

### ByFactoryName (Default)
```
Save-AzDataFactoryLog [-DataFactoryName] <String> [-Id] <String> [-DownloadLogs] [[-Output] <String>]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Save-AzDataFactoryLog [-DataFactory] <PSDataFactory> [-Id] <String> [-DownloadLogs] [[-Output] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Save-AzDataFactoryLog** mengunduh file log yang terkait dengan pemrosesan Azure HDInsight proyek Pig atau Apache Hive atau untuk aktivitas kustom ke hard drive lokal Anda.
Anda terlebih dahulu menjalankan cmdlet Get-AzDataFactoryRun untuk mendapatkan ID untuk aktivitas yang dijalankan untuk irisan data, lalu menggunakan ID tersebut untuk mengambil file log dari penyimpanan objek besar biner (BLOB) yang terkait dengan kluster HDInsight.
Jika Anda tidak menentukan parameter *DownloadLogs* , cmdlet hanya mengembalikan lokasi file log.
Jika Anda menentukan *DownloadLogs* tanpa menentukan direktori output (Parameter *output* ), file log diunduh ke folder Dokumen default.
Jika Anda menentukan *DownloadLogs* bersama dengan folder output (*Output*), file log diunduh ke folder yang ditentukan.

## EXAMPLES

### Contoh 1: Menyimpan file log ke folder tertentu
```powershell
Save-AzDataFactoryLog -ResourceGroupName "ADF" -DataFactoryName "LogProcessingFactory" -Id "841b77c9-d56c-48d1-99a3-8c16c3e77d39" -DownloadLogs -Output "C:\Test"
```

Perintah ini menyimpan file log untuk aktivitas yang dijalankan dengan ID 841b77c9-d56c-48d1-99a3-8c16c3e77d39 tempat aktivitas termasuk dalam alur di pabrik data bernama LogProcessingFactory dalam grup sumber daya bernama ADF.
File log disimpan ke folder C:\Test.

### Contoh 2: Menyimpan file log ke folder Dokumen default
```powershell
Save-AzDataFactoryLog -ResourceGroupName "ADF" -DataFactoryName "LogProcessingFactory" -Id "841b77c9-d56c-48d1-99a3-8c16c3e77d39" -DownloadLogs
```

Perintah ini menyimpan file log ke folder Dokumen (default).

### Contoh 3: Mendapatkan lokasi file log
```powershell
Save-AzDataFactoryLog -ResourceGroupName "ADF" -DataFactoryName "LogProcessingFactory" -Id "841b77c9-d56c-48d1-99a3-8c16c3e77d39"
```

Perintah ini mengembalikan lokasi file log.
Perhatikan bahwa *DownloadLogs* tidak ditentukan.

## PARAMETERS

### -DataFactory
Menentukan objek **PSDataFactory** .

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
Cmdlet ini mengunduh file log untuk pabrik data yang ditentukan parameter ini.

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

### -DownloadLogs
Menunjukkan bahwa cmdlet ini mengunduh file log ke komputer lokal Anda.
Jika folder *Output* tidak ditentukan, file disimpan ke folder Dokumen di bawah subfolder.

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

### -Id
Menentukan ID aktivitas yang dijalankan untuk iringan data.
Gunakan cmdlet Get-AzDataFactoryRun untuk mendapatkan ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Output
Menentukan folder output tempat file log yang diunduh disimpan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure.
Cmdlet ini membuat pabrik data milik grup yang ditentukan parameter ini.

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

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSRunLogInfo

## NOTES
* Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[Get-AzDataFactoryRun](./Get-AzDataFactoryRun.md)

[Get-AzDataFactoryPipeline](./Get-AzDataFactoryPipeline.md)

[New-AzDataFactoryPipeline](./New-AzDataFactoryPipeline.md)

[Remove-AzDataFactoryPipeline](./Remove-AzDataFactoryPipeline.md)

[Set-AzDataFactoryPipelineActivePeriod](./Set-AzDataFactoryPipelineActivePeriod.md)

[Suspensi-AzDataFactoryPipeline](./Suspend-AzDataFactoryPipeline.md)


