---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsesparkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkConfiguration.md
ms.openlocfilehash: 415a166f80f0ad00b3357f877174c95e90c59e00
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144703362"
---
# Get-AzSynapseSparkConfiguration

## SYNOPSIS
Mendapatkan informasi tentang konfigurasi spark di ruang kerja.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsesparkconfiguration) untuk informasi terbaru.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseSparkConfiguration -WorkspaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseSparkConfiguration -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseSparkConfiguration** mendapatkan informasi tentang konfigurasi spark di ruang kerja. Jika Anda menentukan nama konfigurasi spark, cmdlet mendapatkan informasi tentang konfigurasi spark tersebut. Jika Anda tidak menentukan nama, cmdlet mendapatkan informasi tentang semua konfigurasi spark di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua konfigurasi spark di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContosoSparkConfiguration
```

Mendapatkan konfigurasi spark tunggal yang disebut ContosoSparkConfiguration di ruang kerja ContosoWorkspace.

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseSparkConfiguration -Name ContosoSparkConfiguration
```

Mendapatkan konfigurasi spark tunggal yang disebut ContosoSparkConfiguration di ruang kerja ContosoWorkspace melalui alur.

## PARAMETERS

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

### -Name
Nama Konfigurasi Spark.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SparkConfigurationName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: GetByName
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
Parameter Sets: GetByObject
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

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource

## NOTES

## RELATED LINKS
