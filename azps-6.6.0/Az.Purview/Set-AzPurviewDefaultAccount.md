---
external help file: ''
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/set-azpurviewdefaultaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Set-AzPurviewDefaultAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Set-AzPurviewDefaultAccount.md
ms.openlocfilehash: c99e927d6b7e3fb39b8c86014a13812cb7f65af4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143355420"
---
# Set-AzPurviewDefaultAccount

## SYNOPSIS
Mengatur akun default untuk lingkup.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.purview/set-azpurviewdefaultaccount) untuk informasi terbaru.

## SYNTAX

```
Set-AzPurviewDefaultAccount -AccountName <String> -ResourceGroupName <String> -ScopeTenantId <String>
 [-Scope <String>] [-ScopeType <ScopeType>] [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengatur akun default untuk lingkup.

## EXAMPLES

### Contoh 1: Mengatur akun default untuk lingkup.
```powershell
PS C:\> Set-AzPurviewDefaultAccount -AccountName test-pa -ResourceGroupName test-rg -ScopeTenantId xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a

AccountName ResourceGroupName Scope                                ScopeTenantId                        ScopeType SubscriptionId
----------- ----------------- -----                                -------------                        --------- --------------
test-pa      test-rg            xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a Tenant    xxxxxxxx-1bf0-4dda-aec3
```

`test-pa` Mengatur sebagai akun default untuk lingkup.

## PARAMETERS

### -AccountName
Nama akun yang diatur sebagai default.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya akun yang diatur sebagai default.

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

### -Lingkup
ID objek lingkup.
Misalnya, sub ID atau ID penyewa.

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

### -ScopeTenantId
Penyewa lingkup tempat akun default diatur.

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

### -ScopeType
Lingkup di mana akun default diatur.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Support.ScopeType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan akun yang diatur sebagai default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.Api20210701.IDefaultAccountPayload

## NOTES

ALIAS

## RELATED LINKS

