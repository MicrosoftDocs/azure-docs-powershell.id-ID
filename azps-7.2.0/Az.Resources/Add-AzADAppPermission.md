---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/add-azadapppermission
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADAppPermission.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADAppPermission.md
ms.openlocfilehash: b72456728c7d1c00d86f064d1e3fc4cefc73d26e
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138303323"
---
# Add-AzADAppPermission

## SYNOPSIS
Menambahkan izin API.

## SYNTAX

### ObjectIdParameterSet (Default)
```
Add-AzADAppPermission -ApiId <Guid> -PermissionId <String> -ObjectId <Guid> [-Type <String>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AppIdParameterSet
```
Add-AzADAppPermission -ApiId <Guid> -PermissionId <String> [-Type <String>] -ApplicationId <Guid>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menambahkan izin API.
Daftar izin API yang tersedia adalah properti dari aplikasi yang diwakili oleh prinsipal layanan dalam penyewa.

Sebagai contoh, untuk mendapatkan izin yang tersedia untuk Graph API:
* Azure Active Directory Graph:`Get-AzAdServicePrincipal -ApplicationId 00000002-0000-0000-c000-000000000000`
* Microsoft Graph:`Get-AzAdServicePrincipal -ApplicationId 00000003-0000-0000-c000-000000000000`

Izin aplikasi di bawah `appRoles` properti yang berkaitan `Role` dengan dalam `-Type`.
Izin yang didelegasikan di `oauth2Permissions` bawah properti yang berkaitan `Scope` dengan dalam `-Type`.

Pengguna harus memberikan izin melalui Portal Azure jika izin tersebut memerlukan izin admin Azure PowerShell karena Azure PowerShell belum mendukungnya.

## EXAMPLES

### Contoh 1: Tambahkan Izin API
```powershell
PS C:\> Add-AzADAppPermission -ObjectId 9cc74d5e-1162-4b90-8696-65f3d6a3f7d0 -ApiId 00000003-0000-0000-c000-000000000000 -PermissionId 5f8c59db-677d-491f-a6b8-5f174b11ec1d
```

Menambahkan izin yang didelegasikan "Group.Read.All" dari Microsoft Graph API ke Aplikasi AD (9cc74d5e-1162-4b90-8696-65f3d6a3f7d0)

### Contoh 2: Tambahkan Izin API
```powershell
PS C:\> Add-AzADAppPermission -ObjectId 9cc74d5e-1162-4b90-8696-65f3d6a3f7d0 -ApiId 00000003-0000-0000-c000-000000000000 -PermissionId 1138cb37-bd11-4084-a2b7-9f71582aeddb -Type Role
```

Tambahkan izin aplikasi "Device.ReadWrite.All" dari API Microsoft Graph ke AD Application (9cc74d5e-1162-4b90-8696-65f3d6a3f7d0)

## PARAMETERS

### -ApiId
Pengidentifikasi unik untuk sumber daya yang diperlukan akses aplikasi.
Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationId
Id aplikasi.

```yaml
Type: System.Guid
Parameter Sets: AppIdParameterSet
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
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Pengidentifikasi unik di Azure AD.

```yaml
Type: System.Guid
Parameter Sets: ObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermissionId
Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang mengekspos aplikasi sumber daya.

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

### -Tipe
Menentukan apakah properti id merujuk pada oauth2PermissionScopes(Scope, delegated permission) atau appRole(Role, application permission).

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

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS
