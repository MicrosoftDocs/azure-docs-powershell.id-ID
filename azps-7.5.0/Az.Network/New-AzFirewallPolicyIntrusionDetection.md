---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azfirewallpolicyintrusiondetection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicyIntrusionDetection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicyIntrusionDetection.md
ms.openlocfilehash: 28aec5e4a41f6eb92bbcc74080e07ed869c2d4bc
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144223295"
---
# New-AzFirewallPolicyIntrusionDetection

## SYNOPSIS
Membuat Deteksi Penyusupan Kebijakan Azure Firewall baru untuk dikaitkan dengan Kebijakan Firewall

## SYNTAX

```
New-AzFirewallPolicyIntrusionDetection -Mode <String>
 [-SignatureOverride <PSAzureFirewallPolicyIntrusionDetectionSignatureOverride[]>]
 [-BypassTraffic <PSAzureFirewallPolicyIntrusionDetectionBypassTrafficSetting[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzFirewallPolicyIntrusionDetection** membuat Objek Deteksi Intrusi Kebijakan Azure Firewall.

## EXAMPLES

### Contoh 1: Membuat deteksi intrusi dengan mode
```powershell
New-AzFirewallPolicyIntrusionDetection -Mode "Alert"
```

Contoh ini membuat deteksi intrusi dengan mode Pemberitahuan (deteksi)

### Contoh 2: Membuat deteksi intrusi dengan penimpaan tanda tangan
```powershell
$signatureOverride = New-AzFirewallPolicyIntrusionDetectionSignatureOverride -Id "123456798" -Mode "Deny"
New-AzFirewallPolicyIntrusionDetection -Mode "Alert" -SignatureOverride $signatureOverride
```

Contoh ini membuat deteksi intrusi dengan penimpaan tanda tangan tertentu

### Contoh 3: Membuat kebijakan firewall dengan deteksi intrusi yang dikonfigurasi dengan pengaturan lalu lintas bypass
```powershell
$bypass = New-AzFirewallPolicyIntrusionDetectionBypassTraffic -Name "bypass-setting" -Protocol "TCP" -DestinationPort "80" -SourceAddress "10.0.0.0" -DestinationAddress "10.0.0.0"
$intrusionDetection = New-AzFirewallPolicyIntrusionDetection -Mode "Deny" -BypassTraffic $bypass
New-AzFirewallPolicy -Name fp1 -Location "westus2" -ResourceGroup TestRg -SkuTier "Premium" -IntrusionDetection $intrusionDetection
```

Contoh ini membuat deteksi intrusi dengan melewati pengaturan lalu lintas

## PARAMETERS

### -BypassTraffic
Daftar aturan untuk lalu lintas yang akan dilewati.

```yaml
Type: PSAzureFirewallPolicyIntrusionDetectionBypassTrafficSetting[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Status umum Deteksi Intrusi.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Off, Alert, Deny

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureOverride
Daftar status tanda tangan tertentu.

```yaml
Type: PSAzureFirewallPolicyIntrusionDetectionSignatureOverride[]
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
Type: SwitchParameter
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
Type: SwitchParameter
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

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicyIntrusionDetection

## NOTES

## RELATED LINKS
