---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/new-azmanagedservicesdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesDefinition.md
ms.openlocfilehash: a31e90d556945221ca5cd7189af24d77b7404e39
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144598064"
---
# New-AzManagedServicesDefinition

## SYNOPSIS
Membuat atau memperbarui definisi pendaftaran.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.managedservices/new-azmanagedservicesdefinition) untuk informasi terbaru.

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

### Contoh 1: Membuat objek definisi pendaftaran Azure Lighthouse baru dengan otorisasi permanen
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

### -Otorisasi
Pengumpulan objek otorisasi yang menjelaskan akses Azure Active Directory utama di penyewa managedBy akan menerima sumber daya yang didelegasikan di penyewa terkelola.
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
Deskripsi definisi pendaftaran.

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
Pengumpulan objek otorisasi yang memenuhi syarat yang menjelaskan akses just-in-time Azure Active Directory utama di penyewa managedBy akan menerima sumber daya yang didelegasikan di penyewa terkelola.
Untuk membuat, lihat bagian CATATAN untuk properti ELIGIBLEAUTHORIZATION dan buat tabel hash.

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

### -Name
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
Marketplace Azure nama paket.

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
Marketplace Azure ID penerbit.

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

### -Cakupan
Cakupan sumber daya.

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

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationDefinition

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


OTORISASI <IAuthorization[]>: Kumpulan objek otorisasi yang menjelaskan akses Azure Active Directory utama di penyewa managedBy akan menerima sumber daya yang didelegasikan di penyewa terkelola.
  - `PrincipalId <String>`: Pengidentifikasi perwakilan Azure Active Directory.
  - `RoleDefinitionId <String>`: Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan dimiliki Azure Active Directory utama pada cakupan yang diproyeksikan.
  - `[DelegatedRoleDefinitionId <String[]>]`: Bidang delegatedRoleDefinitionIds diperlukan saat roleDefinitionId mengacu pada Peran Administrator Akses Pengguna. Ini adalah daftar id definisi peran yang menentukan semua izin yang dapat ditetapkan pengguna dalam otorisasi ke prinsipal lain.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.

ELIGIBLEAUTHORIZATION <IEligibleAuthorization[]>: Pengumpulan objek otorisasi yang memenuhi syarat yang menjelaskan akses just-in-time Azure Active Directory utama di penyewa managedBy akan menerima sumber daya yang didelegasikan di penyewa terkelola.
  - `PrincipalId <String>`: Pengidentifikasi perwakilan Azure Active Directory.
  - `RoleDefinitionId <String>`: Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan dimiliki Azure Active Directory utama pada cakupan yang diproyeksikan.
  - `[JustInTimeAccessPolicyManagedByTenantApprover <IEligibleApprover[]>]`: Daftar pemberi izin managedByTenant untuk otorisasi yang memenuhi syarat.
    - `PrincipalId <String>`: Pengidentifikasi perwakilan Azure Active Directory.
    - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.
  - `[JustInTimeAccessPolicyMaximumActivationDuration <TimeSpan?>]`: Durasi akses maksimum dalam format ISO 8601 untuk permintaan akses just-in-time.
  - `[JustInTimeAccessPolicyMultiFactorAuthProvider <MultiFactorAuthProvider?>]`: Penyedia otorisasi multifaktor yang akan digunakan untuk permintaan akses just-in-time.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.

## RELATED LINKS

