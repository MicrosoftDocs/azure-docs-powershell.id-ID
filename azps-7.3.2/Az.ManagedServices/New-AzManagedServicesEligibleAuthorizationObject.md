---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.ManagedServices/new-AzManagedServicesEligibleAuthorizationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesEligibleAuthorizationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesEligibleAuthorizationObject.md
ms.openlocfilehash: a0b5751f23385ce9b2f438a2c1d1a1b32053a89e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140571227"
---
# New-AzManagedServicesEligibleAuthorizationObject

## SYNOPSIS
Membuat objek dalam memori untukAuthorisasi yang Memenuhi Syarat

## SYNTAX

```
New-AzManagedServicesEligibleAuthorizationObject -PrincipalId <String> -RoleDefinitionId <String>
 [-JustInTimeAccessPolicyManagedByTenantApprover <IEligibleApprover[]>]
 [-JustInTimeAccessPolicyMaximumActivationDuration <TimeSpan>]
 [-JustInTimeAccessPolicyMultiFactorAuthProvider <MultiFactorAuthProvider>] [-PrincipalIdDisplayName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untukAuthorisasi yang Memenuhi Syarat

## EXAMPLES

### Contoh 1: Membuat objek otorisasi Mercusuar Azure yang baru yang memenuhi syarat untuk digunakan dengan definisi Registrasi
```powershell
PS C:\> New-AzManagedServicesEligibleAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

PrincipalId                          PrincipalIdDisplayName RoleDefinitionId
-----------                          ---------------------- ----------------
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Test user              xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Membuat objek otorisasi Azure Lighthouse yang memenuhi syarat untuk digunakan dengan definisi Registrasi.

### Contoh 2: Buat Mercusuar Azure baru yang memenuhi syarat otorisasi dengan pengaturan JustInTime
```powershell
PS C:\> $approver = New-AzManagedServicesEligibleApproverObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Approver group"

PS C:\> $eligibleAuth = New-AzManagedServicesEligibleAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -JustInTimeAccessPolicyManagedByTenantApprover $approver -JustInTimeAccessPolicyMultiFactorAuthProvider Azure -JustInTimeAccessPolicyMaximumActivationDuration 0:30

PS C:\> $eligibleAuth | Format-List -Property PrinciPalId, PrincipalIdDisplayName, RoleDefinitionId, JustInTimeAccessPolicyManagedByTenantApprover, JustInTimeAccessPolicyMultiFactorAuthProvider, JustInTimeAccessPolicyMaximumActivationDuration

PrincipalId                                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
PrincipalIdDisplayName                          : Test user
RoleDefinitionId                                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
JustInTimeAccessPolicyManagedByTenantApprover   : {Approver group}
JustInTimeAccessPolicyMultiFactorAuthProvider   : Azure
JustInTimeAccessPolicyMaximumActivationDuration : 00:30:00
```

Membuat objek otorisasi Azure Lighthouse yang memenuhi syarat dengan pengaturan JustInTime (JIT).

## PARAMETERS

### -JustInTimeAccessPolicyManagedByTenantApprover
Daftar pemberi persetujuan managedByTenant untuk otorisasi yang memenuhi syarat.
Untuk membuat, lihat bagian CATATAN untuk propertiASEACCESSPOLICYMANAGEDBYTENANTAPPROVER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IEligibleApprover[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JustInTimeAccessPolicyMaximumActivationDuration
Durasi akses maksimum dalam format ISO 8601 untuk permintaan akses langsung.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JustInTimeAccessPolicyMultiFactorAuthProvider
Penyedia otorisasi multi-faktor yang akan digunakan untuk permintaan akses hanya dalam waktu.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Support.MultiFactorAuthProvider
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalId
Pengidentifikasi dari Azure Active Directory pokok.

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

### -PrincipalIdDisplayName
Nama tampilan pokok Azure Active Directory.

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

### -RoleDefinitionId
Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan tersedia Azure Active Directory utamanya pada lingkup yang diproyeksikan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.EligibleAuthorization

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KMTIMEACCESSPOLICYMANAGEDBYTENANTAPPROVER <IEligibleApprover[]>: Daftar pemberi persetujuan managedByTenant untuk otorisasi yang memenuhi syarat.
  - `PrincipalId <String>`: Pengidentifikasi dari Azure Active Directory utama.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan pokok Azure Active Directory.

## RELATED LINKS

