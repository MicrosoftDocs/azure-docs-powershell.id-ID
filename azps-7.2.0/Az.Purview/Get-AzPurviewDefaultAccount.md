---
external help file: ''
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewdefaultaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Get-AzPurviewDefaultAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Get-AzPurviewDefaultAccount.md
ms.openlocfilehash: db0398c348904dc0f499271886937c927f93d877
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138312251"
---
# Get-AzPurviewDefaultAccount

## SYNOPSIS
Dapatkan akun default untuk lingkup tersebut.

## SYNTAX

```
Get-AzPurviewDefaultAccount -ScopeTenantId <String> -ScopeType <ScopeType> [-Scope <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan akun default untuk lingkup tersebut.

## EXAMPLES

### Contoh 1: Dapatkan akun default untuk lingkup Penyewa.
```powershell
PS C:\> Get-AzPurviewDefaultAccount -ScopeTenantId xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a -ScopeType Tenant

AccountName ResourceGroupName Scope                                ScopeTenantId                        ScopeType SubscriptionId
----------- ----------------- -----                                -------------                        --------- --------------
test-pa      test-rg            xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a Tenant    xxxxxxxx-1bf0-4dda-aec3
```

Mendapatkan akun default untuk lingkup Penyewa

## PARAMETERS

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

### -Lingkup
Id objek lingkup, misalnya jika lingkup adalah "Langganan" maka ID langganan tersebut.

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
ID penyewa.

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
Lingkup akun default.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Support.ScopeType
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

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.Api20210701.IDefaultAccountPayload

## CATATAN

ALIAS

## RELATED LINKS

