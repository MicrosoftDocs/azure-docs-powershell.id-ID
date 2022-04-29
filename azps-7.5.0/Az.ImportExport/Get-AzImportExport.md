---
external help file: ''
Module Name: Az.ImportExport
online version: https://docs.microsoft.com/powershell/module/az.importexport/get-azimportexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Get-AzImportExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Get-AzImportExport.md
ms.openlocfilehash: 53a1be49d7dd1da309115dfd483f5c58b50ef03e
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144244167"
---
# Get-AzImportExport

## SYNOPSIS
Mendapatkan informasi tentang pekerjaan yang sudah ada.

## SYNTAX

### Daftar (Default)
```
Get-AzImportExport [-SubscriptionId <String[]>] [-Filter <String>] [-Top <Int32>] [-AcceptLanguage <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzImportExport -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-AcceptLanguage <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzImportExport -InputObject <IImportExportIdentity> [-AcceptLanguage <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzImportExport -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Filter <String>] [-Top <Int32>]
 [-AcceptLanguage <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang pekerjaan yang sudah ada.

## EXAMPLES

### Contoh 1: Mendapatkan pekerjaan ImportExport dengan konteks default
```powershell
Get-AzImportExport
```

```output
Location Name     Type
-------- ----     ----
East US  test-job Microsoft.ImportExport/jobs
```

Cmdlet ini mendapatkan pekerjaan ImportExport dengan konteks default.

### Contoh 2: Mendapatkan pekerjaan ImportExport menurut grup sumber daya dan nama pekerjaan
```powershell
Get-AzImportExport -Name test-job -ResourceGroupName ImportTestRG
```

```output
Location Name     Type
-------- ----     ----
East US  test-job Microsoft.ImportExport/jobs
```

Cmdlet ini mendapatkan pekerjaan ImportExport menurut grup sumber daya dan nama pekerjaan.

### Contoh 3: Mencantumkan semua pekerjaan ImportExport dalam grup sumber daya tertentu
```powershell
Get-AzImportExport -ResourceGroupName ImportTestRG
```

```output
Location Name     Type
-------- ----     ----
East US  test-job Microsoft.ImportExport/jobs
```

Cmdlet ini mencantumkan semua pekerjaan ImportExport dalam grup sumber daya tertentu.

### Contoh 4: Mendapatkan pekerjaan ImportExport berdasarkan identitas
```powershell
$Id = "/subscriptions/<SubscriptionId>/resourceGroups/ImportTestRG/providers/Microsoft.ImportExport/jobs/test-job"
Get-AzImportExport -InputObject $Id
```

```output
Location Name     Type
-------- ----     ----
East US  test-job Microsoft.ImportExport/jobs
```

Cmdlet ini mencantumkan mendapatkan pekerjaan ImportExport menurut identitas.

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

### -Filter
Dapat digunakan untuk membatasi hasil untuk kondisi tertentu.

```yaml
Type: System.String
Parameter Sets: List, List1
Aliases:

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

### -Name
Nama pekerjaan impor/ekspor.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: JobName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya secara unik mengidentifikasi grup sumber daya dalam langganan pengguna.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan untuk pengguna Azure.

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atas
Nilai bilangan bulat yang menentukan berapa banyak pekerjaan yang paling banyak harus dikembalikan.
Nilai tidak boleh melebihi 100.

```yaml
Type: System.Int32
Parameter Sets: List, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.IImportExportIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.Api20161101.IJobResponse

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

