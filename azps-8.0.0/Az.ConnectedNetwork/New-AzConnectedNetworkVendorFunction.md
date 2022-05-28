---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/new-azconnectednetworkvendorfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorFunction.md
ms.openlocfilehash: 222fce29efb5050e4a9d1a14ae134ecf44f455b1
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145510978"
---
# New-AzConnectedNetworkVendorFunction

## SYNOPSIS
Membuat atau memperbarui fungsi jaringan vendor.
Operasi ini dapat memakan waktu hingga 6 jam untuk diselesaikan.
Ini adalah perilaku layanan yang diharapkan.

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
Operasi ini dapat memakan waktu hingga 6 jam untuk diselesaikan.
Ini adalah perilaku layanan yang diharapkan.

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
Dan menggunakan ini untuk membuat dua objek konfigurasi jaringan dengan jenis sakelar vm.
Membuat identitas kunci ssh, Kemudian menggunakannya untuk membuat objek konfigurasi vendor dengan nama peran hpehss, data kustom, keyData, dan array antarmuka jaringan.
Menggunakan ini untuk membuat vendor NF dengan kunci layanan yang ditentukan, langganan vendor, lokasi eastus2euap, nama vendor myVendor, jenis sku EvolvedPacketCore, Penyediaan status provisi vendor.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Wilayah Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.

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
Jenis sku.

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
Untuk membuat, lihat bagian CATATAN untuk properti VENDORCONFIGURATION dan buat tabel hash.

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
Vendor mengontrol status penyediaan fungsi jaringan vendor.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IVendorNetworkFunction

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


VENDORCONFIGURATION <INetworkFunctionVendorConfiguration[]>: Array konfigurasi vendor fungsi jaringan.
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
    - `[VMSwitchType <VMSwitchType?>]`: Jenis sakelar VM.
  - `[OSProfileAdminUsername <String>]`: Menentukan nama akun administrator.    **pembatasan khusus Windows:** Tidak dapat berakhiran "."    **Nilai yang tidak diizinkan:** "administrator", "admin", "user", "user1", "test", "user2", "test1", "user3", "admin1", "1", "123", "a", "actuser", "adm", "admin2", "aspnet", "backup", "console", "david", "guest", "john", "owner", "root", "server", "sql", "support", "support_388945a0", "sys", "test2", "test3", "user4", "user5".    **Panjang minimum (Linux):** Panjang maksimum 1 karakter **(Linux):** Panjang maksimum 64 karakter **(Windows):** 20 karakter    <li> Untuk akses root ke VM Linux, lihat [Menggunakan hak istimewa root pada komputer virtual Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-use-root-privileges?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) <li> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan di bidang ini, lihat [Memilih Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-usernames?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
  - `[OSProfileCustomData <String>]`: Menentukan string data kustom yang dikodekan base-64. String yang dikodekan base-64 didekodekan ke array biner yang disimpan sebagai file pada komputer virtual. Panjang maksimum array biner adalah 65535 byte.    **Catatan: Jangan meneruskan rahasia atau kata sandi apa pun di properti customData**    Properti ini tidak dapat diperbarui setelah VM dibuat.    customData diteruskan ke VM untuk disimpan sebagai file. Untuk informasi selengkapnya lihat [Data Kustom di Azure VM](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/)    Untuk menggunakan cloud-init untuk VM Linux Anda, lihat [Menggunakan cloud-init untuk menyesuaikan VM Linux selama pembuatan](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)
  - `[OSProfileCustomDataRequired <Boolean?>]`: Menunjukkan apakah data kustom diperlukan untuk menyebarkan peran ini.
  - `[RoleName <String>]`: Nama peran fungsi jaringan vendor.
  - `[SshPublicKey <ISshPublicKey[]>]`: Daftar kunci umum SSH yang digunakan untuk mengautentikasi dengan VM berbasis linux.
    - `[KeyData <String>]`: Sertifikat kunci umum SSH yang digunakan untuk mengautentikasi dengan VM melalui ssh. Kuncinya harus setidaknya 2048-bit dan dalam format ssh-rsa.    Untuk membuat kunci ssh, lihat [Membuat kunci SSH di Linux dan Mac untuk VM Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-mac-create-ssh-keys?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
    - `[Path <String>]`: Menentukan jalur lengkap pada VM yang dibuat tempat kunci umum ssh disimpan. Jika file sudah ada, kunci yang ditentukan ditambahkan ke file. Contoh: /home/user/.ssh/authorized_keys

## RELATED LINKS

