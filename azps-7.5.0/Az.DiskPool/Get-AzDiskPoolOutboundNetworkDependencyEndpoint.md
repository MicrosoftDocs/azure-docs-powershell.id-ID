---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpooloutboundnetworkdependencyendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolOutboundNetworkDependencyEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolOutboundNetworkDependencyEndpoint.md
ms.openlocfilehash: eec8ada452ec67bf8e61174477592c8b49290a21
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145741114"
---
# Get-AzDiskPoolOutboundNetworkDependencyEndpoint

## SYNOPSIS
Mendapatkan titik akhir jaringan dari semua dependensi keluar dari Kumpulan Disk

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/get-azdiskpooloutboundnetworkdependencyendpoint) untuk informasi terbaru.

## SYNTAX

```
Get-AzDiskPoolOutboundNetworkDependencyEndpoint -DiskPoolName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan titik akhir jaringan dari semua dependensi keluar dari Kumpulan Disk

## EXAMPLES

### Contoh 1: Mencantumkan titik akhir dependensi jaringan untuk kumpulan Disk
```powershell
Get-AzDiskPoolOutboundNetworkDependencyEndpoint -DiskPoolName disk-pool-1 -ResourceGroupName storagepool-rg-test | Format-Table -Wrap
```

```output
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

Perintah mencantumkan semua titik akhir dependensi jaringan keluar untuk kumpulan Disk.

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
Nama Kumpulan Disk.

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
Nama ini tidak peka huruf besar/kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IOutboundEnvironmentEndpoint

## NOTES

ALIAS

## RELATED LINKS

