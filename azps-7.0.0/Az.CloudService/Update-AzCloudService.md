---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/update-azcloudservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Update-AzCloudService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Update-AzCloudService.md
ms.openlocfilehash: 5a5095e019f582997878c829d19a7835cd8f86aa
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136535981"
---
# Update-AzCloudService

## SYNOPSIS
Membuat atau memperbarui layanan awan.
Harap diperhatikan bahwa beberapa properti dapat diatur hanya selama pembuatan layanan awan.

## SYNTAX

```
Update-AzCloudService -InputObject <ICloudServiceIdentity> -Parameter <ICloudService>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui layanan awan.
Harap diperhatikan bahwa beberapa properti dapat diatur hanya selama pembuatan layanan awan.

## EXAMPLES

### Contoh 1: Tambahkan ekstensi RDP ke layanan awan yang sudah ada
```powershell
# Create RDP extension object
PS C:\> $rdpExtension = New-AzCloudServiceRemoteDesktopExtensionObject -Name "RDPExtension" -Credential $credential -Expiration $expiration -TypeHandlerVersion "1.2.1"
# Get existing cloud service
PS C:\> $cloudService = Get-AzCloudService -ResourceGroup "ContosOrg" -CloudServiceName "ContosoCS"
# Add RDP extension to existing cloud service extension object
PS C:\> $cloudService.ExtensionProfile.Extension = $cloudService.ExtensionProfile.Extension + $rdpExtension
# Update cloud service
PS C:\> $cloudService | Update-AzCloudService
```

Di atas kumpulan perintah menambahkan ekstensi RDP ke layanan awan yang sudah ada bernama ContosoCS yang dimiliki oleh grup sumber daya yang bernama ContosOrg.

### Contoh 2: Hapus semua ekstensi dari layanan cloud
```powershell
# Get existing cloud service
PS C:\> $cloudService = Get-AzCloudService -ResourceGroup "ContosOrg" -CloudServiceName "ContosoCS"
# Set extension to empty list
PS C:\> $cloudService.ExtensionProfile.Extension = @()
# Update cloud service
PS C:\> $cloudService | Update-AzCloudService
```

Kumpulan perintah di atas menghapus semua ekstensi dari layanan awan yang sudah ada bernama ContosoCS yang dimiliki oleh grup sumber daya bernama ContosOrg.

### Contoh 3: Hapus ekstensi RDP dari layanan awan
```powershell
# Get existing cloud service
PS C:\> $cloudService = Get-AzCloudService -ResourceGroup "ContosOrg" -CloudServiceName "ContosoCS"
# Remove extension by name RDPExtension
PS C:\> $cloudService.ExtensionProfile.Extension = $cloudService.ExtensionProfile.Extension | Where-Object { $_.Name -ne "RDPExtension" }
# Update cloud service
PS C:\> $cloudService | Update-AzCloudService
```

Kumpulan perintah di atas menghapus ekstensi RDP dari layanan awan yang sudah ada bernama ContosoCS yang dimiliki oleh grup sumber daya bernama ContosOrg.

### Contoh 4: Scale-Out / Scale-In peran
```powershell
# Get existing cloud service
PS C:\> $cloudService = Get-AzCloudService -ResourceGroup "ContosOrg" -CloudServiceName "ContosoCS"

# Scale-out all role instance count by 1
PS C:\> $cloudService.RoleProfile.Role | ForEach-Object {$_.SkuCapacity += 1}

# Scale-in ContosoFrontend role instance count by 1
PS C:\> $role = $cloudService.RoleProfile.Role | Where-Object {$_.Name -eq "ContosoFrontend"}
PS C:\> $role.SkuCapacity -= 1

# Update cloud service configuration as per the new role instance count
PS C:\> $cloudService.Configuration = $configuration

# Update cloud service
PS C:\> $cloudService | Update-AzCloudService
```

Kumpulan perintah di atas memperlihatkan cara menghitung skala dan skala dalam jumlah contoh peran untuk layanan awan bernama ContosoCS yang dimiliki oleh grup sumber daya bernama ContosOrg.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Parameter
Menjelaskan layanan awan.
Untuk membuat, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICloudServiceIdentity> : Parameter Identitas
  - `[CloudServiceName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi yang terkait dengan versi OS.
  - `[OSFamilyName <String>]`: Nama keluarga OS.
  - `[OSVersionName <String>]`: Nama versi OS.
  - `[ResourceGroupName <String>]`: 
  - `[RoleInstanceName <String>]`: Nama contoh peran.
  - `[RoleName <String>]`: Nama peran.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[UpdateDomain <Int32?>]`: Menentukan nilai bilangan bulat yang mengidentifikasi domain pembaruan. Update domains are identified with a zero-based index: the first update domain has an ID of 0, the second has an ID of 1, and so on.

PARAMETER <ICloudService> : Menjelaskan layanan awan.
  - `Location <String>`: Lokasi sumber daya.
  - `[AllowModelOverride <Boolean?>]`: (Opsional) Menunjukkan apakah properti sku peran (roleProfile.roles.sku) yang ditentukan dalam model/templat harus mengganti jumlah contoh peran dan ukuran vm yang ditentukan masing-masing dalam .cscfg dan .csdef.         Nilai defaultnya adalah `false` .
  - `[Configuration <String>]`: Menentukan konfigurasi layanan XML (.cscfg) untuk layanan awan.
  - `[ConfigurationUrl <String>]`: Menentukan URL yang merujuk ke lokasi konfigurasi layanan dalam layanan Blob. URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (Sas, Shared Access Signature) dari akun penyimpanan apa pun.         Ini adalah properti khusus untuk menulis dan tidak dikembalikan dalam panggilan GET.
  - `[ExtensionProfile <ICloudServiceExtensionProfile>]`: Menjelaskan profil ekstensi layanan awan.
    - `[Extension <IExtension[]>]`: Daftar ekstensi untuk layanan awan.
      - `[AutoUpgradeMinorVersion <Boolean?>]`: Tentukan secara eksplisit apakah platform bisa secara otomatis memutakhirkan tipeHandlerVersion ke versi minor yang lebih tinggi ketika tersedia.
      - `[ForceUpdateTag <String>]`: Tag untuk memaksa menerapkan pengaturan publik dan yang diproteksi yang disediakan.         Mengubah nilai tag memungkinkan untuk menjalankan kembali ekstensi tanpa mengubah pengaturan publik atau yang diproteksi.         Jika forceUpdateTag tidak diubah, pembaruan ke pengaturan publik atau yang diproteksi masih akan diterapkan oleh penanganan.         Jika tidak memaksaUpdateTag maupun pengaturan publik atau yang diproteksi berubah, ekstensi akan mengalir ke contoh peran dengan nomor urutan yang sama, dan sudah siap untuk menangani implementasi apakah akan menjalankannya kembali atau tidak
      - `[Name <String>]`: Nama ekstensi.
      - `[ProtectedSetting <String>]`: Pengaturan terlindungi untuk ekstensi yang dienkripsi sebelum dikirimkan ke contoh peran.
      - `[ProtectedSettingFromKeyVaultSecretUrl <String>]`: 
      - `[Publisher <String>]`: Nama penerbit penanganan ekstensi.
      - `[RolesAppliedTo <String[]>]`: Daftar peran opsional untuk menerapkan ekstensi ini. Jika properti tidak ditentukan atau '*' ditentukan, ekstensi diterapkan ke semua peran di layanan awan.
      - `[Setting <String>]`: Pengaturan publik untuk ekstensi. Untuk ekstensi JSON, ini adalah pengaturan JSON untuk ekstensi tersebut. Untuk Ekstensi XML (seperti RDP), ini adalah pengaturan XML untuk ekstensi.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[Type <String>]`: Menentukan tipe ekstensi.
      - `[TypeHandlerVersion <String>]`: Menentukan versi ekstensi. Menentukan versi ekstensi. Jika elemen ini tidak ditentukan atau tanda bintang (*) digunakan sebagai nilai, versi terbaru ekstensi digunakan. Jika nilai ditentukan dengan nomor versi utama dan tanda bintang sebagai nomor versi minor (X.), versi minor terbaru dari versi utama yang ditentukan akan dipilih. Jika nomor versi utama dan nomor versi minor ditentukan (X.Y), versi ekstensi tertentu dipilih. Jika versi ditentukan, pemutakhiran otomatis dijalankan pada contoh peran.
  - `[NetworkProfile <ICloudServiceNetworkProfile>]`: Profil Jaringan untuk layanan awan.
    - `[LoadBalancerConfiguration <ILoadBalancerConfiguration[]>]`: Daftar konfigurasi Penyeimbang muat. Layanan awan dapat memiliki hingga dua konfigurasi penyeimbang muat, yang terkait dengan Public Load Balancer dan Internal Load Balancer.
      - `FrontendIPConfiguration <ILoadBalancerFrontendIPConfiguration[]>`: Menentukan IP frontend yang akan digunakan untuk penyeimbang muat. Hanya alamat IP frontend IPv4 yang didukung. Setiap konfigurasi penyeimbang muat harus memiliki satu konfigurasi IP frontend.
        - `Name <String>`: Nama sumber daya yang unik dalam kumpulan konfigurasi IP frontend yang digunakan oleh penyeimbang muat. Nama ini bisa digunakan untuk mengakses sumber daya.
        - `[PrivateIPAddress <String>]`: Alamat IP privat jaringan virtual konfigurasi IP.
        - `[PublicIPAddressId <String>]`: Id Sumber Daya
        - `[SubnetId <String>]`: Id Sumber Daya
      - `Name <String>`: Nama Penyeimbang muat
      - `[Id <String>]`: Id Sumber Daya
    - `[SwappableCloudService <ISubResource>]`: Id reference of the cloud service containing the target IP with which the subject cloud service can perform a swap. Properti ini tidak dapat diperbarui setelah diatur. Layanan awan yang dapat menukar yang dirujuk oleh id ini harus ada jika tidak kesalahan akan dilakukan.
      - `[Id <String>]`: Id Sumber Daya
  - `[OSProfile <ICloudServiceOSProfile>]`: Menjelaskan profil OS untuk layanan awan.
    - `[Secret <ICloudServiceVaultSecretGroup[]>]`: Menentukan kumpulan sertifikat yang harus diinstal menjadi contoh peran.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[VaultCertificate <ICloudServiceVaultCertificate[]>]`: Daftar referensi kunci vault dalam SourceVault yang berisi sertifikat.
        - `[CertificateUrl <String>]`: URL sertifikat berikut telah diunggah ke Key Vault sebagai rahasia.
  - `[PackageUrl <String>]`: Menentukan URL yang merujuk ke lokasi paket layanan dalam layanan Blob. URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (Sas, Shared Access Signature) dari akun penyimpanan apa pun.         Ini adalah properti khusus untuk menulis dan tidak dikembalikan dalam panggilan GET.
  - `[RoleProfile <ICloudServiceRoleProfile>]`: Menjelaskan profil peran untuk layanan awan.
    - `[Role <ICloudServiceRoleProfileProperties[]>]`: Daftar peran untuk layanan awan.
      - `[Name <String>]`: Nama sumber daya.
      - `[SkuCapacity <Int64?>]`: Menentukan jumlah instans peran di layanan awan.
      - `[SkuName <String>]`: Nama sku. CATATAN: Jika SKU baru tidak didukung pada perangkat keras layanan awan saat ini, Anda harus menghapus dan membuat ulang layanan awan atau kembali ke sku lama.
      - `[SkuTier <String>]`: Menentukan tingkatan layanan awan. Nilai yang Mungkin adalah <br /><br /> **Standar** <br /><br /> **Dasar**
  - `[StartCloudService <Boolean?>]`: (Opsional) Menunjukkan apakah akan memulai layanan awan segera setelah dibuat. Nilai defaultnya adalah `true` .         Jika false, model layanan masih digunakan, tapi kode tidak langsung dijalankan. Sebaliknya, layanan didukungOff hingga Anda menghubungi Mulai, pada saat layanan akan dimulai. Layanan yang disebarkan masih menimbulkan biaya, bahkan jika didukung.
  - `[Tag <ICloudServiceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[UpgradeMode <CloudServiceUpgradeMode?>]`: Mode pembaruan untuk layanan awan. Contoh peran dialokasikan untuk memperbarui domain ketika layanan digunakan. Pembaruan dapat dimulai secara manual dalam setiap domain pembaruan atau dimulai secara otomatis di semua domain pembaruan.         Nilai yang Mungkin adalah <br /><br />**Otomatis**<br /><br />**Manual** <br /><br />**Bersamaan**<br /><br />         Jika tidak ditentukan, nilai defaultnya adalah Otomatis. Jika diset ke Manual, PUT UpdateDomain harus dipanggil untuk menerapkan pembaruan. Jika diset ke Otomatis, pembaruan otomatis diterapkan ke setiap pembaruan domain secara berurutan.

## RELATED LINKS

