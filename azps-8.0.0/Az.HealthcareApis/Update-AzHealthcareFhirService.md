---
external help file: ''
Module Name: Az.HealthcareApis
online version: https://docs.microsoft.com/powershell/module/az.healthcareapis/update-azhealthcarefhirservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Update-AzHealthcareFhirService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Update-AzHealthcareFhirService.md
ms.openlocfilehash: aa9cf6cb103d4d9e3f34eb9c1973bce379bc9597
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146602896"
---
# Update-AzHealthcareFhirService

## SYNOPSIS
Detail Layanan Patch FHIR.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzHealthcareFhirService -Name <String> -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String>] [-IdentityType <ServiceManagedIdentityType>]
 [-IdentityUserAssignedIdentity <Hashtable>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzHealthcareFhirService -InputObject <IHealthcareApisIdentity>
 [-IdentityType <ServiceManagedIdentityType>] [-IdentityUserAssignedIdentity <Hashtable>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Detail Layanan Patch FHIR.

## EXAMPLES

### Contoh 1: Detail Layanan Patch FHIR.
```powershell
PS C:\> Update-AzHealthcareFhirService -Name azpsfhirservice -ResourceGroupName azps_test_group -WorkspaceName azpshcws -Tag @{"123"="abc"}

Location Name                     Kind    ResourceGroupName
-------- ----                     ----    -----------------
eastus2  azpshcws/azpsfhirservice fhir-R4 azps_test_group
```

Detail Layanan Patch FHIR.

### Contoh 2: Detail Layanan Patch FHIR.
```powershell
PS C:\>  Get-AzHealthcareFhirService -Name azpsfhirservice -ResourceGroupName azps_test_group -WorkspaceName azpshcws | Update-AzHealthcareFhirService -Tag @{"123"="abc"}

Location Name                     Kind    ResourceGroupName
-------- ----                     ----    -----------------
eastus2  azpshcws/azpsfhirservice fhir-R4 azps_test_group
```

Detail Layanan Patch FHIR.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -IdentityType
Jenis identitas yang ditentukan, saat ini SystemAssigned dan None diperbolehkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Support.ServiceManagedIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityUserAssignedIdentity
Kumpulan identitas yang ditetapkan pengguna yang terkait dengan sumber daya.
Kunci kamus userAssignedIdentities akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}.
Nilai kamus dapat berupa objek kosong ({}) dalam permintaan.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

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
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya Layanan FHIR.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: FhirServiceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya yang berisi instans layanan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama sumber daya ruang kerja.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.IHealthcareApisIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api20211101.IFhirService

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

