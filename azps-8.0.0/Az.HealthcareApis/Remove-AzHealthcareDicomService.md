---
external help file: ''
Module Name: Az.HealthcareApis
online version: https://docs.microsoft.com/powershell/module/az.healthcareapis/remove-azhealthcaredicomservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Remove-AzHealthcareDicomService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/Remove-AzHealthcareDicomService.md
ms.openlocfilehash: 3fa6580493579fdf142ee5237c05354166181e27
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145515223"
---
# Remove-AzHealthcareDicomService

## SYNOPSIS
Menghapus Layanan DICOM.

## SYNTAX

### Hapus (Default)
```
Remove-AzHealthcareDicomService -Name <String> -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzHealthcareDicomService -InputObject <IHealthcareApisIdentity> [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus Layanan DICOM.

## EXAMPLES

### Contoh 1: Hapus
```powershell
PS C:\> Remove-AzHealthcareDicomService -Name azpsdicom -ResourceGroupName azps_test_group -WorkspaceName azpshcws

```

Menghapus Layanan DICOM.

### Contoh 2: DeleteViaIdentity
```powershell
PS C:\> Get-AzHealthcareDicomService -Name azpsdicom -ResourceGroupName azps_test_group -WorkspaceName azpshcws | Remove-AzHealthcareDicomService

```

Menghapus Layanan DICOM.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.IHealthcareApisIdentity
Parameter Sets: DeleteViaIdentity
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
Parameter Sets: Delete
Aliases: DicomServiceName

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

### -PassThru
Mengembalikan true saat perintah berhasil

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
Parameter Sets: Delete
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
Parameter Sets: Delete
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
Parameter Sets: Delete
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

### System.Boolean

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

