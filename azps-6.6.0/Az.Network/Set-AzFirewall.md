---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 40E56EC1-3327-4DFF-8262-E2EEBB5E4447
online version: https://docs.microsoft.com/powershell/module/az.network/set-azfirewall
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzFirewall.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzFirewall.md
ms.openlocfilehash: dfbd9e8fb775fd64f0f626a53ea9371ee5bf5974
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136335519"
---
# Set-AzFirewall

## SYNOPSIS
Menyimpan Firewall yang dimodifikasi.

## SYNTAX

```
Set-AzFirewall -AzureFirewall <PSAzureFirewall> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzFirewall** memperbarui Azure Firewall.

## EXAMPLES

### 1: Perbarui prioritas kumpulan aturan aplikasi Firewall
```
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$ruleCollection = $azFw.GetApplicationRuleCollectionByName("ruleCollectionName")
$ruleCollection.Priority = 101
Set-AzFirewall -AzureFirewall $azFw
```

Contoh ini memperbarui prioritas kumpulan aturan azure firewall yang sudah ada.
Dengan menganggap Azure Firewall "AzureFirewall" dalam grup sumber daya "rg" berisi kumpulan aturan aplikasi bernama "ruleCollectionName", perintah di atas akan mengubah prioritas kumpulan aturan tersebut dan memperbarui Azure Firewall sesudahnya. Tanpa perintah Set-AzFirewall, semua operasi yang dilakukan pada objek $azFw lokal tidak akan terlihat di server.

### 2: Buat Azure Firewall dan atur kumpulan aturan aplikasi nanti
```
$azFw = New-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg" -VirtualNetworkName "vnet-name" -PublicIpName "pip-name"

$rule = New-AzFirewallApplicationRule -Name R1 -Protocol "http:80","https:443" -TargetFqdn "*google.com", "*microsoft.com" -SourceAddress "10.0.0.0"
$RuleCollection = New-AzFirewallApplicationRuleCollection -Name RC1 -Priority 100 -Rule $rule -ActionType "Allow"
$azFw.ApplicationRuleCollections = $RuleCollection

$azFw | Set-AzFirewall
```

Dalam contoh ini, Firewall dibuat terlebih dahulu tanpa kumpulan aturan aplikasi apa pun. Setelah itu, Aturan Aplikasi dan Kumpulan Aturan Aplikasi dibuat, kemudian objek Firewall dimodifikasi dalam memori, tanpa memengaruhi konfigurasi sebenarnya di awan. Agar perubahan terlihat di awan, Anda Set-AzFirewall harus dipanggil.

### 3: Mode operasi Update Threat Intel dari Azure Firewall
```
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.ThreatIntelMode = "Deny"
Set-AzFirewall -Firewall $azFw
```

Contoh ini memperbarui mode operasi Threat Intel dari Azure Firewall "AzureFirewall" di grup sumber daya "rg".
Tanpa perintah Set-AzFirewall, semua operasi yang dilakukan pada objek $azFw lokal tidak akan terlihat di server.

### 4: Deallocate dan alokasikan Firewall
```
$firewall=Get-AzFirewall -ResourceGroupName rgName -Name azFw
$firewall.Deallocate()
$firewall | Set-AzFirewall

$vnet = Get-AzVirtualNetwork -ResourceGroupName rgName -Name anotherVNetName
$pip = Get-AzPublicIpAddress -ResourceGroupName rgName -Name publicIpName
$firewall.Allocate($vnet, $pip)
$firewall | Set-AzFirewall
```
Contoh ini mengambil Firewall, deallocates firewall, dan menyimpannya. Perintah Deallocate menghapus layanan yang berjalan namun mempertahankan konfigurasi firewall. Agar perubahan terlihat di awan, Anda Set-AzFirewall harus dipanggil.
Jika pengguna ingin memulai layanan lagi, metode Alokasikan akan dipanggil pada firewall.
VNet dan IP Publik baru harus berada dalam grup sumber daya yang sama seperti Firewall. Sekali lagi, agar perubahan terlihat di awan, Set-AzFirewall harus dipanggil.

### 5: Alokasikan dengan alamat IP publik manajemen untuk skenario skenario paksa
```
$vnet = Get-AzVirtualNetwork -ResourceGroupName rgName -Name anotherVNetName
$pip = Get-AzPublicIpAddress -ResourceGroupName rgName -Name publicIpName
$mgmtPip = Get-AzPublicIpAddress -ResourceGroupName rgName -Name MgmtPublicIpName
$firewall.Allocate($vnet, $pip, $mgmtPip)
$firewall | Set-AzFirewall
```
Contoh ini mengalokasikan firewall dengan alamat IP publik manajemen dan subnet untuk skenario sambungan paksa. VNet harus berisi subnet yang disebut "AzureFirewallManagementSubnet".

### 6: Menambahkan alamat IP Publik ke Azure Firewall
```
$pip = New-AzPublicIpAddress -Name "azFwPublicIp1" -ResourceGroupName "rg" -Sku "Standard" -Location "centralus" -AllocationMethod Static
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.AddPublicIpAddress($pip)

$azFw | Set-AzFirewall
```

Dalam contoh ini, Alamat IP Publik "azFwPublicIp1" yang dilampirkan ke Firewall.

### 7: Hapus alamat IP Publik dari Azure Firewall
```
$pip = Get-AzPublicIpAddress -Name "azFwPublicIp1" -ResourceGroupName "rg"
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.RemovePublicIpAddress($pip)

$azFw | Set-AzFirewall
```

Dalam contoh ini, Alamat IP Publik "azFwPublicIp1" yang dilepas dari Firewall.

### 8: Mengubah alamat IP publik manajemen di Azure Firewall
```
$newMgmtPip = New-AzPublicIpAddress -Name "azFwMgmtPublicIp2" -ResourceGroupName "rg" -Sku "Standard" -Location "centralus" -AllocationMethod Static
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.ManagementIpConfiguration.PublicIpAddress = $newMgmtPip

$azFw | Set-AzFirewall
```

Dalam contoh ini, alamat IP publik manajemen firewall akan diubah menjadi "AzFwMgmtPublicIp2"

### 9: Tambahkan konfigurasi DNS ke Azure Firewall
```
$dnsServers = @("10.10.10.1", "20.20.20.2")
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.DNSEnableProxy = $true
$azFw.DNSServer = $dnsServers

$azFw | Set-AzFirewall
```

Dalam contoh ini, konfigurasi Proksi DNS dan Server DNS dilampirkan ke Firewall.

### 10: Perbarui tujuan aturan yang sudah ada dalam kumpulan aturan aplikasi Firewall
```
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$ruleCollection = $azFw.GetNetworkRuleCollectionByName("ruleCollectionName")
$rule=$ruleCollection.GetRuleByName("ruleName")
$rule.DestinationAddresses = "10.10.10.10"
Set-AzFirewall -AzureFirewall $azFw
```

Contoh ini memperbarui tujuan aturan yang sudah ada dalam kumpulan aturan Azure Firewall. Ini memungkinkan Anda untuk memperbarui aturan secara otomatis saat alamat IP berubah secara dinamis.

### 11: Perbolehkan FTP Aktif di Azure Firewall
```
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.AllowActiveFTP = $true

$azFw | Set-AzFirewall
```

Dalam contoh ini, FTP Aktif diperbolehkan di Firewall.

### 12: Deallocate dan alokasikan Firewall dari Virtual Hub
```
$firewall=Get-AzFirewall -ResourceGroupName rgName -Name azFw
$firewall.Deallocate()
$firewall | Set-AzFirewall

$Hub = Get-AzVirtualHub -ResourceGroupName "testRG" -Name "westushub"
$firewall.Allocate($Hub.Id)
$firewall | Set-AzFirewall
```
Contoh ini mengambil Firewall Hub, deallocates firewall hub, dan menyimpannya. Perintah Deallocate menghapus referensi ke hub virtual tetapi mempertahankan konfigurasi firewall. Agar perubahan terlihat di awan, Anda Set-AzFirewall harus dipanggil.
Metode Alokasikan menetapkan referensi hub virtual ke firewall. Sekali lagi, agar perubahan terlihat di awan, Set-AzFirewall harus dipanggil.

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

### -AzureFirewall
The AzureFirewall

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSAzureFirewall
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## CATATAN

## RELATED LINKS

[Get-AzFirewall](./Get-AzFirewall.md)

[New-AzFirewall](./New-AzFirewall.md)

[Remove-AzFirewall](./Remove-AzFirewall.md)
