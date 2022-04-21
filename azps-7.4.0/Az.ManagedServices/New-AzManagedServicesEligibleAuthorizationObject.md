---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.ManagedServices/new-AzManagedServicesEligibleAuthorizationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesEligibleAuthorizationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesEligibleAuthorizationObject.md
ms.openlocfilehash: 63d00bc2600f06d57c159c58d9a56416e62b2b6d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142746154"
---
# New-AzManagedServicesEligibleAuthorizationObject

## SYNOPSIS
Membuat objek dalam memori untuk Pengabaian yang Memenuhi Syarat

## SYNTAX

```
New-AzManagedServicesEligibleAuthorizationObject -PrincipalId <String> -RoleDefinitionId <String>
 [-JustInTimeAccessPolicyManagedByTenantApprover <IEligibleApprover[]>]
 [-JustInTimeAccessPolicyMaximumActivationDuration <TimeSpan>]
 [-JustInTimeAccessPolicyMultiFactorAuthProvider <MultiFactorAuthProvider>] [-PrincipalIdDisplayName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Pengabaian yang Memenuhi Syarat

## EXAMPLES

### Contoh 1: Membuat objek otorisasi Azure Lighthouse baru yang memenuhi syarat untuk digunakan dengan Definisi registrasi
```powershell
New-AzManagedServicesEligibleAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```

```output
PrincipalId                          PrincipalIdDisplayName RoleDefinitionId
-----------                          ---------------------- ----------------
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Test user              xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Membuat objek otorisasi Azure Lighthouse baru yang memenuhi syarat untuk digunakan dengan definisi Registrasi.

### Contoh 2: Membuat otorisasi Azure Lighthouse baru yang memenuhi syarat dengan pengaturan JustInTime
```powershell
$approver = New-AzManagedServicesEligibleApproverObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Approver group"

$eligibleAuth = New-AzManagedServicesEligibleAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -JustInTimeAccessPolicyManagedByTenantApprover $approver -JustInTimeAccessPolicyMultiFactorAuthProvider Azure -JustInTimeAccessPolicyMaximumActivationDuration 0:30

$eligibleAuth | Format-List -Property PrinciPalId, PrincipalIdDisplayName, RoleDefinitionId, JustInTimeAccessPolicyManagedByTenantApprover, JustInTimeAccessPolicyMultiFactorAuthProvider, JustInTimeAccessPolicyMaximumActivationDuration
```

```output
PrincipalId                                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
PrincipalIdDisplayName                          : Test user
RoleDefinitionId                                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
JustInTimeAccessPolicyManagedByTenantApprover   : {Approver group}
JustInTimeAccessPolicyMultiFactorAuthProvider   : Azure
JustInTimeAccessPolicyMaximumActivationDuration : 00:30:00
```

Membuat objek otorisasi Azure Lighthouse baru yang memenuhi syarat dengan pengaturan JustInTime (JIT).

## PARAMETERS

### -JustInTimeAccessPolicyManagedByTenantApprover
Daftar penyetuju managedByTenant untuk otorisasi yang memenuhi syarat.
Untuk membangun, lihat bagian CATATAN untuk properti JUSTINTIMEACCESSPOLICYMANAGEDBYTENANTAPPROVER dan membuat tabel hash.

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
Durasi akses maksimum dalam format ISO 8601 untuk permintaan akses tepat waktu.

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
Penyedia multi-factor authorization yang akan digunakan untuk permintaan akses tepat waktu.

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
Pengidentifikasi prinsipal Azure Active Directory.

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
Nama tampilan prinsipal Azure Active Directory.

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
Pengidentifikasi peran bawaan Azure yang menentukan izin yang akan dimiliki prinsipal Azure Active Directory pada lingkup yang diproyeksikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.EligibleAuthorization

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


JUSTINTIMEACCESSPOLICYMANAGEDBYTENANTAPPROVER <IEligibleApprover[]>: Daftar penyetuju ManagedByTenant untuk otorisasi yang memenuhi syarat.
  - `PrincipalId <String>`: Pengidentifikasi prinsipal Azure Active Directory.
  - `[PrincipalIdDisplayName <String>]`: Nama tampilan prinsipal Azure Active Directory.

## RELATED LINKS

