---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: EC798838-1850-4E88-B17F-D2F00F2D4EE9
online version: https://docs.microsoft.com/powershell/module/az.network/set-azpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzPublicIpAddress.md
ms.openlocfilehash: 5305fe436cf8a1ac04a38bebe2a1f15c82e84413
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143312741"
---
# Set-AzPublicIpAddress

## SYNOPSIS
Memperbarui alamat IP publik.

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

 Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam $rgName grup sumber daya.
Perintah kedua mengatur metode alokasi objek alamat IP publik menjadi "Statis".
Set-AzPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui, dan mengubah metode alokasi menjadi 'Statis'. Alamat IP publik langsung dialokasikan.

### 2: Menambahkan label domain DNS dari alamat IP publik
```powershell
$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

$publicIp.DnsSettings = @{"DomainNameLabel" = "newdnsprefix"}
    
Set-AzPublicIpAddress -PublicIpAddress $publicIp

$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam $rgName grup sumber daya.
Perintah kedua mengatur properti DomainNameLabel ke prefiks dns yang diperlukan.
Set-AzPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui. DomainNameLabel & Fqdn diubah seperti yang diharapkan.
    
### 3: Mengubah label domain DNS dari alamat IP publik
```powershell
$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

$publicIp.DnsSettings.DomainNameLabel = "newdnsprefix"
    
Set-AzPublicIpAddress -PublicIpAddress $publicIp

$publicIp = Get-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam $rgName grup sumber daya.
Perintah kedua mengatur properti DomainNameLabel ke prefiks dns yang diperlukan.
Set-AzPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui. DomainNameLabel & Fqdn diubah seperti yang diharapkan.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Menentukan objek alamat IP publik yang mewakili status yang harus diatur alamat IP publiknya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## NOTES

## RELATED LINKS

[Get-AzPublicIpAddress](./Get-AzPublicIpAddress.md)

[New-AzPublicIpAddress](./New-AzPublicIpAddress.md)

[Remove-AzPublicIpAddress](./Remove-AzPublicIpAddress.md)


