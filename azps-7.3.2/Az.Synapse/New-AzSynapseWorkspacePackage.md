---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapseworkspacepackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseWorkspacePackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseWorkspacePackage.md
ms.openlocfilehash: 09831edca27163cdd24200becd0057234ff646c5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143069291"
---
# New-AzSynapseWorkspacePackage

## SYNOPSIS
Mengunggah file paket ruang kerja lokal ke ruang kerja Azure Synapse.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/new-azsynapseworkspacepackage) untuk informasi terbaru.

## SYNTAX

### CreateByNameParameterSet (Default)
```
New-AzSynapseWorkspacePackage -WorkspaceName <String> -Package <String> [-ConcurrentTaskCount <Int32>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateByObjectParameterSet
```
New-AzSynapseWorkspacePackage -WorkspaceObject <PSSynapseWorkspace> -Package <String>
 [-ConcurrentTaskCount <Int32>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**New-AzSynapseWorkspacePackage** mengunggah file paket ruang kerja lokal ke ruang kerja Azure Synapse.

## EXAMPLES

### Contoh 1: Upload paket ruang kerja bernama
```powershell
PS C:\> New-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace -Package ".\ContosoPackage.whl"
```

Perintah ini mengunggah paket ruang kerja yang lokasinya ".\ContosoPackage.whl" ke ruang kerja Azure Synapse bernama ContosoWorkspace. Pacakge ruang kerja dapat berupa file roda atau stoples.

### Contoh 2: Upload semua paket ruang kerja di bawah folder saat ini
```powershell
PS C:\> Get-ChildItem -File | New-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace
```

Perintah ini menggunakan cmdlet inti Windows PowerShell Get-ChildItem untuk mendapatkan semua paket ruang kerja dalam folder saat ini dan di subfolder, lalu meneruskannya ke cmdlet saat ini menggunakan operator pipeline. Cmdlet New-AzSynapseWorkspacePackage mengunggah file paket ruang kerja ke ruang kerja Azure Synapse bernama ContosoWorkspace.

### Contoh 3: Upload paket ruang kerja bernama dan menambahkannya ke kumpulan Apache Spark
```powershell
PS C:\> $package = New-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace -Package ".\ContosoPackage.whl"
PS C:\> Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -PackageAction Add -Package $package
```

Perintah pertama ini mengunggah paket ruang kerja yang lokasinya adalah ".\ContosoPackage.whl" ke ruang kerja Azure Synapse bernama ContosoWorkspace. Pacakge ruang kerja dapat berupa file roda atau stoples. Kemudian perintah kedua menambahkan paket ke kumpulan Apache Spark tertentu bernama ContotoSparkPool.

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

### -ConcurrentTaskCount
Jumlah total tugas asinkron serentak.
Nilai defaultnya adalah 10.

```yaml
Type: System.Nullable`1[System.Int32]
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

### -Paket
Menentukan jalur file lokal untuk file yang akan diunggah sebagai paket ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
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
Parameter Sets: CreateByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage

## NOTES

## RELATED LINKS
