---
external help file: ''
Module Name: Az.Databricks
online version: https://docs.microsoft.com/powershell/module/az.databricks/get-azdatabricksoutboundnetworkdependenciesendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Get-AzDatabricksOutboundNetworkDependenciesEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/Get-AzDatabricksOutboundNetworkDependenciesEndpoint.md
ms.openlocfilehash: d8f2f86d81788ce5d6b5b2bce17f59a913d8e6ed
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140179768"
---
# Get-AzDatabricksOutboundNetworkDependenciesEndpoint

## SYNOPSIS
Mendapatkan daftar titik akhir yang ruang kerja Ruang Kerja VNET menghubungi Azure Databricks Control Plane.
Anda harus mengonfigurasi akses keluar dengan titik akhir ini.
Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/azure/databricks/administration-guide/cloud-configurations/azure/udr

## SYNTAX

```
Get-AzDatabricksOutboundNetworkDependenciesEndpoint -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar titik akhir yang ruang kerja Ruang Kerja VNET menghubungi Azure Databricks Control Plane.
Anda harus mengonfigurasi akses keluar dengan titik akhir ini.
Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/azure/databricks/administration-guide/cloud-configurations/azure/udr

## EXAMPLES

### Contoh 1: Mendapatkan daftar titik akhir yang disebut VNET In sinkronisasi Workspace memanggil Azure Databricks Control Plane
```powershell
PS C:\> Get-AzDatabricksOutboundNetworkDependenciesEndpoint -ResourceGroupName "databricks-rg-zbpoy7" -WorkspaceName databricks-portal

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

Perintah ini mendapatkan daftar titik akhir yang disebut VNET In azure databricks Control Plane.
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

### -WorkspaceName
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20210401Preview.IOutboundEnvironmentEndpoint

## CATATAN

ALIAS

## RELATED LINKS

