---
external help file: ''
Module Name: Azs.ContainerService.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerservice.admin/get-azscontainerservicequota
schema: 2.0.0
ms.openlocfilehash: fca146a861a6e1a07b2002a0111d5925770e9542
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143155367"
---
# Get-AzsContainerServiceQuota

## SYNOPSIS
Mengembalikan daftar kuota layanan kontainer di lokasi tertentu.

## SYNTAX

```
Get-AzsContainerServiceQuota [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan daftar kuota layanan kontainer di lokasi tertentu.

## EXAMPLES

### Contoh 1: Dapatkan Kuota untuk Container Service
```powershell
PS C:\> Get-AzsContainerServiceQuota -Location "redmond" | ConvertTo-Json
{
  "Id": "/subscriptions/f9712d12-aa4d-4d37-8f46-fabf3c07c836/providers/Microsoft.ContainerService.Admin/locations/redmond/quotas/Unlimited",
  "Name": "redmond/Unlimited",
  "PropertiesName": "Unlimited",
  "Type": "Microsoft.ContainerService.Admin/locations/quotas"
}
```

Mengembalikan kuota untuk layanan kontainer.

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

### -Lokasi
Nama kawasan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerServiceAdmin.Models.Api20191101.IContainerServiceQuotaListValueItem

## NOTES

ALIAS

## RELATED LINKS

