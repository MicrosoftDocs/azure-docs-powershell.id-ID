---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/export-azsynapsesparkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseSparkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseSparkConfiguration.md
ms.openlocfilehash: 8bd1985281b268639e9c329a1ddd65eebe4a8a75
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142691236"
---
# Export-AzSynapseSparkConfiguration

## SYNOPSIS
Mengekspor konfigurasi spark Synapse ke folder output.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/export-azsynapsesparkconfiguration) untuk informasi terbaru.

## SYNTAX

### ExportByName (Default)
```
Export-AzSynapseSparkConfiguration -WorkspaceName <String> [-Name <String>] -OutputFolder <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExportByObject
```
Export-AzSynapseSparkConfiguration -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 -OutputFolder <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExportByInputObject
```
Export-AzSynapseSparkConfiguration -InputObject <PSSparkConfigurationResource> -OutputFolder <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Export-AzSynapseSparkConfiguration mengekspor** konfigurasi spark Synapse ke file configuration(.json).
Nama konfigurasi percikan menjadi nama file yang diekspor. Jika Anda menentukan nama konfigurasi percikan api, cmdlet akan mengekspor konfigurasi percikan tersebut. Jika Anda tidak menentukan nama, cmdlet mengekspor semua konfigurasi percikan dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Export-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -OutputFolder "C:\SparkConfiguration"
```

Mengekspor semua konfigurasi percikan api di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration".

### Contoh 2
```powershell
PS C:\> Export-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContoSparkConfiguration -OutputFolder "C:\SparkConfiguration"
```

Mengekspor konfigurasi percikan api tunggal bernama ContoSparkConfiguration di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration".

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Export-AzSynapseSparkConfiguration -Name ContoSparkConfiguration -OutputFolder "C:\SparkConfiguration"
```

Mengekspor konfigurasi percikan api tunggal bernama ContoSparkConfiguration di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration" melalui pipeline.

### Contoh 4
```powershell
PS C:\> $sparkConfiguration = Get-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContoSparkConfiguration
PS C:\> $sparkConfiguration | Export-AzSynapseSparkConfiguration -OutputFolder "C:\SparkConfiguration"
```

Mengekspor konfigurasi spark tunggal yang disebut ContoSparkConfiguration di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration" melalui pipeline.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -InputObject
Objek konfigurasi Spark.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource
Parameter Sets: ExportByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Konfigurasi Spark.

```yaml
Type: System.String
Parameter Sets: ExportByName, ExportByObject
Aliases: SparkConfigurationName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFolder
Folder tempat konfigurasi percikan api harus ditempatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: ExportByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: ExportByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS
