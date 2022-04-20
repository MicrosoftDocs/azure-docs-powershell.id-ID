---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azadapppermission
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADAppPermission.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADAppPermission.md
ms.openlocfilehash: 2bc17bcbe92e55d7904a0c7c2080769454965a8d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142695682"
---
# Get-AzADAppPermission

## SYNOPSIS
Mencantumkan izin API yang telah diminta oleh aplikasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azadapppermission) untuk informasi terbaru.

## SYNTAX

### ObjectIdParameterSet (Default)
```
Get-AzADAppPermission -ObjectId <Guid> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### AppIdParameterSet
```
Get-AzADAppPermission -ApplicationId <Guid> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan izin API yang telah diminta oleh aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan izin API
```powershell
PS C:\> Get-AzADAppPermission -ObjectId 18797549-86a9-4906-b2a9-54f08cd3c427

ApiId                                Id                                   Type
-----                                --                                   ----
00000003-0000-0000-c000-000000000000 df021288-bdef-4463-88db-98f22de89214 Scope
00000003-0000-0000-c000-000000000000 5b567255-7703-4780-807c-7be8301ae99b Scope
```

Mengambil semua izin API dari objek Azure AD 18797549-86a9-4906-b2a9-54f08cd3c427

## PARAMETERS

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
Id objek aplikasi.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.MicrosoftGraphApplicationApiPermission

## NOTES

ALIAS

## RELATED LINKS
