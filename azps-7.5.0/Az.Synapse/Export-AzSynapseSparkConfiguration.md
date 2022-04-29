---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/export-azsynapsesparkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseSparkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseSparkConfiguration.md
ms.openlocfilehash: 156d6a955a6cb3615d47847b9e0c430e5f0eaba3
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144228011"
---
# Export-AzSynapseSparkConfiguration

## SYNOPSIS
Mengekspor konfigurasi spark Synapse ke folder output.

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
Cmdlet **Export-AzSynapseSparkConfiguration mengekspor** konfigurasi Synapse spark ke file configuration(.json).
Nama konfigurasi spark menjadi nama file yang diekspor. Jika Anda menentukan nama konfigurasi spark, cmdlet mengekspor konfigurasi spark tersebut. Jika Anda tidak menentukan nama, cmdlet mengekspor semua konfigurasi spark di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Export-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -OutputFolder "C:\SparkConfiguration"
```

Mengekspor semua konfigurasi spark di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration".

### Contoh 2
```powershell
Export-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContoSparkConfiguration -OutputFolder "C:\SparkConfiguration"
```

Mengekspor konfigurasi spark tunggal bernama ContoSparkConfiguration di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration".

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Export-AzSynapseSparkConfiguration -Name ContoSparkConfiguration -OutputFolder "C:\SparkConfiguration"
```

Mengekspor konfigurasi spark tunggal bernama ContoSparkConfiguration di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration" melalui alur.

### Contoh 4
```powershell
$sparkConfiguration = Get-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContoSparkConfiguration
$sparkConfiguration | Export-AzSynapseSparkConfiguration -OutputFolder "C:\SparkConfiguration"
```

Mengekspor konfigurasi spark tunggal yang disebut ContoSparkConfiguration di ruang kerja ContosoWorkspace ke folder "C:\SparkConfiguration" melalui alur.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -Name
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
Folder tempat konfigurasi spark harus ditempatkan.

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

### -WorkspaceName
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
objek input ruang kerja, biasanya melewati alur.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS
