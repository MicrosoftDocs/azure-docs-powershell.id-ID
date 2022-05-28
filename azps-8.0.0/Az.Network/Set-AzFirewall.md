---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 40E56EC1-3327-4DFF-8262-E2EEBB5E4447
online version: https://docs.microsoft.com/powershell/module/az.network/set-azfirewall
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzFirewall.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzFirewall.md
ms.openlocfilehash: d9f54438f91c2679196cd4b4052a9f547834ffb9
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500395"
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

### 1: Memperbarui prioritas kumpulan aturan aplikasi Firewall
```powershell
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$ruleCollection = $azFw.GetApplicationRuleCollectionByName("ruleCollectionName")
$ruleCollection.Priority = 101
Set-AzFirewall -AzureFirewall $azFw
```

Contoh ini memperbarui prioritas kumpulan aturan yang ada dari Azure Firewall.
Dengan asumsi Azure Firewall "AzureFirewall" dalam grup sumber daya "rg" berisi kumpulan aturan aplikasi bernama "ruleCollectionName", perintah di atas akan mengubah prioritas kumpulan aturan tersebut dan memperbarui Azure Firewall setelahnya. Tanpa perintah Set-AzFirewall, semua operasi yang dilakukan pada objek $azFw lokal tidak tercermin di server.

### 2: Buat Azure Firewall dan atur kumpulan aturan aplikasi nanti
```powershell
$azFw = New-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg" -VirtualNetworkName "vnet-name" -PublicIpName "pip-name"

$rule = New-AzFirewallApplicationRule -Name R1 -Protocol "http:80","https:443" -TargetFqdn "*google.com", "*microsoft.com" -SourceAddress "10.0.0.0"
$RuleCollection = New-AzFirewallApplicationRuleCollection -Name RC1 -Priority 100 -Rule $rule -ActionType "Allow"
$azFw.ApplicationRuleCollections = $RuleCollection

$azFw | Set-AzFirewall
```

Dalam contoh ini, Firewall dibuat terlebih dahulu tanpa koleksi aturan aplikasi apa pun. Setelah itu Aturan Aplikasi dan Kumpulan Aturan Aplikasi dibuat, maka objek Firewall dimodifikasi dalam memori, tanpa memengaruhi konfigurasi nyata di cloud. Agar perubahan tercermin di cloud, Set-AzFirewall harus dipanggil.

### 3: Memperbarui mode operasi Intel Ancaman Azure Firewall
```powershell
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.ThreatIntelMode = "Deny"
Set-AzFirewall -AzureFirewall $azFw
```

Contoh ini memperbarui mode operasi Intel Ancaman Azure Firewall "AzureFirewall" dalam grup sumber daya "rg".
Tanpa perintah Set-AzFirewall, semua operasi yang dilakukan pada objek $azFw lokal tidak tercermin di server.

### 4: Batalkan alokasi dan alokasikan Firewall
```powershell
$firewall=Get-AzFirewall -ResourceGroupName rgName -Name azFw
$firewall.Deallocate()
$firewall | Set-AzFirewall

$vnet = Get-AzVirtualNetwork -ResourceGroupName rgName -Name anotherVNetName
$pip = Get-AzPublicIpAddress -ResourceGroupName rgName -Name publicIpName
$firewall.Allocate($vnet, $pip)
$firewall | Set-AzFirewall
```
Contoh ini mengambil Firewall, membatalkan alokasi firewall, dan menyimpannya. Perintah Batalkan alokasi menghapus layanan yang sedang berjalan tetapi mempertahankan konfigurasi firewall. Agar perubahan tercermin di cloud, Set-AzFirewall harus dipanggil.
Jika pengguna ingin memulai layanan lagi, metode Alokasikan harus dipanggil pada firewall.
VNet dan IP Publik baru harus berada dalam grup sumber daya yang sama dengan Firewall. Sekali lagi, agar perubahan tercermin di cloud, Set-AzFirewall harus dipanggil.

### 5: Alokasikan dengan alamat IP publik manajemen untuk skenario penerowongan paksa
```powershell
$vnet = Get-AzVirtualNetwork -ResourceGroupName rgName -Name anotherVNetName
$pip = Get-AzPublicIpAddress -ResourceGroupName rgName -Name publicIpName
$mgmtPip = Get-AzPublicIpAddress -ResourceGroupName rgName -Name MgmtPublicIpName
$firewall.Allocate($vnet, $pip, $mgmtPip)
$firewall | Set-AzFirewall
```
Contoh ini mengalokasikan firewall dengan alamat IP publik manajemen dan subnet untuk skenario penerowongan paksa. VNet harus berisi subnet yang disebut "AzureFirewallManagementSubnet".

### 6: Menambahkan alamat IP Publik ke Azure Firewall
```powershell
$pip = New-AzPublicIpAddress -Name "azFwPublicIp1" -ResourceGroupName "rg" -Sku "Standard" -Location "centralus" -AllocationMethod Static
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.AddPublicIpAddress($pip)

$azFw | Set-AzFirewall
```

Dalam contoh ini, Alamat IP Publik "azFwPublicIp1" seperti yang dilampirkan ke Firewall.

### 7: Menghapus alamat IP Publik dari Azure Firewall
```powershell
$pip = Get-AzPublicIpAddress -Name "azFwPublicIp1" -ResourceGroupName "rg"
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.RemovePublicIpAddress($pip)

$azFw | Set-AzFirewall
```

Dalam contoh ini, Alamat IP Publik "azFwPublicIp1" sebagaimana dicopot dari Firewall.

### 8: Mengubah alamat IP publik manajemen pada Azure Firewall
```powershell
$newMgmtPip = New-AzPublicIpAddress -Name "azFwMgmtPublicIp2" -ResourceGroupName "rg" -Sku "Standard" -Location "centralus" -AllocationMethod Static
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.ManagementIpConfiguration.PublicIpAddress = $newMgmtPip

$azFw | Set-AzFirewall
```

Dalam contoh ini, alamat IP publik manajemen firewall akan diubah menjadi "AzFwMgmtPublicIp2"

### 9: Menambahkan konfigurasi DNS ke Azure Firewall
```powershell
$dnsServers = @("10.10.10.1", "20.20.20.2")
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.DNSEnableProxy = $true
$azFw.DNSServer = $dnsServers

$azFw | Set-AzFirewall
```

Dalam contoh ini, konfigurasi Proksi DNS dan Server DNS dilampirkan ke Firewall.

### 10: Memperbarui tujuan aturan yang ada dalam kumpulan aturan aplikasi Firewall
```powershell
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$ruleCollection = $azFw.GetNetworkRuleCollectionByName("ruleCollectionName")
$rule=$ruleCollection.GetRuleByName("ruleName")
$rule.DestinationAddresses = "10.10.10.10"
Set-AzFirewall -AzureFirewall $azFw
```

Contoh ini memperbarui tujuan aturan yang ada dalam kumpulan aturan Azure Firewall. Ini memungkinkan Anda memperbarui aturan secara otomatis saat alamat IP berubah secara dinamis.

### 11: Izinkan FTP Aktif pada Azure Firewall
```powershell
$azFw = Get-AzFirewall -Name "AzureFirewall" -ResourceGroupName "rg"
$azFw.AllowActiveFTP = $true

$azFw | Set-AzFirewall
```

Dalam contoh ini, FTP Aktif diizinkan pada Firewall.

### 12: Batalkan alokasi dan alokasikan Firewall dari Hub Virtual
```powershell
$firewall=Get-AzFirewall -ResourceGroupName rgName -Name azFw
$firewall.Deallocate()
$firewall | Set-AzFirewall

$Hub = Get-AzVirtualHub -ResourceGroupName "testRG" -Name "westushub"
$firewall.Allocate($Hub.Id)
$firewall | Set-AzFirewall
```
Contoh ini mengambil Firewall Hub, membatalkan alokasi firewall hub, dan menyimpannya. Perintah Batalkan Alokasi menghapus referensi ke hub virtual tetapi mempertahankan konfigurasi firewall. Agar perubahan tercermin di cloud, Set-AzFirewall harus dipanggil.
Metode Alokasikan menetapkan referensi hub virtual ke firewall. Sekali lagi, agar perubahan tercermin di cloud, Set-AzFirewall harus dipanggil.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## NOTES

## RELATED LINKS

[Get-AzFirewall](./Get-AzFirewall.md)

[New-AzFirewall](./New-AzFirewall.md)

[Remove-AzFirewall](./Remove-AzFirewall.md)
