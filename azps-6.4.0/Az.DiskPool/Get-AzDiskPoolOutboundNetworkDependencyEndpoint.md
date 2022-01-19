---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpooloutboundnetworkdependencyendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolOutboundNetworkDependencyEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolOutboundNetworkDependencyEndpoint.md
ms.openlocfilehash: a6f5ba633bdc83bfdf79ef6e0598b3fa60e9f850
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136207181"
---
# Get-AzDiskPoolOutboundNetworkDependencyEndpoint

## SYNOPSIS
Mendapatkan titik akhir jaringan dari semua dependensi keluar Sebuah Disk Pool

## SYNTAX

```
Get-AzDiskPoolOutboundNetworkDependencyEndpoint -DiskPoolName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan titik akhir jaringan dari semua dependensi keluar Sebuah Disk Pool

## EXAMPLES

### Contoh 1: Titik akhir dependensi jaringan daftar untuk disk pool
```powershell
PS C:\>  Get-AzDiskPoolOutboundNetworkDependencyEndpoint -DiskPoolName disk-pool-1 -ResourceGroupName storagepool-rg-test | ft -Wrap

Category              Endpoint
--------              --------
Microsoft Event Hub   {{
                        "domainName": "evhns-rp-prod-eus2euap.servicebus.windows.net",
                        "endpointDetails": [
                          {
                            "port": 443
                          }
                        ]
                      }}
Microsoft Service Bus {{
                        "domainName": "sb-rp-prod-eus2euap.servicebus.windows.net",
                        "endpointDetails": [
                          {
                            "port": 443
                          }
                        ]
                      }}
Microsoft Storage     {{
                        "domainName": "strpprodeus2euap.blob.core.windows.net",
                        "endpointDetails": [
                          {
                            "port": 443
                          }
                        ]
                      }, {
                        "domainName": "stbsprodeus2euap.blob.core.windows.net",
                        "endpointDetails": [
                          {
                            "port": 443
                          }
                        ]
                      }}
Microsoft Apt Mirror  {{
                        "domainName": "azure.archive.ubuntu.com",
                        "endpointDetails": [
                          {
                            "port": 443
                          }
                        ]
                      }}
```

Perintah tersebut mencantumkan semua titik akhir dependensi jaringan keluar untuk sebuah disk pool.

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

### -DiskPoolName
Nama Disk Pool.

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

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210401Preview.IOutboundEnvironmentEndpoint

## CATATAN

ALIAS

## RELATED LINKS

