---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.ManagedServices/new-AzManagedServicesAuthorizationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesAuthorizationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/New-AzManagedServicesAuthorizationObject.md
ms.openlocfilehash: b7f00c96aa36a75835b8b39d56a7080c4cb6d337
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142214749"
---
# New-AzManagedServicesAuthorizationObject

## SYNOPSIS
Membuat objek dalam memori untuk Otorisasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.managedservices/new-azmanagedservicesauthorizationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzManagedServicesAuthorizationObject -PrincipalId <String> -RoleDefinitionId <String>
 [-DelegatedRoleDefinitionId <String[]>] [-PrincipalIdDisplayName <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Otorisasi.

## EXAMPLES

### Contoh 1: Membuat objek Otorisasi Azure Lighthouse baru untuk digunakan dengan Definisi registrasi
```powershell
PS C:\> New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user"

DelegatedRoleDefinitionId PrincipalId                          PrincipalIdDisplayName RoleDefinitionId
------------------------- -----------                          ---------------------- ----------------
                          xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Test user              xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Membuat objek otorisasi Azure Lighthouse baru untuk digunakan dengan definisi Registrasi.

### Contoh 2: Membuat objek Azure Lighthouse Authorization baru dengan delegasiRoleDefinitionIds
```powershell
PS C:\> New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -DelegatedRoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

DelegatedRoleDefinitionId                                                    PrincipalId                          PrincipalIdDisplayName RoleDefinitionId
-------------------------                                                    -----------                          ---------------------- ----------------
{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx} xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Test user              xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Membuat objek otorisasi Azure Lighthouse baru dengan DelegatedRoleDefinitionIds.

## PARAMETERS

### -DelegatedRoleDefinitionId
Bidang delegasiRoleDefinitionIds diperlukan saat roleDefinitionId merujuk ke Peran Administrator Akses Pengguna.
Ini adalah daftar id definisi peran yang menentukan semua izin yang dapat ditetapkan pengguna dalam otorisasi ke prinsipal lain.

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

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.Authorization

## CATATAN

ALIAS

## RELATED LINKS

