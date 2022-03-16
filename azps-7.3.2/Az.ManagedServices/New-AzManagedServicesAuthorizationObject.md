---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.ManagedServices/new-AzManagedServicesAuthorizationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesAuthorizationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesAuthorizationObject.md
ms.openlocfilehash: 3dbc06c571f0228aaa1ce45e247dd7cd42962fd8
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000365"
---
# New-AzManagedServicesAuthorizationObject

## SYNOPSIS
Buat objek dalam memori untuk Otorisasi.

## SYNTAX

```
New-AzManagedServicesAuthorizationObject -PrincipalId <String> -RoleDefinitionId <String>
 [-DelegatedRoleDefinitionId <String[]>] [-PrincipalIdDisplayName <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk Otorisasi.

## EXAMPLES

### Contoh 1: Buat objek Otorisasi Mercusuar Azure yang baru untuk digunakan dengan definisi Registrasi
```powershell
PS C:\> New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user"

DelegatedRoleDefinitionId PrincipalId                          PrincipalIdDisplayName RoleDefinitionId
------------------------- -----------                          ---------------------- ----------------
                          xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Test user              xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Membuat objek otorisasi Mercusuar Azure baru untuk digunakan dengan definisi Registrasi.

### Contoh 2: Membuat objek Azure Lighthouse Authorization baru dengan delegatedRoleDefinitionIds
```powershell
PS C:\> New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -DelegatedRoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

DelegatedRoleDefinitionId                                                    PrincipalId                          PrincipalIdDisplayName RoleDefinitionId
-------------------------                                                    -----------                          ---------------------- ----------------
{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx} xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Test user              xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Membuat objek otorisasi Mercusuar Azure baru dengan pendelegasikanRoleDefinitionIds.

## PARAMETERS

### -DelegatedRoleDefinitionId
Bidang delegatedRoleDefinitionIds diperlukan saat peranDefinitionId merujuk pada Peran Administrator Akses Pengguna.
Ini adalah daftar id definisi peran yang menetapkan semua izin yang bisa ditetapkan pengguna ke prinsipal lain dalam otorisasi.

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

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.Authorization

## CATATAN

ALIAS

## RELATED LINKS

