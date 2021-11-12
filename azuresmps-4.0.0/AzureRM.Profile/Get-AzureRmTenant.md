---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 514e813cd9726ed6167725291bab8c23fb857b59b7026f42f8ed57daae66aef0
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419176"
---
# Get-AzureRmTenant

## SYNOPSIS
Mendapatkan penyewa yang diotorisasi untuk pengguna saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRmTenant [[-TenantId] <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzureRmTenant mendapatkan izin penyewa untuk pengguna saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyewa
```
PS C:\> Add-AzureRmAccount
PS C:\> Get-AzureRmTenant

TenantId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Domain   : microsoft.com

TenantId : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
Domain   : microsoft.com
```

Contoh ini menunjukkan cara mendapatkan semua penyewa resmi akun Azure.

### Contoh 2: Mendapatkan penyewa tertentu
```
PS C:\> Add-AzureRmAccount
PS C:\> Get-AzureRmTenant -TenantId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx

TenantId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Domain   : microsoft.com
```

Contoh ini menunjukkan cara untuk mendapatkan penyewa akun Azure resmi tertentu.

## PARAMETERS

### -TenantId
Menentukan ID penyewa yang akan dapatkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Domain, Tenant

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### PSAzureTenant
Cmdlet ini mengembalikan ID penyewa dan informasi domain terkait untuk penyewa yang diizinkan untuk akun saat ini.

## CATATAN

## RELATED LINKS

