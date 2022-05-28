---
external help file: ''
Module Name: Az.HealthcareApis
online version: https://docs.microsoft.com/powershell/module/az.healthcareapis/get-azhealthcareapisservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Get-AzHealthcareApisService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Get-AzHealthcareApisService.md
ms.openlocfilehash: 6012d20e3736015d1d82ec74aed25dcd64a71e39
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145515226"
---
# Get-AzHealthcareApisService

## SYNOPSIS
Mendapatkan metadata instans layanan.

## SYNTAX

### Daftar (Default)
```
Get-AzHealthcareApisService [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzHealthcareApisService -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzHealthcareApisService -InputObject <IHealthcareApisIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar1
```
Get-AzHealthcareApisService -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan metadata instans layanan.

## EXAMPLES

### Contoh 1: Mencantumkan metadata instans layanan.
```powershell
PS C:\>  Get-AzHealthcareApisService

Location Name           Kind ResourceGroupName
-------- ----           ---- -----------------
eastus2  azpsapiservice fhir azps_test_group
```

Mencantumkan metadata instans layanan.

### Contoh 2: Mencantumkan metadata instans layanan menurut grup sumber daya.
```powershell
PS C:\> Get-AzHealthcareApisService -ResourceGroupName azps_test_group

Location Name           Kind ResourceGroupName
-------- ----           ---- -----------------
eastus2  azpsapiservice fhir azps_test_group
```

Mencantumkan metadata instans layanan menurut grup sumber daya.

### Contoh 3: Mendapatkan metadata instans layanan.
```powershell
PS C:\> Get-AzHealthcareApisService -ResourceGroupName azps_test_group -Name azpsapiservice

Location Name           Kind ResourceGroupName
-------- ----           ---- -----------------
eastus2  azpsapiservice fhir azps_test_group
```

Mendapatkan metadata instans layanan.

## PARAMETERS

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
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.IHealthcareApisIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama instans layanan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi instans layanan.

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
Pengidentifikasi langganan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.IHealthcareApisIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api20211101.IServicesDescription

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IHealthcareApisIdentity>: Parameter Identitas
  - `[DicomServiceName <String>]`: Nama sumber daya Layanan DICOM.
  - `[FhirDestinationName <String>]`: Nama sumber daya tujuan FHIR Konektor IoT.
  - `[FhirServiceName <String>]`: Nama sumber daya Layanan FHIR.
  - `[GroupName <String>]`: Nama grup sumber daya tautan privat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[IotConnectorName <String>]`: Nama sumber daya Konektor IoT.
  - `[LocationName <String>]`: Lokasi operasi.
  - `[OperationResultId <String>]`: ID hasil operasi yang akan didapatkan.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat yang terkait dengan sumber daya Azure
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi instans layanan.
  - `[ResourceName <String>]`: Nama instans layanan.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan.
  - `[WorkspaceName <String>]`: Nama sumber daya ruang kerja.

## RELATED LINKS

