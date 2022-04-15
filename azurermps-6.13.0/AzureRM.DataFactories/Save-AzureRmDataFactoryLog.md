---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
Module Name: AzureRM.DataFactories
ms.assetid: 5490BB24-127E-4C21-B85F-B70D817B659A
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.datafactories/save-azurermdatafactorylog
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/Save-AzureRmDataFactoryLog.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/Save-AzureRmDataFactoryLog.md
ms.openlocfilehash: 41b147307d253271e24667bd61d827c245f4500a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142358381"
---
# Save-AzureRmDataFactoryLog

## SYNOPSIS
Mengunduh file log dari pemrosesan Azure HDInsight.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFactoryName (Default)
```
Save-AzureRmDataFactoryLog [-DataFactoryName] <String> [-Id] <String> [-DownloadLogs] [[-Output] <String>]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
Save-AzureRmDataFactoryLog [-DataFactory] <PSDataFactory> [-Id] <String> [-DownloadLogs] [[-Output] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Save-AzureRmDataFactoryLog** mengunduh file log yang terkait dengan pemrosesan Azure HDInsight proyek Babi atau Sarang atau untuk aktivitas kustom ke hard drive lokal Anda.
Anda terlebih dahulu menjalankan cmdlet Get-AzureRmDataFactoryRun untuk mendapatkan ID untuk aktivitas yang dijalankan untuk sepotong data, lalu gunakan ID tersebut untuk mengambil file log dari penyimpanan objek besar biner (BLOB) yang terkait dengan kluster HDInsight.
Jika Anda tidak menentukan parameter *DownloadLogs* , cmdlet hanya mengembalikan lokasi file log.
Jika Anda menentukan *DownloadLogs* tanpa menentukan direktori output (Parameter *output* ), file log diunduh ke folder Dokumen default.
Jika Anda menentukan *DownloadLogs* bersama dengan folder output (*Output*), file log diunduh ke folder tertentu.

## EXAMPLES

### Contoh 1: Menyimpan file log ke folder tertentu
```
PS C:\>Save-AzureRmDataFactoryLog -ResourceGroupName "ADF" -DataFactoryName "LogProcessingFactory" -Id "841b77c9-d56c-48d1-99a3-8c16c3e77d39" -DownloadLogs -Output "C:\Test"
```

Perintah ini menyimpan file log untuk aktivitas yang dijalankan dengan ID 841b77c9-d56c-48d1-99a3-8c16c3e77d39 tempat aktivitas tersebut termasuk dalam pipeline di pabrik data bernama LogProcessingFactory dalam grup sumber daya bernama ADF.
File log disimpan ke folder C:\Test.

### Contoh 2: Menyimpan file log ke folder Dokumen default
```
PS C:\>Save-AzureRmDataFactoryLog -ResourceGroupName "ADF" -DataFactoryName "LogProcessingFactory" -Id "841b77c9-d56c-48d1-99a3-8c16c3e77d39" -DownloadLogs
```

Perintah ini menyimpan file log ke folder Dokumen (default).

### Contoh 3: Mendapatkan lokasi file log
```
PS C:\>Save-AzureRmDataFactoryLog -ResourceGroupName "ADF" -DataFactoryName "LogProcessingFactory" -Id "841b77c9-d56c-48d1-99a3-8c16c3e77d39"
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DownloadLogs
Menunjukkan bahwa cmdlet ini mengunduh file log ke komputer lokal Anda.
Jika folder *Ouptut* tidak ditentukan, file disimpan ke folder Dokumen di bawah subfolder.

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
Menentukan ID aktivitas yang dijalankan untuk pemisah data.
Gunakan cmdlet Get-AzureRmDataFactoryRun untuk mendapatkan ID.

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
Cmdlet ini membuat pabrik data yang termasuk dalam grup yang ditentukan parameter ini.

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

### Microsoft.Azure.Commands.DataFactories.Models.PSRunLogInfo

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[Get-AzureRmDataFactoryRun](./Get-AzureRmDataFactoryRun.md)

[Get-AzureRmDataFactoryPipeline](./Get-AzureRmDataFactoryPipeline.md)

[AzureRmDataFactoryPipeline baru](./New-AzureRmDataFactoryPipeline.md)

[Hapus-AzureRmDataFactoryPipeline](./Remove-AzureRmDataFactoryPipeline.md)

[Set-AzureRmDataFactoryPipelineActivePeriod](./Set-AzureRmDataFactoryPipelineActivePeriod.md)

[Suspend-AzureRmDataFactoryPipeline](./Suspend-AzureRmDataFactoryPipeline.md)


