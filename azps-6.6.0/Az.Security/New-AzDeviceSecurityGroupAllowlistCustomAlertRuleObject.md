---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject.md
ms.openlocfilehash: 9762d109efabce3bc15a0d49894f7599e8d0604f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141859928"
---
# New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject

## SYNOPSIS
Membuat aturan pemberitahuan kustom daftar perbolehkan baru untuk grup keamanan perangkat (Keamanan IoT)

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.security/new-azdevicesecuritygroupallowlistcustomalertruleobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject -Enabled <Boolean> -Type <String>
 -AllowlistValue <String[]> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject membuat daftar baru aturan peringatan kustom yang diperbolehkan untuk grup keamanan perangkat dalam solusi keamanan IoT.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzDeviceSecurityGroupAllowlistCustomAlertRuleObject -Enabled $false -Type "LocalUserNotAllowed" -AllowlistValue @()

RuleType: "LocalUserNotAllowed"
DisplayName: "Login by a local user that isn't allowed"
Description: "Get an alert when a local user that isn't allowed logins to the device"
IsEnabled: false
ValueType: "String"
AllowlistValues: []
```

Membuat daftar perbolehkan baru pemberitahuan kustom rull dari tipe "LocalUserNotAllowed" dengan status diatur ke nonaktif

## PARAMETERS

### -AllowlistValue
Perbolehkan nilai daftar.

```yaml
Type: System.String[]
Parameter Sets: (All)
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Difungsikan
Aturan diaktifkan.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Tipe aturan.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.DeviceSecurityGroups.PSAllowlistCustomAlertRule

## CATATAN

## RELATED LINKS
