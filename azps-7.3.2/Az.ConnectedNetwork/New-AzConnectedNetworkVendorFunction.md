---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/new-azconnectednetworkvendorfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorFunction.md
ms.openlocfilehash: 222fce29efb5050e4a9d1a14ae134ecf44f455b1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140560219"
---
# New-AzConnectedNetworkVendorFunction

## SYNOPSIS
Membuat atau memperbarui fungsi jaringan vendor.
Operasi ini dapat memakan waktu hingga 6 jam untuk selesai.
Perilaku ini adalah perilaku layanan yang diharapkan.

## SYNTAX

```
New-AzConnectedNetworkVendorFunction -LocationName <String> -ServiceKey <String> -VendorName <String>
 [-SubscriptionId <String>] [-SkuType <SkuType>]
 [-VendorConfiguration <INetworkFunctionVendorConfiguration[]>]
 [-VendorProvisioningState <VendorProvisioningState>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui fungsi jaringan vendor.
Operasi ini dapat memakan waktu hingga 6 jam untuk selesai.
Perilaku ini adalah perilaku layanan yang diharapkan.

## EXAMPLES

### Contoh 1: New-AzConnectedNetworkVendorFunction
```powershell
PS C:\> $ipconf1 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ipconf2 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip1 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"
PS C:\> $ip2 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf2 -Name "mrmlannic1" -VMSwitchType "Lan"
PS C:\> $keyData = @{keyData = "ssh-rsa\AAAAB3NzaC1yc2EAAAADAQABAAABAQCyMpVbBgu0kftv1k+z1c3NtcB5CVDoo/X9X1LE2JUjlLlo0luEkFGJk61i53BhiTSTeRmQXN8hAZ7sn4MDUmZK7fWcHouZ2fsJo+ehses3wQPLubWBFw2L/hoSTyXifXMbEBu9SxHgqf1CEKQcvdNiWf4U7npXwjweXW9DtsF5E7h4kxhKJKFI4sNFTIX0IwUB15QEVHoBs92kDwH3fBH3kZZCMBJE/u6kT+XB22crRKkIGlp3a9gcogtOCvP+3xmsP7hjw5+nHxMUwkc/6kYyfTeLwvfI4xrTWpnB5xufts5LW5/U5GOXVg97ix9EXgiV0czThowG5K2xQ649UlJb redmond\user@n1-azuredev1"; path = $Null}
PS C:\> $keys = @{ }
PS C:\> $key += $keyData
PS C:\> $vendorconf = New-AzConnectedNetworkFunctionVendorConfigurationObject -NetworkInterface $ip1,$ip2 -RoleName hpehss -OSProfileAdminUsername MecUser -OSProfileCustomData $customData -OSProfileCustomDataRequired $True -SshPublicKey $key
PS C:\> $vendorvnf1 = New-AzConnectedNetworkVendorFunction -LocationName eastus2euap -ServiceKey b78d39-xxxx-xxxx-00946c5 -SubscriptionId xxxx-4444-xxxx-4444 -VendorName myVendor -VendorConfiguration $vendorconf -SkuType EvolvedPacketCore -VendorProvisioningState Provisioning
```

Membuat antarmuka jaringan dengan alokasi metode dinamis dan versi ip ke IPv4.
Dan menggunakan ini untuk membuat dua objek konfigurasi jaringan dengan tipe vm switch.
Creating a array key identity, Then using those to create vendor configuration object with role name hpehss, custom data, keyData and network interface array.
Menggunakan ini untuk membuat vendor NF dengan kunci layanan yang ditentukan, langganan vendor, lokasi eastus2euap, nama vendor myVendor, sku ketik EvolvedPacketCore, penyediaan status vendor Provisioning.

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

### -LocationName
Kawasan Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.

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

### -NoWait
Menjalankan perintah secara asinkron

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

### -ServiceKey
GUID untuk fungsi jaringan vendor.

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

### -SkuType
Tipe sku.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.SkuType
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

### -VendorConfiguration
Array konfigurasi vendor fungsi jaringan.
Untuk membuat, lihat bagian CATATAN untuk properti VENDORCONFIGURATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkFunctionVendorConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VendorName
Nama vendor.

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

### -VendorProvisioningState
Status penyediaan terkontrol vendor dari fungsi jaringan vendor.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.VendorProvisioningState
Parameter Sets: (All)
Aliases:

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IVendorNetworkFunction

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


VENDORCONFIGURATION <INetworkFunctionVendorConfiguration[]>: Array konfigurasi vendor fungsi jaringan.
  - `[NetworkInterface <INetworkInterface[]>]`: Konfigurasi antarmuka jaringan.
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
  - `[OSProfileAdminUsername <String>]`: Menentukan nama akun administrator.    **Windows saja: Tidak** dapat diakhiri dengan "."    **Nilai yang tidak diizinkan:** "administrator", "admin", "pengguna", "user1", "test", "user2", "test1", "user3", "admin1", "1", "123", "a", "actuser", "adm", "admin2", "aspnet", "backup", "console", "david", "guest", "john", "owner", "root", "server", "sql", "support", "support_388945a0", "sys", "test2", "test3", "user4", "user5".    **Panjang minimum (Linux):** 1 karakter **Panjang maksimum (Linux):** 64 karakter **Panjang maksimum (Windows):** 20 karakter    <li> Untuk akses akar ke VM Linux, lihat [Menggunakan hak istimewa akar pada komputer virtual Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-use-root-privileges?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) <li> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan dalam bidang ini, lihat Memilih [Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-usernames?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
  - `[OSProfileCustomData <String>]`: Menentukan string berkode basis 64 dari data kustom. String berkode basis 64 dikodekan ke array biner yang disimpan sebagai file di mesin virtual. Panjang maksimum array biner adalah 65535 byte.    **Catatan: Jangan sampai rahasia atau kata sandi apa pun dalam properti CustomData**    Properti ini tidak dapat diperbarui setelah VM dibuat.    customData disampaikan ke VM untuk disimpan sebagai file. Untuk informasi selengkapnya, lihat [Data Kustom di VM Azure](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/) Untuk menggunakan cloud-init untuk Linux VM, lihat Menggunakan [cloud-init](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) untuk mengustomisasi VM Linux selama pembuatan
  - `[OSProfileCustomDataRequired <Boolean?>]`: Menunjukkan jika data kustom diperlukan untuk menggunakan peran ini.
  - `[RoleName <String>]`: Nama peran fungsi jaringan vendor.
  - `[SshPublicKey <ISshPublicKey[]>]`: Daftar kunci publik KEYS digunakan untuk mengautentikasi menggunakan VM berbasis linux.
    - `[KeyData <String>]`: Sertifikat kunci publik VM digunakan untuk mengautentikasi dengan VM melalui vm. Kuncinya setidaknya harus memiliki 2048-bit dan dalam format linux-rsa.    Untuk membuat tombol linux, lihat [Membuat tombol KEYS DI Linux dan Mac untuk VM Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-mac-create-ssh-keys?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
    - `[Path <String>]`: Menentukan jalur lengkap pada VM yang dibuat dengan kunci publik vm yang disimpan. Jika file sudah ada, kunci tertentu akan ditambahkan ke file. Contoh: /home/user/.firefox/authorized_keys

## RELATED LINKS

