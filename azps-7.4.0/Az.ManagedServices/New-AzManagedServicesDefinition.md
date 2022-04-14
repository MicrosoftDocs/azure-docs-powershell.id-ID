---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/new-azmanagedservicesdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesDefinition.md
ms.openlocfilehash: a9a5b1e5b02a906f895536c5f64cea53426dc913
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142177627"
---
# New-AzManagedServicesDefinition

## SYNOPSIS
Membuat atau memperbarui definisi pendaftaran.

## SYNTAX

```
New-AzManagedServicesDefinition -Name <String> [-Scope <String>] [-Authorization <IAuthorization[]>]
 [-Description <String>] [-EligibleAuthorization <IEligibleAuthorization[]>] [-ManagedByTenantId <String>]
 [-PlanName <String>] [-PlanProduct <String>] [-PlanPublisher <String>] [-PlanVersion <String>]
 [-RegistrationDefinitionName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui definisi pendaftaran.

## EXAMPLES

### Contoh 1: Buat objek definisi pendaftaran Azure Lighthouse baru dengan otorisasi permanen
```powershell
$permantAuth = New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -DelegatedRoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx","xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

New-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -RegistrationDefinitionName "Test definition" -ManagedByTenantId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Authorization $permantAuth -Description "Test definition desc" -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" 
```

```output
Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationDefinitions
```

Membuat objek definisi pendaftaran Azure Lighthouse baru dengan otorisasi permanen.

### Contoh 2: Buat objek definisi pendaftaran Azure Lighthouse baru dengan otorisasi permanen dan memenuhi syarat
```powershell
$approver = New-AzManagedServicesEligibleApproverObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Approver group"

$eligibleAuth = New-AzManagedServicesEligibleAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -JustInTimeAccessPolicyManagedByTenantApprover $approver -JustInTimeAccessPolicyMultiFactorAuthProvider Azure -JustInTimeAccessPolicyMaximumActivationDuration 0:30

New-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx-RegistrationDefinitionName "Test definition" -ManagedByTenantId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Authorization $permantAuth -EligibleAuthorization $eligibleAuth -Description "Test definition desc" -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```

```output
Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxMicrosoft.ManagedServices/registrationDefinitions
```

Membuat objek definisi pendaftaran Azure Lighthouse baru dengan otorisasi permanen dan memenuhi syarat.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -Otorisasi
Kumpulan objek otorisasi yang menjelaskan akses Azure Active Directory pokok dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa yang dikelola.
Untuk membangun, lihat bagian CATATAN untuk properti OTORISASI dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IAuthorization[]
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

### -Deskripsi
Penjabaran dari definisi pendaftaran.

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

### -EligibleAuthorization
Kumpulan objek otorisasi yang memenuhi syarat yang menjelaskan akses tepat waktu Azure Active Directory pokok dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa yang dikelola.
Untuk membangun, lihat bagian CATATAN untuk properti ELIGIBLEAUTHORIZATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IEligibleAuthorization[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedByTenantId
Pengidentifikasi penyewa managedBy.

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
GUID definisi pendaftaran.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RegistrationDefinitionId

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

### -PlanName
Marketplace Azure nama rencana.

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

### -PlanProduct
Marketplace Azure kode produk.

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

### -PlanPublisher
MARKETPLACE AZURE ID penerbit.

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

### -PlanVersion
Marketplace Azure versi paket.

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

### -RegistrationDefinitionName
Nama definisi pendaftaran.

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

### -Lingkup
Lingkup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "subscriptions/" + (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationDefinition

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


OTORISASI <IAuthorization[]>: Kumpulan objek otorisasi yang menjelaskan akses Azure Active Directory prinsipal dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa yang dikelola.
  - `PrincipalId <String>`: Pengidentifikasi prinsipal Azure Active Directory.
  - `RoleDefinitionId <String>`: Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan dimiliki prinsipal Azure Active Directory pada lingkup yang diproyeksikan.
  - `[DelegatedRoleDefinitionId <String[]>]`: Bidang delegasiRoleDefinitionIds diperlukan saat roleDefinitionId merujuk ke Peran Administrator Akses Pengguna. Ini adalah daftar id definisi peran yang menentukan semua izin yang dapat ditetapkan pengguna dalam otorisasi ke prinsipal lain.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.

ELIGIBLEAUTHORIZATION <IEligibleAuthorization[]>: Kumpulan objek otorisasi yang memenuhi syarat yang menjelaskan akses tepat waktu Azure Active Directory prinsipal dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa terkelola.
  - `PrincipalId <String>`: Pengidentifikasi prinsipal Azure Active Directory.
  - `RoleDefinitionId <String>`: Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan dimiliki prinsipal Azure Active Directory pada lingkup yang diproyeksikan.
  - `[JustInTimeAccessPolicyManagedByTenantApprover <IEligibleApprover[]>]`: Daftar penyetuju managedByTenant untuk otorisasi yang memenuhi syarat.
    - `PrincipalId <String>`: Pengidentifikasi prinsipal Azure Active Directory.
    - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.
  - `[JustInTimeAccessPolicyMaximumActivationDuration <TimeSpan?>]`: Durasi akses maksimum dalam format ISO 8601 untuk permintaan akses tepat waktu.
  - `[JustInTimeAccessPolicyMultiFactorAuthProvider <MultiFactorAuthProvider?>]`: Penyedia otorisasi multifaktor yang akan digunakan untuk permintaan akses tepat waktu.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.

## RELATED LINKS

