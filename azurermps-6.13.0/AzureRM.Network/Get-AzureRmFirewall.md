---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 91D58F60-F22A-454A-B04C-E5AEF33E9D06
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermfirewall
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmFirewall.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmFirewall.md
ms.openlocfilehash: cdaa9689919d2e307434d888b435dad9d29e105e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141883646"
---
# Get-AzureRmFirewall

## SYNOPSIS
Dapatkan Azure Firewall.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmFirewall [-Name <String>] [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmFirewall** mendapatkan satu atau beberapa Firewall dalam grup sumber daya.

## EXAMPLES

### 1: Mengambil semua Firewall dalam grup sumber daya
```
Get-AzureRmFirewall -ResourceGroupName rgName
```

Contoh ini mengambil semua Firewall dalam grup sumber daya "rgName".

### 2: Mengambil Firewall berdasarkan nama
```
Get-AzureRmFirewall -ResourceGroupName rgName -Name azFw
```

Contoh ini mengambil Firewall bernama "azFw" dalam grup sumber daya "rgName".

### 3: Mengambil firewall lalu menambahkan kumpulan aturan aplikasi ke Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$appRule = New-AzureRmFirewallApplicationRule -Name R1 -Protocol "http:80","https:443" -TargetFqdn "*google.com", "*microsoft.com" -SourceAddress "10.0.0.0"
$appRuleCollection = New-AzureRmFirewallApplicationRuleCollection -Name "MyAppRuleCollection" -Priority 100 -Rule $appRule -ActionType "Allow"
$azFw.AddApplicationRuleCollection($appRuleCollection)
```

Contoh ini mengambil firewall, lalu menambahkan kumpulan aturan aplikasi ke firewall dengan memanggil metode AddApplicationRuleCollection.

### 4: Mengambil firewall lalu menambahkan kumpulan aturan jaringan ke Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$netRule = New-AzureRmFirewallNetworkRule -Name "all-udp-traffic" -Description "Rule for all UDP traffic" -Protocol "Udp" -SourceAddress "*" -DestinationAddress "*" -DestinationPort "*"
$netRuleCollection = New-AzureRmFirewallNetworkRuleCollection -Name "MyNetworkRuleCollection" -Priority 100 -Rule $netRule -ActionType "Allow"
$azFw.AddNetworkRuleCollection($netRuleCollection)
```

Contoh ini mengambil firewall, lalu menambahkan kumpulan aturan jaringan ke firewall dengan metode panggilan AddNetworkRuleCollection.

### 5: Mengambil firewall lalu mengambil kumpulan aturan aplikasi berdasarkan nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$getAppRc=$azFw.GetApplicationRuleCollectionByName("MyAppRuleCollection")
```

Contoh ini mengambil firewall lalu mendapatkan kumpulan aturan berdasarkan nama, metode panggilan GetApplicationRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode GetApplicationRuleCollectionByName tidak peka huruf besar kecil.

### 6: Mengambil firewall lalu mengambil kumpulan aturan jaringan berdasarkan nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$getNetRc=$azFw.GetNetworkRuleCollectionByName("MyNetworkRuleCollection")
```

Contoh ini mengambil firewall lalu mendapatkan kumpulan aturan berdasarkan nama, metode panggilan GetNetworkRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode GetNetworkRuleCollectionByName tidak peka huruf besar kecil.

### 7: Mengambil firewall lalu menghapus kumpulan aturan aplikasi berdasarkan nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$azFw.RemoveApplicationRuleCollectionByName("MyAppRuleCollection")
```

Contoh ini mengambil firewall lalu menghapus kumpulan aturan berdasarkan nama, metode panggilan RemoveApplicationRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode RemoveApplicationRuleCollectionByName tidak peka huruf besar kecil.

### 8: Mengambil firewall lalu menghapus kumpulan aturan jaringan berdasarkan nama dari Firewall
```
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$azFw.RemoveNetworkRuleCollectionByName("MyNetworkRuleCollection")
```

Contoh ini mengambil firewall lalu menghapus kumpulan aturan berdasarkan nama, metode panggilan RemoveNetworkRuleCollectionByName pada objek firewall. Nama kumpulan aturan untuk metode RemoveNetworkRuleCollectionByName tidak peka huruf besar kecil.

### 9: Mengambil firewall lalu mengalokasikan firewall
```
$vnet=Get-AzureRmVirtualNetwork -Name "vnet" -ResourceGroupName "rgName"
$publicIp=Get-AzureRmPublicIpAddress -Name "firewallpip" -ResourceGroupName "rgName"
$azFw=Get-AzureRmFirewall -Name "azFw" -ResourceGroupName "rgName"
$azFw.Allocate($vnet, $publicIp)
```

Contoh ini mengambil firewall dan panggilan Alokasikan di firewall untuk memulai layanan firewall menggunakan konfigurasi (kumpulan aturan aplikasi dan jaringan) yang terkait dengan firewall.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan nama Firewall yang didapatkan cmdlet ini.

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
Menentukan nama grup sumber daya tempat Firewall berada.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## CATATAN

## RELATED LINKS

[New-AzureRmFirewall](./New-AzureRmFirewall.md)

[Hapus-AzureRmFirewall](./Remove-AzureRmFirewall.md)

[Set-AzureRmFirewall](./Set-AzureRmFirewall.md)
