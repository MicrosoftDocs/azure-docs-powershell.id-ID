---
external help file: ''
Module Name: Azs.ContainerService.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerservice.admin/get-azscontainerservice
schema: 2.0.0
ms.openlocfilehash: 045a244f8925ae2c6457cb8c00b83a97a3aa3960
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141919425"
---
# Get-AzsContainerService

## SYNOPSIS
Mengembalikan daftar kluster terkelola yang ada di semua lokasi penyewa.

## SYNTAX

```
Get-AzsContainerService [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan daftar kluster terkelola yang ada di semua lokasi penyewa.

## EXAMPLES

### Contoh 1: Dapatkan daftar kluster terkelola
```powershell
PS C:\> Get-AzsContainerService -Location "redmond" | ConvertTo-Json
[
  {
    "CreationDate": "2021-08-24T21:33:46Z",
    "Id": "/subscriptions/f9712d12-aa4d-4d37-8f46-fabf3c07c836/providers/Microsoft.ContainerService.Admin/locations/redmond/managedclusters/testaksux",
    "Location": "redmond",
    "Name": "redmond/testaksux",
    "OrchestratorVersion": "1.19.11",
    "PropertiesId": "/subscriptions/16661f04-6eca-4ccb-acef-3624fc128005/resourcegroups/testaksuxrg/providers/Microsoft.ContainerService/managedClusters/testaksux",
    "PropertiesName": "testaksux",
    "ProvisioningState": "Succeeded",
    "SubscriptionId": "16661f04-6eca-4ccb-acef-3624fc128005",
    "Type": "Microsoft.ContainerService.Admin/locations/managedclusters"
  },
  {
    "CreationDate": "2021-08-25T20:02:38Z",
    "Id": "/subscriptions/f9712d12-aa4d-4d37-8f46-fabf3c07c836/providers/Microsoft.ContainerService.Admin/locations/redmond/managedclusters/testaksaddon",
    "Location": "redmond",
    "Name": "redmond/testaksaddon",
    "OrchestratorVersion": "1.19.11",
    "PropertiesId": "/subscriptions/a174daa5-4b9c-4745-8d80-ca8a6c1e2279/resourcegroups/testaksaddonrg/providers/Microsoft.ContainerService/managedClusters/testaksaddon",
    "PropertiesName": "testaksaddon",
    "ProvisioningState": "Succeeded",
    "SubscriptionId": "a174daa5-4b9c-4745-8d80-ca8a6c1e2279",
    "Type": "Microsoft.ContainerService.Admin/locations/managedclusters"
  }
]
```

Mengembalikan daftar semua kluster layanan kontainer penyewa.

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerServiceAdmin.Models.Api20191101.IContainerServicesListValueItem

## CATATAN

ALIAS

## RELATED LINKS

