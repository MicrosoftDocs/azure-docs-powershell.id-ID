---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-aznetworkwatcherconnectionmonitortestconfigurationobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkWatcherConnectionMonitorTestConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkWatcherConnectionMonitorTestConfigurationObject.md
ms.openlocfilehash: a6529302b1be6fb4e436b5113789ca34db428225
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145674220"
---
# New-AzNetworkWatcherConnectionMonitorTestConfigurationObject

## SYNOPSIS
Membuat konfigurasi pengujian monitor koneksi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-aznetworkwatcherconnectionmonitortestconfigurationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name <String> -TestFrequencySec <Int32>
 -ProtocolConfiguration <PSNetworkWatcherConnectionMonitorProtocolConfiguration>
 [-SuccessThresholdChecksFailedPercent <Int32>] [-SuccessThresholdRoundTripTimeMs <Double>]
 [-PreferredIPVersion <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzNetworkWatcherConnectionMonitorTestConfigurationObject membuat konfigurasi pengujian monitor koneksi.

## EXAMPLES

### Contoh 1
```powershell
$httpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -HttpProtocol -Port 443 -Method GET -RequestHeader @{"Allow" = "GET"} -ValidStatusCodeRange 2xx, 300-308 -PreferHTTPS
$httpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name httpTC -TestFrequencySec 120 -ProtocolConfiguration $httpProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 30
```

```output
Name                  : httpTC
TestFrequencySec      : 120
PreferredIPVersion    :
ProtocolConfiguration : {
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
                        }
SuccessThreshold      : {
                          "ChecksFailedPercent": 20,
                          "RoundTripTimeMs": 30
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

### -Name
Nama konfigurasi pengujian monitor koneksi.

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

### -PreferredIPVersion
Versi IP pilihan untuk digunakan dalam evaluasi pengujian. Pemantau koneksi dapat memilih untuk menggunakan versi yang berbeda tergantung pada parameter lain.

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

### -ProtocolConfiguration
Parameter yang digunakan untuk melakukan evaluasi pengujian atas beberapa protokol.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorProtocolConfiguration
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuccessThresholdChecksFailedPercent
Persentase maksimum pemeriksaan gagal yang diizinkan untuk pengujian untuk dievaluasi sebagai berhasil.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuccessThresholdRoundTripTimeMs
Waktu pulang-pergi maksimum dalam milidetik yang diizinkan untuk pengujian untuk dievaluasi sebagai berhasil.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestFrequencySec
Frekuensi evaluasi pengujian, dalam hitungan detik.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TestFrequency

Required: True
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

### Microsoft.Azure.Commands.Network.Models.PSNetworkWatcherConnectionMonitorTestConfigurationObject

## NOTES

## RELATED LINKS
