---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/get-azmigratesite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateSite.md
ms.openlocfilehash: d9c7498d7277992d414a8d0fc21aa3a07108dc2e
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136575061"
---
# Get-AzMigrateSite

## SYNOPSIS
Metode untuk mendapatkan situs.

## SYNTAX

```
Get-AzMigrateSite -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Metode untuk mendapatkan situs.

## EXAMPLES

### Contoh 1: Get (Default)
```powershell
PS C:\> Get-AzMigrateSite -SubscriptionId xxx-xxx-xxx -ResourceGroupName BugBashAVSVMware -SiteName BBVMwareAVScbbcsite

ETag Location      Name                Type
---- --------      ----                ----
     southeastasia BBVMwareAVScbbcsite Microsoft.OffAzure/VMwareSites

```

Dapatkan situs berdasarkan nama

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

### -Nama
Nama situs.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SiteName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api202001.IVMwareSite

## CATATAN

ALIAS

## RELATED LINKS

