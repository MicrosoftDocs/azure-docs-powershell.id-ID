---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceInitDefinitionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceInitDefinitionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceInitDefinitionObject.md
ms.openlocfilehash: 06883b7c346fb2c6a7ac305b3b9b9b9400373d9b
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136375432"
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
PS C:\> New-AzContainerInstanceInitDefinitionObject -Name "initDefinition" -Command "/bin/sh -c myscript.sh"

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IEnvironmentVariable[]
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
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IVolumeMount[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.InitContainerDefinition

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENVIRONMENTVARIABLE <IEnvironmentVariable[]>: Variabel lingkungan untuk diatur dalam wadah init.
  - `Name <String>`: Nama variabel lingkungan.
  - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
  - `[Value <String>]`: Nilai variabel lingkungan.

VOLUMEMOUNT <IVolumeMount[]>: Volume terpasang yang tersedia pada wadah init.
  - `MountPath <String>`: Jalur di dalam wadah tempat volume harus terpasang. Tidak boleh berisi titik dua (:).
  - `Name <String>`: Nama volume yang naik.
  - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah volume naik merupakan baca-saja.

## RELATED LINKS

