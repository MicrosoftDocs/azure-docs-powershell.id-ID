---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azadapppermission
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADAppPermission.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADAppPermission.md
ms.openlocfilehash: 8c41befbeebaaf50346e718d3df9428e511170e1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140049728"
---
# Remove-AzADAppPermission

## SYNOPSIS
Menghapus izin API.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/remove-azadapppermission) untuk informasi terkini.

## SYNTAX

### ObjectIdParameterSet (Default)
```
Remove-AzADAppPermission -PermissionId <Guid> -ObjectId <Guid> [-DefaultProfile <PSObject>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AppIdParameterSet
```
Remove-AzADAppPermission -PermissionId <Guid> -ApplicationId <Guid> [-DefaultProfile <PSObject>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus izin API.

## EXAMPLES

### Contoh 1: Hapus Izin API
```powershell
PS C:\> Remove-AzADAppPermission -ObjectId 9cc74d5e-1162-4b90-8696-65f3d6a3f7d0 -PermissionId 5f8c59db-677d-491f-a6b8-5f174b11ec1d
```

Menghapus izin yang didelegasikan "Group.Read.All" dari Microsoft Graph API dari Aplikasi AD (9cc74d5e-1162-4b90-8696-65f3d6a3f7d0)

## PARAMETERS

### -ApplicationId
Pengidentifikasi unik untuk aplikasi yang ditetapkan oleh Azure AD.

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
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: True
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
