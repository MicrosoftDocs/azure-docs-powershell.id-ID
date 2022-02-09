---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/get-azelasticdeploymentinfo
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticDeploymentInfo.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticDeploymentInfo.md
ms.openlocfilehash: 8ace258421e4304602b4bde5fcf705565fec9cf2
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138169297"
---
# Get-AzElasticDeploymentInfo

## SYNOPSIS
Ambil informasi terkait penyebaran awan Elastis yang terkait dengan sumber daya monitor Elastis.

## SYNTAX

```
Get-AzElasticDeploymentInfo -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Ambil informasi terkait penyebaran awan Elastis yang terkait dengan sumber daya monitor Elastis.

## EXAMPLES

### Contoh 1: Mengambil informasi terkait penyebaran awan Elastis yang terkait dengan sumber daya monitor Elastis
```powershell
PS C:\> Get-AzElasticDeploymentInfo -ResourceGroupName elastic-rg-3eytki -Name elastic-rhqz1v

DiskCapacity MemoryCapacity Status  Version
------------ -------------- ------  -------
491520       16384          Healthy 7.14.1
```

Perintah ini mengambil informasi terkait penyebaran awan Elastis yang terkait dengan sumber daya monitor Elastis.

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
Nama grup sumber daya tempat sumber daya Elastis dimiliki.

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
ID langganan Azure.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-00000000000)

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

### Microsoft.Azure.PowerShell.Cmdlets.Elastis.Models.Api20200701.IDeploymentInfoResponse

## CATATAN

ALIAS

## RELATED LINKS

