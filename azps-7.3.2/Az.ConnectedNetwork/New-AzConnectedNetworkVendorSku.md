---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/new-azconnectednetworkvendorsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkVendorSku.md
ms.openlocfilehash: f7ddbcb0aeca64fb626a8a880b0ad145af55f88f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143246933"
---
# New-AzConnectedNetworkVendorSku

## SYNOPSIS
Membuat atau memperbarui sku.
Operasi ini dapat memakan waktu hingga 2 jam untuk diselesaikan.
Ini adalah perilaku layanan yang diharapkan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.connectednetwork/new-azconnectednetworkvendorsku) untuk informasi terbaru.

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
Operasi ini dapat memakan waktu hingga 2 jam untuk diselesaikan.
Ini adalah perilaku layanan yang diharapkan.

## EXAMPLES

### Contoh 1: New-AzConnectedNetworkVendorSku
```powershell
PS C:\> $role = New-AzConnectedNetworkFunctionRoleConfigurationObject -NetworkInterface $ip1,$ip2 -OSDiskName NetFoundry -OSDiskOstype Linux -OSDiskSizeGb 40 -OSProfileCustomDataRequired $False -OSProfileAdminUsername MecUser -RoleName hpehss -RoleType VirtualMachine -VirtualMachineSize "Standard_D3_v2" -SshPublicKey $key -StorageProfileDataDisk $storage -VhdUri "https://mecvdrvhd.blob.core.windows/myvhd.vhd"
PS C:\> New-AzConnectedNetworkVendorSku -SkuName sku1 -VendorName myVendor -SubscriptionId xxxxx-22222-xxxxx-22222 -SkuType VirtualMachine -DeploymentMode PrivateEdgeZone -NetworkFunctionRoleConfigurationType @($role)

```

Membuat objek konfigurasi peran NF dengan detail yang ditentukan.
Menggunakan ini untuk membuat sku dengan sku name sku1, nama vendor myVendor, tipe sku VirtualMachine, tipe deployment PrivateEdgeZone.

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
Parameter untuk aplikasi yang dikelola akan disediakan oleh vendor.

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
Templat untuk penyebaran aplikasi terkelola.

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
Untuk membangun, lihat bagian CATATAN untuk properti NETWORKFUNCTIONROLECONFIGURATIONTYPE dan membuat tabel hash.

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

### -Pratinjau
Menunjukkan apakah sku vendor berada dalam mode pratinjau.

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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IVendorSku

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NETWORKFUNCTIONROLECONFIGURATIONTYPE <INetworkFunctionRoleConfiguration[]>: Array definisi peran fungsi jaringan.
  - `[CustomProfileMetadataConfigurationPath <String>]`: Jalur untuk konfigurasi metadata.
  - `[ImageReferenceExactVersion <String>]`: Menentukan angka desimal, versi gambar yang tepat digunakan untuk membuat mesin virtual.
  - `[ImageReferenceOffer <String>]`: Menentukan penawaran gambar yang digunakan untuk membuat mesin virtual.
  - `[ImageReferencePublisher <String>]`: Penerbit gambar.
  - `[ImageReferenceSku <String>]`: SKU gambar.
  - `[ImageReferenceVersion <String>]`: Menentukan versi gambar yang digunakan untuk membuat mesin virtual. Format yang diizinkan adalah Major.Minor.Build atau 'terbaru'. Mayor, Minor, dan Build adalah angka desimal. Tentukan 'terbaru' untuk menggunakan versi terbaru gambar yang tersedia pada waktu penggunaan. Bahkan jika Anda menggunakan 'terbaru', gambar VM tidak akan diperbarui secara otomatis setelah waktu penggunaan bahkan jika versi baru tersedia.
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
  - `[OSDiskName <String>]`: Nama VHD.
  - `[OSDiskOstype <OperatingSystemTypes?>]`: Tipe OS.
  - `[OSDiskSizeGb <Int32?>]`: Menentukan ukuran disk os dalam gigabyte. Ini adalah ukuran disk yang sepenuhnya diperluas yang diperlukan dari gambar VHD di ASE. Ukuran disk ini harus lebih besar dari ukuran VHD yang disediakan dalam vhdUri.
  - `[OSProfileAdminUsername <String>]`: Menentukan nama akun administrator.    **batasan Windows-saja:** Tidak dapat berakhiran "."    **Nilai yang tidak diperbolehkan:** "administrator", "admin", "user", "user1", "test", "user2", "test1", "user3", "admin1", "1", "123", "a", "actuser", "adm", "admin2", "aspnet", "backup", "console", "david", "guest", "john", "owner", "root", "server", "sql", "support", "support_388945a0", "sys", "test2", "test3", "user4", "user5".    **Panjang minimum (Linux):** Panjang maksimal 1 karakter **(Linux):** Panjang maksimal 64 karakter **(Windows):** 20 karakter    <li> Untuk akses akar ke VM Linux, lihat [Menggunakan hak istimewa akar pada mesin virtual Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-use-root-privileges?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) <li> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan dalam bidang ini, lihat [Memilih Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-usernames?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
  - `[OSProfileCustomData <String>]`: Menentukan string data kustom berkode basis 64. String berkode basis 64 didekodekan ke array biner yang disimpan sebagai file di mesin virtual. Panjang maksimum array biner adalah 65535 byte.    **Catatan: Jangan berikan rahasia atau kata sandi apa pun dalam properti customData**    Properti ini tidak dapat diperbarui setelah VM dibuat.    customData dialihkan ke VM untuk disimpan sebagai file. Untuk informasi selengkapnya, lihat [Data Kustom di Azure VM](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/)    Untuk menggunakan cloud-init untuk VM Linux Anda, lihat [Menggunakan cloud-init untuk mengkustomisasi VM Linux selama pembuatan](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)
  - `[OSProfileCustomDataRequired <Boolean?>]`: Menunjukkan apakah data kustom diperlukan untuk menyebarkan peran ini.
  - `[RoleName <String>]`: Nama peran fungsi jaringan.
  - `[RoleType <NetworkFunctionRoleConfigurationType?>]`: Tipe peran.
  - `[SshPublicKey <ISshPublicKey[]>]`: Daftar kunci publik SSH yang digunakan untuk mengautentikasi dengan VM berbasis linux.
    - `[KeyData <String>]`: Sertifikat kunci publik SSH yang digunakan untuk mengautentikasi dengan VM melalui ssh. Kunci harus setidaknya 2048-bit dan dalam format ssh-rsa.    Untuk membuat kunci ssh, lihat [Membuat kunci SSH di Linux dan Mac untuk VM Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-mac-create-ssh-keys?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
    - `[Path <String>]`: Menentukan jalur lengkap pada VM yang dibuat tempat kunci publik ssh disimpan. Jika file sudah ada, kunci yang ditentukan ditambahkan ke file. Contoh: /home/user/.ssh/authorized_keys
  - `[StorageProfileDataDisk <IDataDisk[]>]`: Menentukan parameter yang digunakan untuk menambahkan disk data ke mesin virtual.
    - `[CreateOption <DiskCreateOptionTypes?>]`: Menentukan bagaimana mesin virtual harus dibuat.
    - `[DiskSizeGb <Int32?>]`: Menentukan ukuran disk kosong dalam gigabyte. Elemen ini dapat digunakan untuk menimpa ukuran disk dalam gambar mesin virtual.
    - `[Name <String>]`: Nama disk data.
  - `[UserDataParameter <IAny>]`: Parameter pengguna untuk pelanggan. Format parameter data pengguna harus dicocokkan dengan templat data pengguna yang disediakan.
  - `[UserDataTemplate <IAny>]`: Templat data pengguna untuk pelanggan. Ini adalah templat skema json yang menjelaskan format dan tipe data parameter data pengguna.
  - `[VhdUri <String>]`: Menentukan uri hard disk virtual.
  - `[VirtualMachineSize <VirtualMachineSizeTypes?>]`: Ukuran mesin virtual.

## RELATED LINKS

