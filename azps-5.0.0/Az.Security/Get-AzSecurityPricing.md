---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/en-us/powershell/module/az.security/Get-AzSecurityPricing
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Security/Security/help/Get-AzSecurityPricing.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Security/Security/help/Get-AzSecurityPricing.md
ms.openlocfilehash: a1b07c5fb76d912ec117d42497f0d0b14bfb298c
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132407107"
---
# Get-AzSecurityPricing

## SYNOPSIS
Mendapatkan data tingkatan harga untuk Pusat Keamanan Azure untuk lingkupnya.

## SINTAKS

### SubscriptionScope (Default)
```
Get-AzSecurityPricing [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelResource
```
Get-AzSecurityPricing -Name <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzSecurityPricing -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Tingkatan harga Azure Security Center ditentukan per lingkup, dengan cmdlet ini Anda dapat memperoleh tingkatan harga yang dikonfigurasikan.
Tingkatan harga langganan mencakup semua grup sumber daya di bawahnya.
Tingkatan harga Grup Sumber Daya akan menimpa tingkat harga langganan.

## CONTOH

### Contoh 1
```powershell
PS C:\> Get-AzSecurityPricing
Id                                                                                                                             Name       PricingTier
--                                                                                                                             ----       -----------
Id--/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/VirtualMachines
--                                                                                                                             ----       -----------
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/SqlServers
/subscriptions/487bb485-b5b0-471e-9c0d-10717612f869/providers/Microsoft.Security/pricings/default                              default    Standard
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/AppServices
/subscriptions/487bb485-b5b0-471e-9c0d-10717612f869/resourceGroups/myService1/providers/Microsoft.Security/pricings/myService1 myService1 Standard
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/StorageAccounts
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/SqlServerVirtualMachin…
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/KubernetesService
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/ContainerRegistry
/subscriptions/fbaa2b23-e9dd-4bed-93c1-9e2a44f64bc0/providers/Microsoft.Security/pricings/KeyVaults
```

Mendapatkan semua tingkatan harga yang dikonfigurasi untuk langganan dan grup sumber daya di bawahnya.

### Contoh 2
```powershell
PS C:\> Get-AzSecurityPricing -ResourceGroupName "myService1"
Id                                                                                                                             Name       PricingTier
--                                                                                                                             ----       -----------
/subscriptions/487bb485-b5b0-471e-9c0d-10717612f869/resourceGroups/myService1/providers/Microsoft.Security/pricings/myService1 myService1 Standard
```

Mendapatkan tingkatan harga yang dikonfigurasi untuk grup sumber daya "myService1".

## PARAMETERS

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

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: SubscriptionLevelResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Security.Models.Pricings.PSSecurityPricing

## CATATAN

## LINK TERKAIT
