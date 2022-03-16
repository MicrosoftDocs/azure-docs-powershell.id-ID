---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceInitDefinitionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceInitDefinitionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceInitDefinitionObject.md
ms.openlocfilehash: fb22c88d680cea9c59ec15577ecdb1431ed6c954
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140209792"
---
# New-AzContainerInstanceInitDefinitionObject

## SYNOPSIS
Membuat objek dalam memori untuk InitContainerDefinition

## SYNTAX

```
New-AzContainerInstanceInitDefinitionObject -Name <String> [-Command <String[]>]
 [-EnvironmentVariable <IEnvironmentVariable[]>] [-Image <String>] [-VolumeMount <IVolumeMount[]>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk InitContainerDefinition

## EXAMPLES

### Contoh 1: Setel definisi wadah init
```powershell
New-AzContainerInstanceInitDefinitionObject -Name "initDefinition" -Command "/bin/sh -c myscript.sh"
```

```output
Name
----
initDefinition
```

Perintah ini menyiapkan definisi wadah init dengan perintah `/bin/sh -c myscript.sh`

## PARAMETERS

### -Command
Perintah untuk dijalankan dalam wadah init dalam bentuk exec.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentVariable
Variabel lingkungan yang diatur dalam wadah init.
Untuk membuat, lihat bagian CATATAN untuk properti ENVIRONMENTVARIABLE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IEnvironmentVariable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Image
Gambar wadah init.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama untuk wadah init.

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

### -VolumeMount
Volume terpasang yang tersedia pada wadah init.
Untuk membuat, lihat bagian CATATAN untuk properti VOLUMEMOUNT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IVolumeMount[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.InitContainerDefinition

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENVIRONMENTVARIABLE <IEnvironmentVariable[]>: Variabel lingkungan untuk diatur dalam wadah init.
  - `Name <String>`: Nama variabel lingkungan.
  - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
  - `[Value <String>]`: Nilai variabel lingkungan.

VOLUMEMOUNT <IVolumeMount[]>: Volume terpasang yang tersedia untuk wadah init.
  - `MountPath <String>`: Jalur di dalam wadah tempat volume harus terpasang. Tidak boleh berisi titik dua (:).
  - `Name <String>`: Nama volume yang naik.
  - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah volume naik merupakan baca-saja.

## RELATED LINKS

