---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/get-azelasticvmhost
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticVMHost.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticVMHost.md
ms.openlocfilehash: 2fc4b6248ba8c8ff756cdfec7525a960e7d239f8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144247936"
---
# Get-AzElasticVMHost

## SYNOPSIS
Cantumkan sumber daya vm yang saat ini sedang dipantau oleh sumber daya monitor Elastic.

## SYNTAX

```
Get-AzElasticVMHost -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Cantumkan sumber daya vm yang saat ini sedang dipantau oleh sumber daya monitor Elastic.

## EXAMPLES

### Contoh 1: Mencantumkan sumber daya vm yang saat ini sedang dipantau oleh sumber daya monitor Elastic
```powershell
Get-AzElasticVMHost -ResourceGroupName azure-elastic-test -Name elastic-pwsh02
```

```output
VMResourceId
------------
/subscriptions/xxxxxx-xxxxx-xxxx-xxxxxx/resourceGroups/vidhi-rg/providers/Microsoft.Compute/virtualMachines/vidhi-linuxOS
```

Perintah ini mencantumkan sumber daya vm yang saat ini sedang dipantau oleh sumber daya monitor Elastic.

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

### -Name
Memantau nama sumber daya

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

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya Elastic berada.

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
Atur ID Langganan Azure.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000)

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

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.IVMResources

## NOTES

ALIAS

## RELATED LINKS

