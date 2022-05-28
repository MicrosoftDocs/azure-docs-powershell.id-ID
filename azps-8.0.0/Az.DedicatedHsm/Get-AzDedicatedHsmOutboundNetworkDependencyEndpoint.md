---
external help file: ''
Module Name: Az.DedicatedHsm
online version: https://docs.microsoft.com/powershell/module/az.dedicatedhsm/get-azdedicatedhsmoutboundnetworkdependencyendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DedicatedHsm/help/Get-AzDedicatedHsmOutboundNetworkDependencyEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DedicatedHsm/help/Get-AzDedicatedHsmOutboundNetworkDependencyEndpoint.md
ms.openlocfilehash: 90d45f6fa85a06b52958fb0368445bd6ae391877
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145507387"
---
# Get-AzDedicatedHsmOutboundNetworkDependencyEndpoint

## SYNOPSIS
Mendapatkan daftar titik akhir keluar (titik akhir jaringan dari semua dependensi keluar) di sumber daya hsm khusus yang ditentukan.
Operasi mengembalikan properti dari setiap titik akhir keluar.

## SYNTAX

```
Get-AzDedicatedHsmOutboundNetworkDependencyEndpoint -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar titik akhir keluar (titik akhir jaringan dari semua dependensi keluar) di sumber daya hsm khusus yang ditentukan.
Operasi mengembalikan properti dari setiap titik akhir keluar.

## EXAMPLES

### Contoh 1: Mendapatkan daftar titik akhir keluar (titik akhir jaringan dari semua dependensi keluar) di sumber daya hsm khusus yang ditentukan.
```powershell
Get-AzDedicatedHsmOutboundNetworkDependencyEndpoint -Name dedicatedHsmName01 -ResourceGroupName resourceGroup
```

Perintah ini mendapatkan daftar titik akhir keluar (titik akhir jaringan dari semua dependensi keluar) dalam sumber daya hsm khusus yang ditentukan.
Operasi mengembalikan properti dari setiap titik akhir keluar.

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
Nama HSM khusus.

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
Nama Grup Sumber Daya tempat hsm khusus berada.

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
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DedicatedHsm.Models.Api20211130.IOutboundEnvironmentEndpoint

## NOTES

ALIAS

## RELATED LINKS

