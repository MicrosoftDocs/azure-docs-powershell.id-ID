---
external help file: ''
Module Name: Az.ImportExport
online version: https://docs.microsoft.com/powershell/module/az.importexport/get-azimportexportlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Get-AzImportExportLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Get-AzImportExportLocation.md
ms.openlocfilehash: c05f95636830a6a98cc0b0a022a0efe61f88e318
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142178327"
---
# Get-AzImportExportLocation

## SYNOPSIS
Mengembalikan detail tentang lokasi tempat Anda dapat mengirimkan disk yang terkait dengan pekerjaan impor atau ekspor.
Lokasi adalah kawasan Azure.

## SYNTAX

### Daftar (Default)
```
Get-AzImportExportLocation [-AcceptLanguage <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
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
Mengembalikan detail tentang lokasi tempat Anda dapat mengirimkan disk yang terkait dengan pekerjaan impor atau ekspor.
Lokasi adalah kawasan Azure.

## EXAMPLES

### Contoh 1: Dapatkan semua detail lokasi kawasan Azure dengan konteks default
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

Cmdlet ini mendapatkan semua detail lokasi kawasan Azure dengan konteks default.

### Contoh 2: Dapatkan detail lokasi kawasan Azure menurut nama lokasi
```powershell
Get-AzImportExportLocation -Name eastus
```

```output
Name    Type
----    ----
East US Microsoft.ImportExport/locations
```

Cmdlet ini mendapatkan detail lokasi kawasan Azure menurut nama lokasi.

### Contoh 3: Dapatkan detail lokasi kawasan Azure menurut identitas
```powershell
$Id = "/providers/Microsoft.ImportExport/locations/eastus"
Get-AzImportExportLocation -InputObject $Id
```

```output
Name    Type
----    ----
East US Microsoft.ImportExport/locations
```

Daftar cmdlet ini mendapatkan detail lokasi kawasan Azure menurut identitas.

## PARAMETERS

### -AcceptLanguage
Menentukan bahasa pilihan untuk respons.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Nama
Nama lokasi.
Misalnya, AS Barat atau westus.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.IImportExportIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.Api20161101.ILocation

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IImportExportIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobName <String>]`: Nama pekerjaan impor/ekspor.
  - `[LocationName <String>]`: Nama lokasi. Misalnya, AS Barat atau westus.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya mengidentifikasi grup sumber daya dalam langganan pengguna secara unik.
  - `[SubscriptionId <String>]`: ID langganan untuk pengguna Azure.

## RELATED LINKS

