---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/new-azmanagedservicesdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesDefinition.md
ms.openlocfilehash: 0f1e1b2633b8d825accb804ca5eaf54c100635a2
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139956651"
---
# New-AzManagedServicesDefinition

## SYNOPSIS
Membuat atau memperbarui definisi registrasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.managedservices/new-azmanagedservicesdefinition) untuk informasi terkini.

## SYNTAX

```
New-AzManagedServicesDefinition -Name <String> [-Scope <String>] [-Authorization <IAuthorization[]>]
 [-Description <String>] [-EligibleAuthorization <IEligibleAuthorization[]>] [-ManagedByTenantId <String>]
 [-PlanName <String>] [-PlanProduct <String>] [-PlanPublisher <String>] [-PlanVersion <String>]
 [-RegistrationDefinitionName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui definisi registrasi.

## EXAMPLES

### Contoh 1: Buat objek definisi pendaftaran Azure Lighthouse yang baru dengan otorisasi permanen
```powershell
PS C:\> $permantAuth = New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -DelegatedRoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx","xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

PS C:\> New-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -RegistrationDefinitionName "Test definition" -ManagedByTenantId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Authorization $permantAuth -Description "Test definition desc" -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" 

Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationDefinitions
```

Membuat objek definisi pendaftaran Azure Lighthouse yang baru dengan otorisasi permanen.

### Contoh 2: Buat objek definisi registrasi Azure Lighthouse yang baru dengan otorisasi permanen dan yang memenuhi syarat
```powershell
PS C:\> $approver = New-AzManagedServicesEligibleApproverObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Approver group"

PS C:\> $eligibleAuth = New-AzManagedServicesEligibleAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -JustInTimeAccessPolicyManagedByTenantApprover $approver -JustInTimeAccessPolicyMultiFactorAuthProvider Azure -JustInTimeAccessPolicyMaximumActivationDuration 0:30

PS C:\> New-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx-RegistrationDefinitionName "Test definition" -ManagedByTenantId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Authorization $permantAuth -EligibleAuthorization $eligibleAuth -Description "Test definition desc" -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxMicrosoft.ManagedServices/registrationDefinitions
```

Membuat objek definisi registrasi Azure Lighthouse baru dengan otorisasi permanen dan yang memenuhi syarat.

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

### -Authorization
Kumpulan objek otorisasi yang menjelaskan akses Azure Active Directory utama dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa yang dikelola.
Untuk membuat, lihat bagian CATATAN untuk properti OTORISASI dan membuat tabel hash.

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
Deskripsi definisi registrasi.

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
Kumpulan objek otorisasi yang memenuhi syarat yang menjelaskan akses langsung Azure Active Directory lokal dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa yang dikelola.
Untuk membuat, lihat bagian CATATAN untuk propertiAUTHORISASI YANG MEMENUHI SYARAT dan membuat tabel hash.

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
GUID definisi registrasi.

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
Menjalankan perintah secara asinkron

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
Nama paket Azure Marketplace.

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
Kode produk Azure Marketplace.

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
ID penerbit Azure Marketplace.

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
Versi paket Azure Marketplace.

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
Nama definisi registrasi.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationDefinition

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AUTHORIZATION <IAuthorization[]>: Kumpulan objek otorisasi yang menjelaskan prinsipal Azure Active Directory akses dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa terkelola.
  - `PrincipalId <String>`: Pengidentifikasi dari Azure Active Directory utama.
  - `RoleDefinitionId <String>`: Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan tersedia Azure Active Directory utamanya pada lingkup proyek.
  - `[DelegatedRoleDefinitionId <String[]>]`: Bidang delegatedRoleDefinitionIds diperlukan saat peranDefinitionId merujuk pada Peran Administrator Akses Pengguna. Ini adalah daftar id definisi peran yang menetapkan semua izin yang bisa ditetapkan pengguna ke prinsipal lain dalam otorisasi.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan pokok Azure Active Directory.

SITUS RESMI <IEligibleAuthorization[]>: Kumpulan objek otorisasi yang memenuhi syarat yang menjelaskan prinsipal Azure Active Directory akses langsung dalam penyewa managedBy akan diterima pada sumber daya yang didelegasikan dalam penyewa yang dikelola.
  - `PrincipalId <String>`: Pengidentifikasi dari Azure Active Directory utama.
  - `RoleDefinitionId <String>`: Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan tersedia Azure Active Directory utamanya pada lingkup proyek.
  - `[JustInTimeAccessPolicyManagedByTenantApprover <IEligibleApprover[]>]`: Daftar pemberi persetujuan ManagedByTenant untuk otorisasi yang memenuhi syarat.
    - `PrincipalId <String>`: Pengidentifikasi dari Azure Active Directory utama.
    - `[PrincipalIdDisplayName <String>]`: Nama tampilan pokok Azure Active Directory.
  - `[JustInTimeAccessPolicyMaximumActivationDuration <TimeSpan?>]`: Durasi akses maksimum dalam format ISO 8601 untuk permintaan akses langsung.
  - `[JustInTimeAccessPolicyMultiFactorAuthProvider <MultiFactorAuthProvider?>]`: Penyedia otorisasi multiftor yang akan digunakan untuk permintaan akses hanya dalam waktu.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan pokok Azure Active Directory.

## RELATED LINKS

