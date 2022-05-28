---
external help file: ''
Module Name: Az.HealthcareApis
online version: https://docs.microsoft.com/powershell/module/az.healthcareapis/new-azhealthcareapisservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/New-AzHealthcareApisService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HealthcareApis/help/New-AzHealthcareApisService.md
ms.openlocfilehash: fe9a304818e465fc95faf44346424080b98a1eb8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145530295"
---
# New-AzHealthcareApisService

## SYNOPSIS
Membuat atau memperbarui metadata instans layanan.

## SYNTAX

```
New-AzHealthcareApisService -Name <String> -ResourceGroupName <String> -CosmosOfferThroughput <Int32>
 -Kind <Kind> -Location <String> [-SubscriptionId <String>]
 [-AccessPolicyObjectId <IServiceAccessPolicyEntry[]>] [-AcrConfigurationLoginServer <String[]>]
 [-AcrConfigurationOciArtifact <IServiceOciArtifactEntry[]>] [-AllowCorsCredential] [-Audience <String>]
 [-Authority <String>] [-CorsHeader <String[]>] [-CorsMaxAge <Int32>] [-CorsMethod <String[]>]
 [-CorsOrigin <String[]>] [-CosmosKeyVaultKeyUri <String>] [-EnableSmartProxy] [-Etag <String>]
 [-ExportStorageAccountName <String>] [-IdentityType <ManagedServiceIdentityType>]
 [-PrivateEndpointConnection <IPrivateEndpointConnection[]>] [-PublicNetworkAccess <PublicNetworkAccess>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui metadata instans layanan.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui metadata instans layanan.
```powershell
PS C:\> New-AzHealthcareApisService -ResourceGroupName azps_test_group -Name azpsapiservice -Kind 'fhir' -Location eastus2 -CosmosOfferThroughput 400

Location Name           Kind ResourceGroupName
-------- ----           ---- -----------------
eastus2  azpsapiservice fhir azps_test_group
```

Membuat atau memperbarui metadata instans layanan.

## PARAMETERS

### -AccessPolicyObjectId
Kebijakan akses instans layanan.
Untuk membuat, lihat bagian CATATAN untuk properti ACCESSPOLICYOBJECTID dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api20211101.IServiceAccessPolicyEntry[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AcrConfigurationLoginServer
Daftar server login ACR.

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

### -AcrConfigurationOciArtifact
Daftar artefak Open Container Initiative (OCI).
Untuk membuat, lihat bagian CATATAN untuk properti ACRCONFIGURATIONOCIARTIFACT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api20211101.IServiceOciArtifactEntry[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowCorsCredential
Jika kredensial diizinkan melalui CORS.

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

### -Audiens
Url audiens untuk layanan

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

### -Otoritas
Url otoritas untuk layanan

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

### -CorsHeader
Header yang akan diizinkan melalui CORS.

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

### -CorsMaxAge
Usia maksimal yang diizinkan melalui CORS.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CorsMethod
Metode yang akan diizinkan melalui CORS.

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

### -CorsOrigin
Asal-usul yang akan diizinkan melalui CORS.

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

### -CosmosKeyVaultKeyUri
URI kunci yang dikelola pelanggan untuk database cadangan.

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

### -CosmosOfferThroughput
Throughput yang disediakan untuk database cadangan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
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

### -EnableSmartProxy
Jika proksi SMART di FHIR diaktifkan

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

### -Etag
Etag yang terkait dengan sumber daya, digunakan untuk konkurensi optimis saat mengeditnya.

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

### -ExportStorageAccountName
Nama akun penyimpanan ekspor default.

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

### -IdentityType
Jenis identitas yang ditentukan, saat ini SystemAssigned dan None diperbolehkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Support.ManagedServiceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kind
Jenis layanan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Support.Kind
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

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

### -Name
Nama instans layanan.

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

### -PrivateEndpointConnection
Daftar koneksi titik akhir privat yang disiapkan untuk sumber daya ini.
Untuk membuat, lihat bagian CATATAN untuk properti PRIVATEENDPOINTCONNECTION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api10.IPrivateEndpointConnection[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccess
Izin kontrol untuk lalu lintas sarana data yang berasal dari jaringan publik saat titik akhir privat diaktifkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Support.PublicNetworkAccess
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.HealthcareApis.Models.Api20211101.IServicesDescription

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ACCESSPOLICYOBJECTID <IServiceAccessPolicyEntry[]>: Kebijakan akses instans layanan.
  - `ObjectId <String>`: ID objek Azure AD (Pengguna atau Aplikasi) yang diizinkan mengakses layanan FHIR.

ACRCONFIGURATIONOCIARTIFACT <IServiceOciArtifactEntry[]>: Daftar artefak Open Container Initiative (OCI).
  - `[Digest <String>]`: Hash artefak.
  - `[ImageName <String>]`: Nama artefak.
  - `[LoginServer <String>]`: Server login Azure Container Registry.

PRIVATEENDPOINTCONNECTION <IPrivateEndpointConnection[]>: Daftar koneksi titik akhir privat yang disiapkan untuk sumber daya ini.
  - `[PrivateLinkServiceConnectionStateActionsRequired <String>]`: Pesan yang menunjukkan apakah perubahan pada penyedia layanan memerlukan pembaruan pada konsumen.
  - `[PrivateLinkServiceConnectionStateDescription <String>]`: Alasan persetujuan/penolakan koneksi.
  - `[PrivateLinkServiceConnectionStateStatus <PrivateEndpointServiceConnectionStatus?>]`: Menunjukkan apakah koneksi telah Disetujui/Ditolak/Dihapus oleh pemilik layanan.

## RELATED LINKS

