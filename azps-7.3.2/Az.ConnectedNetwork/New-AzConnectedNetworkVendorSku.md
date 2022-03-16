---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/new-azconnectednetworkvendorsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorSku.md
ms.openlocfilehash: 52447797e4a17f01ec3e2ad68f52cfc767fd4fc8
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140010221"
---
# New-AzConnectedNetworkVendorSku

## SYNOPSIS
Membuat atau memperbarui sku.
Operasi ini dapat memakan waktu hingga 2 jam untuk selesai.
Perilaku ini adalah perilaku layanan yang diharapkan.

## SYNTAX

```
New-AzConnectedNetworkVendorSku -SkuName <String> -VendorName <String> [-SubscriptionId <String>]
 [-DeploymentMode <SkuDeploymentMode>] [-ManagedApplicationParameter <Hashtable>]
 [-ManagedApplicationTemplate <Hashtable>]
 [-NetworkFunctionRoleConfigurationType <INetworkFunctionRoleConfiguration[]>]
 [-NetworkFunctionType <NetworkFunctionType>] [-Preview] [-SkuType <SkuType>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sku.
Operasi ini dapat memakan waktu hingga 2 jam untuk selesai.
Perilaku ini adalah perilaku layanan yang diharapkan.

## EXAMPLES

### Contoh 1: New-AzConnectedNetworkVendorSku
```powershell
PS C:\> $role = New-AzConnectedNetworkFunctionRoleConfigurationObject -NetworkInterface $ip1,$ip2 -OSDiskName NetFoundry -OSDiskOstype Linux -OSDiskSizeGb 40 -OSProfileCustomDataRequired $False -OSProfileAdminUsername MecUser -RoleName hpehss -RoleType VirtualMachine -VirtualMachineSize "Standard_D3_v2" -SshPublicKey $key -StorageProfileDataDisk $storage -VhdUri "https://mecvdrvhd.blob.core.windows/myvhd.vhd"
PS C:\> New-AzConnectedNetworkVendorSku -SkuName sku1 -VendorName myVendor -SubscriptionId xxxxx-22222-xxxxx-22222 -SkuType VirtualMachine -DeploymentMode PrivateEdgeZone -NetworkFunctionRoleConfigurationType @($role)

```

Membuat objek konfigurasi peran NF wuth detail yang ditentukan.
Gunakan fitur ini untuk membuat sku dengan nama sku1, nama vendor myVendor, sku tipe VirtualMachine, tipe penyebaran PrivateEdgeZone.

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

### -DeploymentMode
Mode penyebaran sku.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.SkuDeploymentMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedApplicationParameter
Parameter untuk aplikasi terkelola yang akan disediakan oleh vendor.

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

### -ManagedApplicationTemplate
Templat untuk penyebaran aplikasi yang dikelola.

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

### -NetworkFunctionRoleConfigurationType
Array definisi peran fungsi jaringan.
Untuk membuat, lihat bagian CATATAN untuk properti NETWORKFUNCTIONROLECONFIGURATIONTYPE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkFunctionRoleConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkFunctionType
Tipe fungsi jaringan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.NetworkFunctionType
Parameter Sets: (All)
Aliases:

Required: False
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

### -Preview
Menunjukkan jika sku vendor berada dalam mode pratinjau.

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

### -SkuName
Nama sku.

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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IVendorSku

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NETWORKFUNCTIONROLECONFIGURATIONTYPE <INetworkFunctionRoleConfiguration[]>: Array definisi peran fungsi jaringan.
  - `[CustomProfileMetadataConfigurationPath <String>]`: Jalur untuk konfigurasi metadata.
  - `[ImageReferenceExactVersion <String>]`: Menentukan dalam angka desimal, versi gambar yang tepat yang digunakan untuk membuat mesin virtual.
  - `[ImageReferenceOffer <String>]`: Menentukan penawaran gambar yang digunakan untuk membuat mesin virtual.
  - `[ImageReferencePublisher <String>]`: Penerbit gambar.
  - `[ImageReferenceSku <String>]`: SKU gambar.
  - `[ImageReferenceVersion <String>]`: Menentukan versi gambar yang digunakan untuk membuat mesin virtual. Format yang diperbolehkan adalah Major.Minor.Build atau 'terbaru'. Major, Minor, dan Build adalah angka desimal. Tentukan 'terbaru' untuk menggunakan versi terbaru gambar yang tersedia saat penggunaan. Meskipun Anda menggunakan 'terbaru', gambar VM tidak akan diperbarui secara otomatis setelah waktu penyebaran meskipun versi baru sudah tersedia.
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
  - `[OSDiskName <String>]`: Nama VHD.
  - `[OSDiskOstype <OperatingSystemTypes?>]`: Tipe OS.
  - `[OSDiskSizeGb <Int32?>]`: Menentukan ukuran os disk dalam gigabyte. Ini adalah ukuran disk yang diperluas sepenuhnya dari gambar VHD di ASE. Ukuran disk ini harus lebih besar dari ukuran VHD yang disediakan di vhdUri.
  - `[OSProfileAdminUsername <String>]`: Menentukan nama akun administrator.    **Windows saja: Tidak** dapat diakhiri dengan "."    **Nilai yang tidak diizinkan:** "administrator", "admin", "pengguna", "user1", "test", "user2", "test1", "user3", "admin1", "1", "123", "a", "actuser", "adm", "admin2", "aspnet", "backup", "console", "david", "guest", "john", "owner", "root", "server", "sql", "support", "support_388945a0", "sys", "test2", "test3", "user4", "user5".    **Panjang minimum (Linux):** 1 karakter **Panjang maksimum (Linux):** 64 karakter **Panjang maksimum (Windows):** 20 karakter    <li> Untuk akses akar ke VM Linux, lihat [Menggunakan hak istimewa akar pada komputer virtual Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-use-root-privileges?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) <li> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan dalam bidang ini, lihat Memilih [Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-usernames?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
  - `[OSProfileCustomData <String>]`: Menentukan string berkode basis 64 dari data kustom. String berkode basis 64 dikodekan ke array biner yang disimpan sebagai file di mesin virtual. Panjang maksimum array biner adalah 65535 byte.    **Catatan: Jangan sampai rahasia atau kata sandi apa pun dalam properti CustomData**    Properti ini tidak dapat diperbarui setelah VM dibuat.    customData disampaikan ke VM untuk disimpan sebagai file. Untuk informasi selengkapnya, lihat [Data Kustom di VM Azure](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/) Untuk menggunakan cloud-init untuk Linux VM, lihat Menggunakan [cloud-init](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) untuk mengustomisasi VM Linux selama pembuatan
  - `[OSProfileCustomDataRequired <Boolean?>]`: Menunjukkan jika data kustom diperlukan untuk menggunakan peran ini.
  - `[RoleName <String>]`: Nama peran fungsi jaringan.
  - `[RoleType <NetworkFunctionRoleConfigurationType?>]`: Tipe peran.
  - `[SshPublicKey <ISshPublicKey[]>]`: Daftar kunci publik KEYS digunakan untuk mengautentikasi menggunakan VM berbasis linux.
    - `[KeyData <String>]`: Sertifikat kunci publik VM digunakan untuk mengautentikasi dengan VM melalui vm. Kuncinya setidaknya harus memiliki 2048-bit dan dalam format linux-rsa.    Untuk membuat tombol linux, lihat [Membuat tombol KEYS DI Linux dan Mac untuk VM Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-mac-create-ssh-keys?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
    - `[Path <String>]`: Menentukan jalur lengkap pada VM yang dibuat dengan kunci publik vm yang disimpan. Jika file sudah ada, kunci tertentu akan ditambahkan ke file. Contoh: /home/user/.firefox/authorized_keys
  - `[StorageProfileDataDisk <IDataDisk[]>]`: Menentukan parameter yang digunakan untuk menambahkan disk data ke komputer virtual.
    - `[CreateOption <DiskCreateOptionTypes?>]`: Menentukan bagaimana mesin virtual harus dibuat.
    - `[DiskSizeGb <Int32?>]`: Menentukan ukuran disk kosong dalam gigabyte. Elemen ini bisa digunakan untuk menimpa ukuran disk dalam gambar mesin virtual.
    - `[Name <String>]`: Nama disk data.
  - `[UserDataParameter <IAny>]`: Parameter pengguna untuk pelanggan. Format parameter data pengguna harus cocok dengan templat data pengguna yang disediakan.
  - `[UserDataTemplate <IAny>]`: Templat data pengguna untuk pelanggan. Ini adalah templat skema json yang menjelaskan format dan tipe data parameter data pengguna.
  - `[VhdUri <String>]`: Menentukan uri hard disk virtual.
  - `[VirtualMachineSize <VirtualMachineSizeTypes?>]`: Ukuran mesin virtual.

## RELATED LINKS

