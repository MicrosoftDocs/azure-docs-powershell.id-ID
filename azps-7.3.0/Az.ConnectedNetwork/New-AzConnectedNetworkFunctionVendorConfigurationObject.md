---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkFunctionVendorConfigurationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunctionVendorConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunctionVendorConfigurationObject.md
ms.openlocfilehash: b06d168ae2d4b597310d81ba5d9253ab3b3d445c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140193127"
---
# New-AzConnectedNetworkFunctionVendorConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk NetworkFunctionVendorConfiguration

## SYNTAX

```
New-AzConnectedNetworkFunctionVendorConfigurationObject [-NetworkInterface <INetworkInterface[]>]
 [-OSProfileAdminUsername <String>] [-OSProfileCustomData <String>] [-OSProfileCustomDataRequired <Boolean>]
 [-RoleName <String>] [-SshPublicKey <ISshPublicKey[]>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk NetworkFunctionVendorConfiguration

## EXAMPLES

### Contoh 1: New-AzConnectedNetworkFunctionVendorConfigurationObject
```powershell
PS C:\> $ipconf1 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ipconf2 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip1 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"
PS C:\> $ip2 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf2 -Name "mrmlannic1" -VMSwitchType "Lan"
PS C:\> $keyData = @{keyData = "ssh-rsa\AAAAB3NzaC1yc2EAAAADAQABAAABAQCyMpVbBgu0kftv1k+z1c3NtcB5CVDoo/X9X1LE2JUjlLlo0luEkFGJk61i53BhiTSTeRmQXN8hAZ7sn4MDUmZK7fWcHouZ2fsJo+ehses3wQPLubWBFw2L/hoSTyXifXMbEBu9SxHgqf1CEKQcvdNiWf4U7npXwjweXW9DtsF5E7h4kxhKJKFI4sNFTIX0IwUB15QEVHoBs92kDwH3fBH3kZZCMBJE/u6kT+XB22crRKkIGlp3a9gcogtOCvP+3xmsP7hjw5+nHxMUwkc/6kYyfTeLwvfI4xrTWpnB5xufts5LW5/U5GOXVg97ix9EXgiV0czThowG5K2xQ649UlJb redmond\userk@n1-azuredev1"; path = $Null}
PS C:\> $keys = @{ }
PS C:\> $key += $keyData
PS C:\> $vendorconf = New-AzConnectedNetworkFunctionVendorConfigurationObject -NetworkInterface $ip1,$ip2 -RoleName hpehss -OSProfileAdminUsername MecUser -OSProfileCustomData $customData -OSProfileCustomDataRequired $True -SshPublicKey $key
```

Membuat antarmuka jaringan dengan alokasi metode dinamis dan versi ip ke IPv4.
Dan menggunakan ini untuk membuat dua objek konfigurasi jaringan dengan tipe vm switch.
Creating a wizard key identity, Then using those to create vendor configuration object with role name hpehss, custom data, keyData and network interface array, which will be used in vendor NF creation.

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

### -OSProfileAdminUsername
Menentukan nama akun administrator.


 **Windows saja: Tidak** dapat diakhiri dengan "." 

 **Nilai yang tidak diizinkan:** "administrator", "admin", "pengguna", "user1", "test", "user2", "test1", "user3", "admin1", "1", "123", "a", "actuser", "adm", "admin2", "aspnet", "backup", "console", "david", "guest", "john", "owner", "root", "server", "sql", "support", "support_388945a0", "sys", "test2", "test3", "user4", "user5".


 **Panjang-minimum (Linux):** 1 karakter 

 **Panjang-maks (Linux):** 64 karakter 

 **Panjang maks (Windows):** 20 karakter  

\<li\> Untuk akses akar ke VM Linux, lihat Menggunakan hak istimewa akar pada komputer [virtual Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-use-root-privileges?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)
\<li\> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan dalam bidang ini, lihat Memilih Nama Pengguna untuk [Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-usernames?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).

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

### -OSProfileCustomDataRequired
Menunjukkan jika data kustom diperlukan untuk menggunakan peran ini.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleName
Nama peran fungsi jaringan vendor.

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

### -KlikPublicKey
Daftar kunci publik KEYS digunakan untuk mengautentikasi menggunakan VM berbasis linux.
Untuk membuat, lihat bagian CATATAN untuk properti NOTESPUBECKEY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.ISshPublicKey[]
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.NetworkFunctionVendorConfiguration

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

KEYSPUCHEREY <ISshPublicKey[]>: Daftar tombol publik KEYS YANG digunakan untuk mengautentikasi dengan VM berbasis linux.
  - `[KeyData <String>]`: Sertifikat kunci publik VM digunakan untuk mengautentikasi dengan VM melalui vm. Kuncinya setidaknya harus memiliki 2048-bit dan dalam format linux-rsa.    Untuk membuat tombol linux, lihat [Membuat tombol KEYS DI Linux dan Mac untuk VM Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-mac-create-ssh-keys?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
  - `[Path <String>]`: Menentukan jalur lengkap pada VM yang dibuat dengan kunci publik vm yang disimpan. Jika file sudah ada, kunci tertentu akan ditambahkan ke file. Contoh: /home/user/.firefox/authorized_keys

## RELATED LINKS

