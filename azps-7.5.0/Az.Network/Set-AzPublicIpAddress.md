---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: EC798838-1850-4E88-B17F-D2F00F2D4EE9
online version: https://docs.microsoft.com/powershell/module/az.network/set-azpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzPublicIpAddress.md
ms.openlocfilehash: d84df69fbe2c0ec4d76efd0dea08b25c90bf6a10
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145665372"
---
# Set-AzPublicIpAddress

## SYNOPSIS
Memperbarui alamat IP publik.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azpublicipaddress) untuk informasi terbaru.

## SYNTAX

```
Set-AzPublicIpAddress -PublicIpAddress <PSPublicIpAddress> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzPublicIpAddress** memperbarui alamat IP publik.

## EXAMPLES

### 1: Mengubah metode alokasi alamat IP publik
```powershell
$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

$publicIp.PublicIpAllocationMethod = "Static"
    
Set-AzPublicIpAddress -PublicIpAddress $publicIp

Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

 Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName di grup sumber daya $rgName.
Perintah kedua mengatur metode alokasi objek alamat IP publik ke "Statis".
Set-AzPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui, dan memodifikasi metode alokasi menjadi 'Statis'. Alamat IP publik segera dialokasikan.

### 2: Menambahkan label domain DNS dari alamat IP publik
```powershell
$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

$publicIp.DnsSettings = @{"DomainNameLabel" = "newdnsprefix"}
    
Set-AzPublicIpAddress -PublicIpAddress $publicIp

$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName di grup sumber daya $rgName.
Perintah kedua mengatur properti DomainNameLabel ke awalan dns yang diperlukan.
Set-AzPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui. DomainNameLabel & Fqdn dimodifikasi seperti yang diharapkan.
    
### 3: Mengubah label domain DNS dari alamat IP publik
```powershell
$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

$publicIp.DnsSettings.DomainNameLabel = "newdnsprefix"
    
Set-AzPublicIpAddress -PublicIpAddress $publicIp

$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName di grup sumber daya $rgName.
Perintah kedua mengatur properti DomainNameLabel ke awalan dns yang diperlukan.
Set-AzPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui. DomainNameLabel & Fqdn dimodifikasi seperti yang diharapkan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -PublicIpAddress
Menentukan objek alamat IP publik yang mewakili status tempat alamat IP publik harus diatur.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## NOTES

## RELATED LINKS

[Dapatkan-AzPublicIpAddress](./Get-AzPublicIpAddress.md)

[New-AzPublicIpAddress](./New-AzPublicIpAddress.md)

[Remove-AzPublicIpAddress](./Remove-AzPublicIpAddress.md)


