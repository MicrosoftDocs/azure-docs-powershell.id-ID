---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/new-azconnectednetworkfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunction.md
ms.openlocfilehash: 8241045660327665894ca89954565ac729b0f8fb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143080469"
---
# New-AzConnectedNetworkFunction

## SYNOPSIS
Membuat atau memperbarui sumber daya fungsi jaringan.
Operasi ini dapat memakan waktu hingga 6 jam untuk diselesaikan.
Ini adalah perilaku layanan yang diharapkan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.connectednetwork/new-azconnectednetworkfunction) untuk informasi terbaru.

## SYNTAX

```
New-AzConnectedNetworkFunction -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-ContainerConfiguration <Hashtable>] [-DeviceId <String>] [-Etag <String>]
 [-ManagedApplicationParameter <Hashtable>] [-SkuName <String>] [-Tag <Hashtable>]
 [-UserConfiguration <INetworkFunctionUserConfiguration[]>] [-VendorName <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sumber daya fungsi jaringan.
Operasi ini dapat memakan waktu hingga 6 jam untuk diselesaikan.
Ini adalah perilaku layanan yang diharapkan.

## EXAMPLES

### Contoh 1: Penyebaran VNF 1 langkah
```powershell
PS C:\> $ipconf1 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ipconf2 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip1 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"
PS C:\> $ip2 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf2 -Name "mrmlannic1" -VMSwitchType "Lan"
PS C:\> $customData = "I2Nsb3VkLWNvbmZpZwp3cml0ZV9maWxlczoKLSBwYXRoOiAvdmFyL2xpYi9jbG91ZC9paHNzY29uZmlnLmpzb24KICBwZXJtaXNzaW9uczogJzA2NDQnCiAgb3duZXI6IHJvb3Q6cm9vdAogIGNvbnRlbnQ6IHwKICAgIHsKICAgICAgICAgICAiRGlhbWV0ZXJHVyI6ewogICAgICAgICAgICAgICAgICAiSE9TVElQQUREUkVTUyI6IjEyOC4wLjAuMSIsCiAgICAgICAgICAgICAgICAgICJGUUROIjoiaHNzLmF5VmVuZG9yLmNvbSIsCiAgICAgICAgICAgICAgICAgICJSRUFMTSI6Imhzcy5lcGMubXlWZW5kb3I5OS5teVZlbmRvci4zZ3BwbmV0d29yay5vcmciCiAgICAgICAgICAgfSwKICAgICAgICAgICAiREdXQmluZEFkZHIiOnsKICAgICAgICAgICAgICAgICAgIkFERFJFU1MiOiIxMjguMC4wLjIiLAogICAgICAgICAgICAgICAgICAiVFJBTlNQT1JUIjoiU0NUUCIsCiAgICAgICAgICAgICAgICAgICJQT1JUIjozODY4CiAgICAgICAgICAgfSwKICAgICAgICAgICAiU05NUFRhcmdldCI6ewogICAgICAgICAgICAgICAgICAiSE9TVCI6IjEyOC4wLjAuMyIsCiAgICAgICAgICAgICAgICAgICJQT1JUIjoiMTYyIiwKICAgICAgICAgICAgICAgICAgIlRSSUdHRVJfTEVWRUwiOiIzIgogICAgICAgICAgIH0sCiAgICAgICAgICAgIk1hbmFnZW1lbnQiOnsKICAgICAgICAgICAgICAgICAgImlwQWRkcmVzcyI6IjEyOC4wLjAuNCIsCiAgICAgICAgICAgICAgICAgICJzdWJuZXQiOiIxMjguMC4wLjEvMjQiLAogICAgICAgICAgICAgICAgICAiZ2F0ZXdheSI6IjEyOC4wLjAuMCIKICAgICAgICAgICB9LAogICAgICAgICAgICJMYW4iOnsKICAgICAgICAgICAgICAgICAgImlwQWRkcmVzcyI6IjEyOC4wLjAuNSIsCiAgICAgICAgICAgICAgICAgICJzdWJuZXQiOiIxMjguMC4wLjAvMjQiLAogICAgICAgICAgICAgICAgICAiZ2F0ZXdheSI6IjEyOC4wLjAuMCIKICAgICAgICAgICB9LAoKICAgIH0JCSAgCg=="
PS C:\> $userconf = New-AzConnectedNetworkFunctionUserConfigurationObject -NetworkInterface $ip1,$ip2 -OSProfileCustomData $customData -RoleName "hpehss"
PS C:\> New-AzConnectedNetworkFunction -Name vnf_Test1 -ResourceGroupName myResources -Location "eastus" -DeviceId /subscriptions/xxxxx-00000-xxxxx-00000/resourceGroups/myResources/providers/Microsoft.HybridNetwork/devices/mec_2111_020 -SkuName Affirmed-HSS-0527 -UserConfiguration $userconf -VendorName "AffirmedVendor"

Location Name      Etag                 ResourceGroupName
-------- ----      ----                 -----------------
eastus   vnf_Test1 "SampleEtagvalue"    myResources
```

Membuat antarmuka jaringan dengan alokasi metode dinamis dan versi IP ke IPv4.
Dan menggunakan ini untuk membuat dua objek konfigurasi jaringan dengan tipe sakelar vm.
Lalu menggunakannya untuk membuat objek konfigurasi pengguna dengan hpehs nama peran, data kustom dan array antarmuka jaringan.
Kemudian membuat NF menggunakan konfigurasi pengguna, nama vendor, nama sku, nama perangkat dll.

### Contoh 2: Penyebaran VNF 2 langkah
```powershell
PS C:\> $ipconf1 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ipconf2 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip1 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"
PS C:\> $ip2 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf2 -Name "mrmlannic1" -VMSwitchType "Lan"
PS C:\> $userconfig2 = New-AzConnectedNetworkFunctionUserConfigurationObject -NetworkInterface $ip1,$ip2 -RoleName "hpehss"
PS C:\> $vnf1 = New-AzConnectedNetworkFunction -Name vnftest11 -DeviceId /subscriptions/xxxxx-00000-xxxxx-00000/resourceGroups/myResources/providers/Microsoft.HybridNetwork/devices/mec_autotest_01 -ResourceGroupName myResources -SubscriptionId xxxxx-00000-xxxxx-00000 -Location eastus2euap -SkuName staticSku -VendorName hssvendor01 -UserConfiguration $userconfig2 -verbose
PS C:\> $v2.ServiceKey
abcd-sample-service-key-val-1234
```

Sama dengan alur kerja 1 langkah selain tidak ada bidang data kustom dalam objek Konfigurasi Pengguna.
Membuat NF dan akan menggunakan kunci layanan yang diperoleh di sini untuk menyebarkan NF vendor.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -ContainerConfiguration
Fungsi jaringan kontainer konfigurasi dari pengguna.

```yaml
Type: System.Collections.Hashtable
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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceId
ID Sumber Daya.

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

### -Etag
String baca-saja unik yang berubah setiap kali sumber daya diperbarui.

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

### -Lokasi
Lokasi geografis tempat sumber daya berada

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

### -ManagedApplicationParameter
Parameter untuk aplikasi yang dikelola.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya untuk sumber daya fungsi jaringan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NetworkFunctionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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

### -SkuName
Nama sku untuk fungsi jaringan.
Setelah diatur, perangkat tidak dapat diperbarui.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserConfiguration
Konfigurasi fungsi jaringan dari pengguna.
Untuk membangun, lihat bagian CATATAN untuk properti USERCONFIGURATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkFunctionUserConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VendorName
Nama vendor untuk fungsi jaringan.
Setelah diatur, perangkat tidak dapat diperbarui.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkFungsi

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


USERCONFIGURATION <INetworkFunctionUserConfiguration[]>: Konfigurasi fungsi jaringan dari pengguna.
  - `[NetworkInterface <INetworkInterface[]>]`: Konfigurasi antarmuka jaringan.
    - `[IPConfiguration <INetworkInterfaceIPConfiguration[]>]`: Daftar konfigurasi IP antarmuka jaringan.
      - `[DnsServer <String[]>]`: Daftar alamat IP server DNS.
      - `[Gateway <String>]`: Nilai gateway.
      - `[IPAddress <String>]`: Nilai alamat IP.
      - `[IPAllocationMethod <IPAllocationMethod?>]`: Metode alokasi alamat IP.
      - `[IPVersion <IPVersion?>]`: Versi alamat IP.
      - `[Subnet <String>]`: Nilai subnet.
    - `[MacAddress <String>]`: Alamat MAC antarmuka jaringan.
    - `[Name <String>]`: Nama antarmuka jaringan.
    - `[VMSwitchType <VMSwitchType?>]`: Tipe sakelar VM.
  - `[OSProfileCustomData <String>]`: Menentukan string data kustom berkode basis 64. String berkode basis 64 didekodekan ke array biner yang disimpan sebagai file di mesin virtual. Panjang maksimum array biner adalah 65535 byte.    **Catatan: Jangan berikan rahasia atau kata sandi apa pun dalam properti customData**    Properti ini tidak dapat diperbarui setelah VM dibuat.    customData dialihkan ke VM untuk disimpan sebagai file. Untuk informasi selengkapnya, lihat [Data Kustom di Azure VM](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/)    Untuk menggunakan cloud-init untuk VM Linux Anda, lihat [Menggunakan cloud-init untuk mengkustomisasi VM Linux selama pembuatan](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)
  - `[RoleName <String>]`: Nama peran fungsi jaringan.
  - `[UserDataParameter <IAny>]`: Parameter data pengguna dari pelanggan.

## RELATED LINKS

