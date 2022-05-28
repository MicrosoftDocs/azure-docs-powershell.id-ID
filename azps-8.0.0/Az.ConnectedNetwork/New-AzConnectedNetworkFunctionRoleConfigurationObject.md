---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkFunctionRoleConfigurationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunctionRoleConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkFunctionRoleConfigurationObject.md
ms.openlocfilehash: 941bacf3ec4580787438d732efa92caf8b99a599
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145551570"
---
# New-AzConnectedNetworkFunctionRoleConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk NetworkFunctionRoleConfiguration

## SYNTAX

```
New-AzConnectedNetworkFunctionRoleConfigurationObject [-CustomProfileMetadataConfigurationPath <String>]
 [-ImageReferenceExactVersion <String>] [-ImageReferenceOffer <String>] [-ImageReferencePublisher <String>]
 [-ImageReferenceSku <String>] [-ImageReferenceVersion <String>] [-NetworkInterface <INetworkInterface[]>]
 [-OSDiskName <String>] [-OSDiskOstype <OperatingSystemTypes>] [-OSDiskSizeGb <Int32>]
 [-OSProfileAdminUsername <String>] [-OSProfileCustomData <String>] [-OSProfileCustomDataRequired <Boolean>]
 [-RoleName <String>] [-RoleType <NetworkFunctionRoleConfigurationType>] [-SshPublicKey <ISshPublicKey[]>]
 [-StorageProfileDataDisk <IDataDisk[]>] [-UserDataParameter <IAny>] [-UserDataTemplate <IAny>]
 [-VhdUri <String>] [-VirtualMachineSize <VirtualMachineSizeTypes>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk NetworkFunctionRoleConfiguration

## EXAMPLES

### Contoh 1: New-AzConnectedNetworkFunctionUserConfigurationObject
```powershell
PS C:\> $ipconf1 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ipconf2 = New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"
PS C:\> $ip1 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"
PS C:\> $ip2 = New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf2 -Name "mrmlannic1" -VMSwitchType "Lan"
PS C:\> $keyData = @{keyData = "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCyMpVbBgu0kftv1k+z1c3NtcB5CVDoo/X9X1LE2JUjlLlo0luEkFGJk61i53BhiTSTeRmQXN8hAZ7sn4MDUmZK7fWcHouZ2fsJo+ehses3wQPLubWBFw2L/hoSTyXifXMbEBu9SxHgqf1CEKQcvdNiWf4U7npXwjweXW9DtsF5E7h4kxhKJKFI4sNFTIX0IwUB15QEVHoBs92kDwH3fBH3kZZCMBJE/u6kT+XB22crRKkIGlp3a9gcogtOCvP+3xmsP7hjw5+nHxMUwkc/6kYyfTeLwvfI4xrTWpnB5xufts5LW5/U5GOXVg97ix9EXgiV0czThowG5K2xQ649UlJb"; path = $Null}
PS C:\> $key = @( $keyData)
PS C:\> $role = New-AzConnectedNetworkFunctionRoleConfigurationObject -NetworkInterface $ip1,$ip2 -OSDiskName Disk1 -OSDiskOstype Linux -OSDiskSizeGb 40 -OSProfileCustomDataRequired $False -OSProfileAdminUsername MecUser -RoleName hpehss -RoleType VirtualMachine -VirtualMachineSize "Standard_D3_v2" -SshPublicKey $key -StorageProfileDataDisk $storage -VhdUri "https://mecvdrvhd.blob.core.windows/myvhd.vhd"

RoleName RoleType       VirtualMachineSize
-------- --------       ------------------
hpehss   VirtualMachine Standard_D3_v2

```

Membuat 2 objek konfigurasi ip (ipconf1 dan ipconf2) dengan metode alokasi dinamis dan IPv4.
Menggunakan ini untuk membuat objek antarmuka jaringan dengan ipconfiguration $ipconf 1 dan $ipconf 2, nama antarmuka sebagai mrmmanagementnic1 dan mrmlannic1 dan beralih jenis sebagai manajemen dan lan, masing-masing.
Menyimpan data kunci profil os dalam array kunci.
Dan membuat objek konfigurasi pengguna fungsi jaringan dari objek antarmuka jaringan, data kunci, dan nama peran hpehss.

## PARAMETERS

### -CustomProfileMetadataConfigurationPath
Jalur untuk konfigurasi metadata.

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

### -ImageReferenceExactVersion
Menentukan angka desimal, versi gambar yang tepat yang digunakan untuk membuat komputer virtual.

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

### -ImageReferenceOffer
Menentukan penawaran gambar yang digunakan untuk membuat komputer virtual.

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

### -ImageReferencePublisher
Penerbit gambar.

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

### -ImageReferenceSku
SKU gambar.

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

### -ImageReferenceVersion
Menentukan versi gambar yang digunakan untuk membuat komputer virtual.
Format yang diizinkan adalah Major.Minor.Build atau 'terbaru'.
Mayor, Minor, dan Build adalah angka desimal.
Pilih 'terbaru' untuk menggunakan citra versi terbaru yang tersedia pada waktu penerapan.
Bahkan jika Anda menggunakan 'terbaru', gambar VM tidak akan diperbarui secara otomatis setelah waktu penyebaran bahkan jika versi baru tersedia.

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

### -NetworkInterface
Konfigurasi antarmuka jaringan.
Untuk membuat, lihat bagian CATATAN untuk properti NETWORKINTERFACE dan buat tabel hash.

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

### -OSDiskName
Nama VHD.

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

### -OSDiskOstype
Jenis OS.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.OperatingSystemTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSDiskSizeGb
Menentukan ukuran disk os dalam gigabyte.
Ini adalah ukuran disk yang diperluas sepenuhnya yang diperlukan dari gambar VHD pada ASE.
Ukuran disk ini harus lebih besar dari ukuran VHD yang disediakan dalam vhdUri.

```yaml
Type: System.Int32
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


 **pembatasan khusus Windows:** Tidak dapat berakhiran "." 

 **Nilai yang tidak diizinkan:** "administrator", "admin", "user", "user1", "test", "user2", "test1", "user3", "admin1", "1", "123", "a", "actuser", "adm", "admin2", "aspnet", "backup", "console", "david", "guest", "john", "owner", "root", "server", "sql", "support", "support_388945a0", "sys", "test2", "test3", "user4", "user5".


 **Panjang minimum (Linux):** 1 karakter 

 **Panjang maksimum (Linux):** 64 karakter 

 **Panjang maksimum (Windows):** 20 karakter  

\<li\> Untuk akses root ke VM Linux, lihat [Menggunakan hak istimewa root pada komputer virtual Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-use-root-privileges?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)
\<li\> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan di bidang ini, lihat [Memilih Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-usernames?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).

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
Menentukan string data kustom yang dikodekan base-64.
String yang dikodekan base-64 didekodekan ke array biner yang disimpan sebagai file pada komputer virtual.
Panjang maksimum array biner adalah 65535 byte.


 **Catatan: Jangan berikan rahasia atau kata sandi apa pun di properti customData** 

 Properti ini tidak dapat diperbarui setelah VM dibuat.


 customData diteruskan ke VM untuk disimpan sebagai file.
Untuk informasi selengkapnya, lihat [Data Kustom di Azure VM](https://azure.microsoft.com/en-us/blog/custom-data-and-cloud-init-on-windows-azure/) 

 Untuk menggunakan cloud-init untuk VM Linux Anda, lihat [Menggunakan cloud-init untuk menyesuaikan VM Linux selama pembuatan](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-using-cloud-init?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).

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
Menunjukkan apakah data kustom diperlukan untuk menyebarkan peran ini.

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

### -RoleType
Jenis peran.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.NetworkFunctionRoleConfigurationType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshPublicKey
Daftar kunci umum SSH yang digunakan untuk mengautentikasi dengan VM berbasis linux.
Untuk membuat, lihat bagian CATATAN untuk properti SSHPUBLICKEY dan membuat tabel hash.

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

### -StorageProfileDataDisk
Menentukan parameter yang digunakan untuk menambahkan disk data ke komputer virtual.
Untuk membuat, lihat bagian CATATAN untuk properti STORAGEPROFILEDATADISK dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IDataDisk[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserDataParameter
Parameter pengguna untuk pelanggan.
Format parameter data pengguna harus dicocokkan dengan templat data pengguna yang disediakan.

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

### -UserDataTemplate
Templat data pengguna untuk pelanggan.
Ini adalah templat skema json yang menjelaskan format dan jenis data parameter data pengguna.

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

### -VhdUri
Menentukan uri hard disk virtual.

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

### -VirtualMachineSize
Ukuran komputer virtual.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.VirtualMachineSizeTypes
Parameter Sets: (All)
Aliases:

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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.NetworkFunctionRoleConfiguration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NETWORKINTERFACE <INetworkInterface[]>: Konfigurasi antarmuka jaringan.
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

SSHPUBLICKEY <ISshPublicKey[]>: Daftar kunci publik SSH yang digunakan untuk mengautentikasi dengan VM berbasis linux.
  - `[KeyData <String>]`: Sertifikat kunci publik SSH yang digunakan untuk mengautentikasi dengan VM melalui ssh. Kuncinya harus setidaknya 2048-bit dan dalam format ssh-rsa.    Untuk membuat kunci ssh, lihat [Membuat kunci SSH di Linux dan Mac untuk VM Linux di Azure](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-mac-create-ssh-keys?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json).
  - `[Path <String>]`: Menentukan jalur lengkap pada VM yang dibuat tempat kunci umum ssh disimpan. Jika file sudah ada, kunci yang ditentukan ditambahkan ke file. Contoh: /home/user/.ssh/authorized_keys

STORAGEPROFILEDATADISK <IDataDisk[]>: Menentukan parameter yang digunakan untuk menambahkan disk data ke komputer virtual.
  - `[CreateOption <DiskCreateOptionTypes?>]`: Menentukan bagaimana komputer virtual harus dibuat.
  - `[DiskSizeGb <Int32?>]`: Menentukan ukuran disk kosong dalam gigabyte. Elemen ini dapat digunakan untuk menimpa ukuran disk dalam gambar komputer virtual.
  - `[Name <String>]`: Nama disk data.

## RELATED LINKS

