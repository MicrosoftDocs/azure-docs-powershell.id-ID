---
external help file: ''
Module Name: Az.HealthcareApis
online version: https://docs.microsoft.com/powershell/module/az.healthcareapis/get-azhealthcaredicomservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Get-AzHealthcareDicomService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Get-AzHealthcareDicomService.md
ms.openlocfilehash: 0453dea5dd5d96413432b91d8f557e2e22c1bb64
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146605884"
---
# Get-AzHealthcareDicomService

## SYNOPSIS
Mendapatkan properti dari Layanan DICOM yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzHealthcareDicomService -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzHealthcareDicomService -Name <String> -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzHealthcareDicomService -InputObject <IHealthcareApisIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti dari Layanan DICOM yang ditentukan.

## EXAMPLES

### Contoh 1: Mencantumkan properti ruang kerja yang ditentukan.
```powershell
PS C:\> Get-AzHealthcareDicomService -ResourceGroupName azps_test_group -WorkspaceName azpshcws

Location Name               ResourceGroupName
-------- ----               -----------------
eastus2  azpshcws/azpsdicom azps_test_group
```

Mencantumkan properti ruang kerja yang ditentukan.

### Contoh 2: Mendapatkan properti dari Layanan DICOM yang ditentukan.
```powershell
PS C:\> Get-AzHealthcareDicomService -Name azpsdicom -ResourceGroupName azps_test_group -WorkspaceName azpshcws

Location Name               ResourceGroupName
-------- ----               -----------------
eastus2  azpshcws/azpsdicom azps_test_group
```

Mendapatkan properti dari Layanan DICOM yang ditentukan.

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
Nama sumber daya Layanan DICOM.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DicomServiceName

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
Parameter Sets: Get, List
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
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama sumber daya ruang kerja.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.IHealthcareApisIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api20211101.IDicomService

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IHealthcareApisIdentity>`: Parameter Identitas
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

