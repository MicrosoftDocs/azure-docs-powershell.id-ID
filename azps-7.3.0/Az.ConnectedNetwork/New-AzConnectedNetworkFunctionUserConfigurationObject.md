---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkFunctionUserConfigurationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunctionUserConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunctionUserConfigurationObject.md
ms.openlocfilehash: aab2241ecdaa4914c56d1bda6cf950c3ccce115d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140193158"
---
# New-AzConnectedNetworkFunctionUserConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk NetworkFunctionUserConfiguration

## SYNTAX

```
New-AzConnectedNetworkFunctionUserConfigurationObject [-NetworkInterface <INetworkInterface[]>]
 [-OSProfileCustomData <String>] [-RoleName <String>] [-UserDataParameter <IAny>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk NetworkFunctionUserConfiguration

## EXAMPLES

### Contoh 1: New-AzConnectedNetworkFunction
```powershell
PS C:\> $ipconf1 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip1 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"
PS C:\> $ipconf2 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip2 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf2 -Name "mrmlannic1" -VMSwitchType "LAN"
PS C:\> $customData = "I2Nsb3VkLWNvbmZpZwp3cml0ZV9maWxlczoKLSBwYXRoOiAvdmFyL2xpYi9jbG91ZC9paHNzY29uZmlnLmpzb24KICBwZXJtaXNzaW9uczogJzA2NDQnCiAgb3duZXI6IHJvb3Q6cm9vdAogIGNvbnRlbnQ6IHwKICAgIHsKICAgICAgICAgICAiRGlhbWV0ZXJHVyI6ewogICAgICAgICAgICAgICAgICAiSE9TVElQQUREUkVTUyI6IjEyOC4wLjAuMSIsCiAgICAgICAgICAgICAgICAgICJGUUROIjoiaHNzLmF5VmVuZG9yLmNvbSIsCiAgICAgICAgICAgICAgICAgICJSRUFMTSI6Imhzcy5lcGMubXlWZW5kb3I5OS5teVZlbmRvci4zZ3BwbmV0d29yay5vcmciCiAgICAgICAgICAgfSwKICAgICAgICAgICAiREdXQmluZEFkZHIiOnsKICAgICAgICAgICAgICAgICAgIkFERFJFU1MiOiIxMjguMC4wLjIiLAogICAgICAgICAgICAgICAgICAiVFJBTlNQT1JUIjoiU0NUUCIsCiAgICAgICAgICAgICAgICAgICJQT1JUIjozODY4CiAgICAgICAgICAgfSwKICAgICAgICAgICAiU05NUFRhcmdldCI6ewogICAgICAgICAgICAgICAgICAiSE9TVCI6IjEyOC4wLjAuMyIsCiAgICAgICAgICAgICAgICAgICJQT1JUIjoiMTYyIiwKICAgICAgICAgICAgICAgICAgIlRSSUdHRVJfTEVWRUwiOiIzIgogICAgICAgICAgIH0sCiAgICAgICAgICAgIk1hbmFnZW1lbnQiOnsKICAgICAgICAgICAgICAgICAgImlwQWRkcmVzcyI6IjEyOC4wLjAuNCIsCiAgICAgICAgICAgICAgICAgICJzdWJuZXQiOiIxMjguMC4wLjEvMjQiLAogICAgICAgICAgICAgICAgICAiZ2F0ZXdheSI6IjEyOC4wLjAuMCIKICAgICAgICAgICB9LAogICAgICAgICAgICJMYW4iOnsKICAgICAgICAgICAgICAgICAgImlwQWRkcmVzcyI6IjEyOC4wLjAuNSIsCiAgICAgICAgICAgICAgICAgICJzdWJuZXQiOiIxMjguMC4wLjAvMjQiLAogICAgICAgICAgICAgICAgICAiZ2F0ZXdheSI6IjEyOC4wLjAuMCIKICAgICAgICAgICB9LAoKICAgIH0JCSAgCg=="
PS C:\> $userconf = New-AzConnectedNetworkFunctionUserConfigurationObject -NetworkInterface $ip1,$ip2 -OSProfileCustomData $customData -RoleName "hpehss"
```

Membuat antarmuka jaringan dengan alokasi metode dinamis dan versi ip ke IPv4.
Dan menggunakan ini untuk membuat dua objek konfigurasi jaringan dengan tipe vm switch.
Lalu menggunakannya untuk membuat objek konfigurasi pengguna dengan nama peran hpehss, data kustom dan array antarmuka jaringan.

## PARAMETERS

### -NetworkInterface
Konfigurasi antarmuka jaringan.
Untuk membuat, lihat bagian CATATAN untuk properti NETWORKINTERFACE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkInterface[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSProfileCustomData
Menentukan string berkode basis 64 dari data kustom.
String berkode basis 64 dikodekan ke array biner yang disimpan sebagai file di mesin virtual.
Panjang maksimum array biner adalah 65535 byte.


 **Catatan: Jangan sampai rahasia atau kata sandi apa pun dalam properti CustomData** 

 Properti ini tidak dapat diperbarui setelah VM dibuat.


 customData disampaikan ke VM untuk disimpan sebagai file.
Untuk informasi selengkapnya lihat [Data Kustom di VM Azure](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/) 

 Untuk menggunakan cloud-init untuk Linux VM, lihat [Menggunakan cloud-init untuk mengustomisasi VM Linux selama pembuatan](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).

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

### -RoleName
Nama peran fungsi jaringan.

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

### -UserDataParameter
Parameter data pengguna dari pelanggan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.IAny
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.NetworkFunctionUserConfiguration

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NETWORKINTERFACE <INetworkInterface[]>: Konfigurasi antarmuka jaringan.
  - `[IPConfiguration <INetworkInterfaceIPConfiguration[]>]`: Daftar konfigurasi IP antarmuka jaringan.
    - `[DnsServer <String[]>]`: Daftar alamat IP server DNS.
    - `[Gateway <String>]`: Nilai gateway.
    - `[IPAddress <String>]`: Nilai alamat IP.
    - `[IPAllocationMethod <IPAllocationMethod?>]`: metode alokasi alamat IP.
    - `[IPVersion <IPVersion?>]`: versi alamat IP.
    - `[Subnet <String>]`: Nilai subnet.
  - `[MacAddress <String>]`: Alamat MAC antarmuka jaringan.
  - `[Name <String>]`: Nama antarmuka jaringan.
  - `[VMSwitchType <VMSwitchType?>]`: Tipe sakelar VM.

## RELATED LINKS

