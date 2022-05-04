---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceInitDefinitionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceInitDefinitionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceInitDefinitionObject.md
ms.openlocfilehash: 1bf30f5cc75266958c455cce921ca90fde42cbb2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144632852"
---
# New-AzContainerInstanceInitDefinitionObject

## SYNOPSIS
Membuat objek dalam memori untuk InitContainerDefinition

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainerinstanceinitdefinitionobject) untuk informasi terbaru.

## SYNTAX

```
New-AzContainerInstanceInitDefinitionObject -Name <String> [-Command <String[]>]
 [-EnvironmentVariable <IEnvironmentVariable[]>] [-Image <String>] [-VolumeMount <IVolumeMount[]>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk InitContainerDefinition

## EXAMPLES

### Contoh 1: Menyiapkan definisi kontainer init
```powershell
New-AzContainerInstanceInitDefinitionObject -Name "initDefinition" -Command "/bin/sh -c myscript.sh"
```

```output
Name
----
initDefinition
```

Perintah ini menyiapkan definisi kontainer init dengan perintah `/bin/sh -c myscript.sh`

## PARAMETERS

### -Perintah
Perintah untuk menjalankan dalam kontainer init dalam bentuk eksekusi.

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
Variabel lingkungan yang akan diatur dalam kontainer init.
Untuk membuat, lihat bagian CATATAN untuk properti ENVIRONMENTVARIABLE dan buat tabel hash.

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

### -Gambar
Gambar kontainer init.

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

### -Name
Nama untuk kontainer init.

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
Mount volume yang tersedia untuk kontainer init.
Untuk membuat, lihat bagian CATATAN untuk properti VOLUMEMOUNT dan buat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.InitContainerDefinition

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENVIRONMENTVARIABLE <IEnvironmentVariable[]>: Variabel lingkungan yang akan diatur dalam kontainer init.
  - `Name <String>`: Nama variabel lingkungan.
  - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
  - `[Value <String>]`: Nilai variabel lingkungan.

VOLUMEMOUNT <IVolumeMount[]>: Volume dipasang tersedia untuk kontainer init.
  - `MountPath <String>`: Jalur dalam kontainer tempat volume harus dipasang. Tidak boleh ada titik dua (:).
  - `Name <String>`: Nama pemasangan volume.
  - `[ReadOnly <Boolean?>]`: Bendera yang menunjukkan apakah pemasangan volume bersifat baca-saja.

## RELATED LINKS

