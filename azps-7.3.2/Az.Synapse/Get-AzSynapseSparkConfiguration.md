---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsesparkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkConfiguration.md
ms.openlocfilehash: 475cc6978154c8ddb4481d5b0e1fb39621a5cc72
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139998112"
---
# Get-AzSynapseSparkConfiguration

## SYNOPSIS
Mendapatkan informasi tentang konfigurasi grafik api di ruang kerja.

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
Cmdlet **Get-AzSynapseSparkConfiguration** mendapatkan informasi tentang konfigurasi grafik api di dalam ruang kerja. Jika Anda menentukan nama konfigurasi grafik api, cmdlet mendapatkan informasi tentang konfigurasi grafik api tersebut. Jika Anda tidak menentukan nama, cmdlet mendapatkan informasi tentang semua konfigurasi grafik api di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua konfigurasi grafik api di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContosoSparkConfiguration
```

Mendapatkan konfigurasi grafik api tunggal yang disebut ContosoSparkConfiguration di ruang kerja ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseSparkConfiguration -Name ContosoSparkConfiguration
```

Mendapatkan konfigurasi grafik api tunggal yang disebut ContosoSparkConfiguration di ruang kerja ContosoWorkspace melalui pipeline.

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

### -Nama
Nama Konfigurasi Grafik Api.

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
objek input ruang kerja, biasanya melewati saluran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource

## CATATAN

## RELATED LINKS
