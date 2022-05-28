---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/add-azadapppermission
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADAppPermission.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADAppPermission.md
ms.openlocfilehash: 3dad627aa3ce69800d89ef142ab14a433418625e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145551959"
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
Daftar izin API yang tersedia adalah properti aplikasi yang diwakili oleh perwakilan layanan dalam penyewa.

Misalnya, untuk mendapatkan izin yang tersedia untuk API Graph:
* Azure Active Directory Graph:`Get-AzAdServicePrincipal -ApplicationId 00000002-0000-0000-c000-000000000000`
* Microsoft Graph: `Get-AzAdServicePrincipal -ApplicationId 00000003-0000-0000-c000-000000000000`

Izin aplikasi di `appRoles` bawah properti sesuai dengan `Role` di `-Type`.
Izin yang didelegasikan di `oauth2Permissions` bawah properti sesuai dengan `Scope` di `-Type`.

Pengguna perlu memberikan persetujuan melalui Portal Microsoft Azure jika izin memerlukan persetujuan admin karena Azure PowerShell belum mendukungnya.

## EXAMPLES

### Contoh 1: Menambahkan Izin API
```powershell
Add-AzADAppPermission -ObjectId 9cc74d5e-1162-4b90-8696-65f3d6a3f7d0 -ApiId 00000003-0000-0000-c000-000000000000 -PermissionId 5f8c59db-677d-491f-a6b8-5f174b11ec1d
```

Menambahkan izin yang didelegasikan "Group.Read.All" dari Microsoft Graph API ke Aplikasi AD (9cc74d5e-1162-4b90-8696-65f3d6a3f7d0)

### Contoh 2: Menambahkan Izin API
```powershell
Add-AzADAppPermission -ObjectId 9cc74d5e-1162-4b90-8696-65f3d6a3f7d0 -ApiId 00000003-0000-0000-c000-000000000000 -PermissionId 1138cb37-bd11-4084-a2b7-9f71582aeddb -Type Role
```

Tambahkan izin aplikasi "Device.ReadWrite.All" dari Microsoft Graph API ke Aplikasi AD (9cc74d5e-1162-4b90-8696-65f3d6a3f7d0)

## PARAMETERS

### -ApiId
Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.
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
Pengidentifikasi unik dalam Azure AD.

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
Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang diekspos aplikasi sumber daya.

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

### -Type
Menentukan apakah properti id mereferensikan oauth2PermissionScopes(Cakupan, izin yang didelegasikan) atau appRole(Peran, izin aplikasi).

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

### System.Boolean

## NOTES

ALIAS

## RELATED LINKS
