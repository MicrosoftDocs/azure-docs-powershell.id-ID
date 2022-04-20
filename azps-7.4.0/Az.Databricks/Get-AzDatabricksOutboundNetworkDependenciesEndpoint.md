---
external help file: ''
Module Name: Az.Databricks
online version: https://docs.microsoft.com/powershell/module/az.databricks/get-azdatabricksoutboundnetworkdependenciesendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Get-AzDatabricksOutboundNetworkDependenciesEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Get-AzDatabricksOutboundNetworkDependenciesEndpoint.md
ms.openlocfilehash: e187f9eb52504c4bbb082475eac473a98f9f5a65
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142684630"
---
# Get-AzDatabricksOutboundNetworkDependenciesEndpoint

## SYNOPSIS
Mendapatkan daftar titik akhir yang VNET Injected Workspace memanggil Azure Databricks Control Plane.
Anda harus mengonfigurasi akses keluar dengan titik akhir ini.
Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/azure/databricks/administration-guide/cloud-configurations/azure/udr

## SYNTAX

```
Get-AzDatabricksOutboundNetworkDependenciesEndpoint -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar titik akhir yang VNET Injected Workspace memanggil Azure Databricks Control Plane.
Anda harus mengonfigurasi akses keluar dengan titik akhir ini.
Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/azure/databricks/administration-guide/cloud-configurations/azure/udr

## EXAMPLES

### Contoh 1: Mendapatkan daftar titik akhir yang VNET Injected Workspace memanggil Azure Databricks Control Plane
```powershell
Get-AzDatabricksOutboundNetworkDependenciesEndpoint -ResourceGroupName "databricks-rg-zbpoy7" -WorkspaceName databricks-portal
```

```output
Category : Webapp
Endpoint : {{
             "endpointDetails": [
               {
                 "ipAddress": "40.70.58.221/32",
                 "port": 443
               },
               {
                 "ipAddress": "20.42.4.209/32",
                 "port": 443
               },
               {
                 "ipAddress": "20.42.4.211",
                 "port": 443
               }
             ]
           }}

Category : Control Plane NAT
Endpoint : {{
             "endpointDetails": [
               {
                 "ipAddress": "23.101.152.95/32",
                 "port": 443
               },
               {
                 "ipAddress": "20.42.4.208/32",
                 "port": 443
               },
               {
                 "ipAddress": "20.42.4.210",
                 "port": 443
               }
             ]
           }}

Category : Extended infrastructure
Endpoint : {{
             "endpointDetails": [
               {
                 "ipAddress": "20.57.106.0/28",
                 "port": 443
               }
             ]
           }}
```

Perintah ini mendapatkan daftar titik akhir yang VNET Injected Workspace memanggil Azure Databricks Control Plane.
Anda harus mengonfigurasi akses keluar dengan titik akhir ini.
Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/azure/databricks/administration-guide/cloud-configurations/azure/udr

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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

### -Nama Ruang Kerja
Nama ruang kerja.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20210401Preview.IOutboundEnvironmentEndpoint

## NOTES

ALIAS

## RELATED LINKS

