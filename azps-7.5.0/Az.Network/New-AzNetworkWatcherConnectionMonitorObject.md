---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-aznetworkwatcherconnectionmonitorobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkWatcherConnectionMonitorObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkWatcherConnectionMonitorObject.md
ms.openlocfilehash: 573b33cf804b1ecc3f788b177f1da13bb1d1a000
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145674346"
---
# New-AzNetworkWatcherConnectionMonitorObject

## SYNOPSIS
Buat objek V2 monitor koneksi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-aznetworkwatcherconnectionmonitorobject) untuk informasi terbaru.

## SYNTAX

### SetByResource
```
New-AzNetworkWatcherConnectionMonitorObject -NetworkWatcher <PSNetworkWatcher> -Name <String>
 [-TestGroup <PSNetworkWatcherConnectionMonitorTestGroupObject[]>]
 [-Output <PSNetworkWatcherConnectionMonitorOutputObject[]>] [-Note <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByName
```
New-AzNetworkWatcherConnectionMonitorObject -NetworkWatcherName <String> -ResourceGroupName <String>
 -Name <String> [-TestGroup <PSNetworkWatcherConnectionMonitorTestGroupObject[]>]
 [-Output <PSNetworkWatcherConnectionMonitorOutputObject[]>] [-Note <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByLocation
```
New-AzNetworkWatcherConnectionMonitorObject -Location <String> -Name <String>
 [-TestGroup <PSNetworkWatcherConnectionMonitorTestGroupObject[]>]
 [-Output <PSNetworkWatcherConnectionMonitorOutputObject[]>] [-Note <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzNetworkWatcherConnectionMonitorObject membuat objek V2 monitor koneksi.

## EXAMPLES

### Contoh 1
```powershell
$cmtest = New-AzNetworkWatcherConnectionMonitorObject -Location westcentralus -Name cmV2test -TestGroup $testGroup1, $testGroup2 -Tag @{"name" = "value"}
$cmtest
```

```output
NetworkWatcherName : NetworkWatcher_westcentralus
ResourceGroupName  : NetworkWatcherRG
Name               : cmV2test
TestGroups         : [
                       {
                         "Name": "testGroup1",
                         "Disable": false,
                         "TestConfigurations": [
                           {
                             "Name": "tcpTC",
                             "TestFrequencySec": 60,
                             "ProtocolConfiguration": {
                               "Port": 80,
                               "DisableTraceRoute": false
                             },
                             "SuccessThreshold": {
                               "ChecksFailedPercent": 20,
                               "RoundTripTimeMs": 5
                             }
                           },
                           {
                             "Name": "icmpTC",
                             "TestFrequencySec": 30,
                             "PreferredIPVersion": "IPv4",
                             "ProtocolConfiguration": {
                               "DisableTraceRoute": true
                             }
                           }
                         ],
                         "Sources": [
                           {
                             "Name": "MultiTierApp0(IrinaRGWestcentralus)",
                             "ResourceId": "/subscriptions/00000000-0000-0000-0000-00000000/resourceGroups/RGW
                     estcentralus/providers/Microsoft.Compute/virtualMachines/MultiTierApp0"
                           },
                           {
                             "Name": "NPM-CommonEUS(er-lab)",
                             "ResourceId": "/subscriptions/00000000-0000-0000-0000-00000000/resourceGroups/er-lab/p
                     roviders/Microsoft.OperationalInsights/workspaces/NPM-CommonEUS",
                             "Filter": {
                               "Type": "Include",
                               "Items": [
                                 {
                                   "Type": "AgentAddress",
                                   "Address": "SEA-Cust50-VM01"
                                 },
                                 {
                                   "Type": "AgentAddress",
                                   "Address": "WIN-P0HGNDO2S1B"
                                 }
                               ]
                             }
                           }
                         ],
                         "Destinations": [
                           {
                             "Name": "bingEndpoint",
                             "Address": "bing.com"
                           },
                           {
                             "Name": "googleEndpoint",
                             "Address": "google.com"
                           }
                         ]
                       },
                       {
                         "Name": "testGroup2",
                         "Disable": false,
                         "TestConfigurations": [
                           {
                             "Name": "httpTC",
                             "TestFrequencySec": 120,
                             "ProtocolConfiguration": {
                               "Port": 443,
                               "Method": "GET",
                               "RequestHeaders": [
                                 {
                                   "Name": "Allow",
                                   "Value": "GET"
                                 }
                               ],
                               "ValidStatusCodeRanges": [
                                 "2xx",
                                 "300-308"
                               ],
                               "PreferHTTPS": true
                             },
                             "SuccessThreshold": {
                               "ChecksFailedPercent": 20,
                               "RoundTripTimeMs": 30
                             }
                           }
                         ],
                         "Sources": [
                           {
                             "Name": "MultiTierApp0(IrinaRGWestcentralus)",
                             "ResourceId": "/subscriptions/00000000-0000-0000-0000-00000000/resourceGroups/IrinaRGW
                     estcentralus/providers/Microsoft.Compute/virtualMachines/MultiTierApp0"
                           }
                         ],
                         "Destinations": [
                           {
                             "Name": "googleEndpoint",
                             "Address": "google.com"
                           }
                         ]
                       }
                     ]
Outputs            : null
Notes              :
Tags               : {
                       "name": "value"
                     }
```      
   

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

### -Lokasi
Lokasi pengamat jaringan.

```yaml
Type: System.String
Parameter Sets: SetByLocation
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama pemantau koneksi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ConnectionMonitorName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkWatcher
Sumber daya network watcher.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkWatcher
Parameter Sets: SetByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkWatcherName
Nama network watcher.

```yaml
Type: System.String
Parameter Sets: SetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Catatan
Catatan yang terkait dengan pemantau koneksi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Output
Menjelaskan tujuan output monitor koneksi.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorOutputObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya network watcher.

```yaml
Type: System.String
Parameter Sets: SetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Hashtable yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TestGroup
Daftar grup pengujian.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorTestGroupObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorObject

## NOTES

## RELATED LINKS
