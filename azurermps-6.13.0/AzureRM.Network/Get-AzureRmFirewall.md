---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 91D58F60-F22A-454A-B04C-E5AEF33E9D06
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermfirewall
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmFirewall.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmFirewall.md
ms.openlocfilehash: cdaa9689919d2e307434d888b435dad9d29e105e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420696"
---
# Get-AzureRmFirewall

## SYNOPSIS
Mendapatkan Azure Firewall.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmFirewall [-Name <String>] [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmFirewall** mendapatkan satu atau beberapa Firewall dalam grup sumber daya.

## EXAMPLES

### 1: Ambil semua Firewall di grup sumber daya
```
Get-AzureRmFirewall -ResourceGroupName rgName
```

Contoh ini mengambil semua Firewall dalam grup sumber daya "rgName".

### 2: Ambil Firewall dengan nama
```
Get-AzureRmFirewall -ResourceGroupName rgName -Name azFw
```

Contoh ini mengambil Firewall yang bernama "azFw" di grup sumber daya "rgName".

### 3: Ambil firewall lalu tambahkan kumpulan aturan aplikasi ke Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$appRule = New-AzureRmFirewallApplicationRule -Name R1 -Protocol "http:80","https:443" -TargetFqdn "*google.com", "*microsoft.com" -SourceAddress "10.0.0.0"
$appRuleCollection = New-AzureRmFirewallApplicationRuleCollection -Name "MyAppRuleCollection" -Priority 100 -Rule $appRule -ActionType "Allow"
$azFw.AddApplicationRuleCollection($appRuleCollection)
```

Contoh ini mengambil firewall, lalu menambahkan kumpulan aturan aplikasi ke firewall dengan metode panggilan AddApplicationRuleCollection.

### 4: Ambil firewall lalu tambahkan kumpulan aturan jaringan ke Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$netRule = New-AzureRmFirewallNetworkRule -Name "all-udp-traffic" -Description "Rule for all UDP traffic" -Protocol "Udp" -SourceAddress "*" -DestinationAddress "*" -DestinationPort "*"
$netRuleCollection = New-AzureRmFirewallNetworkRuleCollection -Name "MyNetworkRuleCollection" -Priority 100 -Rule $netRule -ActionType "Allow"
$azFw.AddNetworkRuleCollection($netRuleCollection)
```

Contoh ini mengambil firewall, lalu menambahkan kumpulan aturan jaringan ke firewall dengan metode panggilan AddNetworkRuleCollection.

### 5: Ambil firewall lalu ambil kumpulan aturan aplikasi menurut nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$getAppRc=$azFw.GetApplicationRuleCollectionByName("MyAppRuleCollection")
```

Contoh ini mengambil firewall lalu mendapatkan kumpulan aturan menurut nama, metode panggilan GetApplicationRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode GetApplicationRuleCollectionByName adalah case-insensitive.

### 6: Ambil firewall lalu ambil kumpulan aturan jaringan menurut nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$getNetRc=$azFw.GetNetworkRuleCollectionByName("MyNetworkRuleCollection")
```

Contoh ini mengambil firewall lalu mendapatkan kumpulan aturan menurut nama, metode panggilan GetNetworkRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode GetNetworkRuleCollectionByName adalah case-insensitive.

### 7: Ambil firewall lalu hapus kumpulan aturan aplikasi menurut nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$azFw.RemoveApplicationRuleCollectionByName("MyAppRuleCollection")
```

Contoh ini mengambil firewall lalu menghapus kumpulan aturan menurut nama, metode panggilan RemoveApplicationRuleCollectionByName di objek firewall. Nama kumpulan aturan untuk metode RemoveApplicationRuleCollectionByName adalah case-insensitive.

### 8: Ambil firewall lalu hapus kumpulan aturan jaringan menurut nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$azFw.RemoveNetworkRuleCollectionByName("MyNetworkRuleCollection")
```

Contoh ini mengambil firewall lalu menghapus kumpulan aturan menurut nama, metode panggilan RemoveNetworkRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode RemoveNetworkRuleCollectionByName adalah case-insensitive.

### 9: Ambil firewall lalu alokasikan firewall
```
$vnet=Get-AzureRmVirtualNetwork -Name "vnet" -ResourceGroupName "rgName"
$publicIp=Get-AzureRmPublicIpAddress -Name "firewallpip" -ResourceGroupName "rgName"
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$azFw.Allocate($vnet, $publicIp)
```

Contoh ini mengambil firewall dan panggilan Mengalokasikan di firewall untuk memulai layanan firewall menggunakan konfigurasi (aplikasi dan kumpulan aturan jaringan) yang terkait dengan firewall.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama Firewall yang akan dapatkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang dimiliki Firewall.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## CATATAN

## RELATED LINKS

[New-AzureRmFirewall](./New-AzureRmFirewall.md)

[Remove-AzureRmFirewall](./Remove-AzureRmFirewall.md)

[Set-AzureRmFirewall](./Set-AzureRmFirewall.md)
