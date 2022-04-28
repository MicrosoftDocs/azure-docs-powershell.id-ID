---
external help file: ''
Module Name: Az.ImportExport
online version: https://docs.microsoft.com/powershell/module/az.importexport/get-azimportexportlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Get-AzImportExportLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Get-AzImportExportLocation.md
ms.openlocfilehash: c05f95636830a6a98cc0b0a022a0efe61f88e318
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144244142"
---
# Get-AzImportExportLocation

## SYNOPSIS
Mengembalikan detail tentang lokasi tempat Anda dapat mengirim disk yang terkait dengan pekerjaan impor atau ekspor.
Lokasi adalah wilayah Azure.

## SYNTAX

### Daftar (Default)
```
Get-AzImportExportLocation [-AcceptLanguage <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzImportExportLocation -Name <String> [-AcceptLanguage <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzImportExportLocation -InputObject <IImportExportIdentity> [-AcceptLanguage <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan detail tentang lokasi tempat Anda dapat mengirim disk yang terkait dengan pekerjaan impor atau ekspor.
Lokasi adalah wilayah Azure.

## EXAMPLES

### Contoh 1: Mendapatkan semua detail lokasi wilayah Azure dengan konteks default
```powershell
Get-AzImportExportLocation
```

```output
Name                 Type
----                 ----
Australia East       Microsoft.ImportExport/locations
Australia Southeast  Microsoft.ImportExport/locations
Brazil South         Microsoft.ImportExport/locations
Canada Central       Microsoft.ImportExport/locations
Canada East          Microsoft.ImportExport/locations
...
West Central US      Microsoft.ImportExport/locations
West Europe          Microsoft.ImportExport/locations
West India           Microsoft.ImportExport/locations
West US              Microsoft.ImportExport/locations
West US 2            Microsoft.ImportExport/locations
```

Cmdlet ini mendapatkan semua detail lokasi wilayah Azure dengan konteks default.

### Contoh 2: Mendapatkan detail lokasi wilayah Azure berdasarkan nama lokasi
```powershell
Get-AzImportExportLocation -Name eastus
```

```output
Name    Type
----    ----
East US Microsoft.ImportExport/locations
```

Cmdlet ini mendapatkan detail lokasi wilayah Azure berdasarkan nama lokasi.

### Contoh 3: Mendapatkan detail lokasi wilayah Azure berdasarkan identitas
```powershell
$Id = "/providers/Microsoft.ImportExport/locations/eastus"
Get-AzImportExportLocation -InputObject $Id
```

```output
Name    Type
----    ----
East US Microsoft.ImportExport/locations
```

Daftar cmdlet ini mendapatkan detail lokasi wilayah Azure berdasarkan identitas.

## PARAMETERS

### -AcceptLanguage
Menentukan bahasa yang dipilih untuk respons.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.IImportExportIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama lokasi.
Misalnya, US Barat atau westus.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: LocationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.IImportExportIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.Api20161101.ILocation

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IImportExportIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobName <String>]`: Nama pekerjaan impor/ekspor.
  - `[LocationName <String>]`: Nama lokasi. Misalnya, US Barat atau westus.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya secara unik mengidentifikasi grup sumber daya dalam langganan pengguna.
  - `[SubscriptionId <String>]`: ID langganan untuk pengguna Azure.

## RELATED LINKS

