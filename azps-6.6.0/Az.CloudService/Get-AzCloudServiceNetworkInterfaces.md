---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudservicenetworkinterfaces
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceNetworkInterfaces.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceNetworkInterfaces.md
ms.openlocfilehash: 6e4a4f38b2824b85a61a5a16d2225ce28b7b0984
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141871952"
---
# Get-AzCloudServiceNetworkInterfaces

## SYNOPSIS
Dapatkan antarmuka jaringan layanan awan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cloudservice/get-azcloudservicenetworkinterfaces) untuk informasi terbaru.

## SYNTAX

### CloudServiceName (Default)
```
Get-AzCloudServiceNetworkInterfaces -CloudServiceName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-RoleInstanceName <String>] [<CommonParameters>]
```

### CloudService
```
Get-AzCloudServiceNetworkInterfaces -CloudService <CloudService> [-SubscriptionId <String>]
 [-RoleInstanceName <String>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan antarmuka jaringan layanan awan.

## EXAMPLES

### Contoh 1: Mendapatkan antarmuka jaringan dengan nama layanan awan
```powershell
PS C:\> Get-AzCloudServiceNetworkInterfaces -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca

```

Mendapatkan semua antarmuka jaringan untuk nama layanan awan tertentu.

### Contoh 2: Mendapatkan antarmuka jaringan menurut objek layanan awan
```powershell
PS C:\> $cs = Get-AzCloudService -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
PS C:\> Get-AzCloudServiceNetworkInterfaces -CloudService $cs

```

Mendapatkan semua antarmuka jaringan untuk objek layanan awan tertentu.

### Contoh 3: Dapatkan antarmuka jaringan menurut objek layanan awan dan nama contoh peran.
```powershell
PS C:\> Get-AzCloudServiceNetworkInterfaces -CloudService $cs -RoleInstanceName WebRole1_IN_0

```

Mendapatkan semua antarmuka jaringan untuk objek layanan awan dan nama contoh peran tertentu.

## PARAMETERS

### -CloudService
Contoh CloudService.
Untuk membangun, lihat bagian CATATAN untuk properti CLOUDSERVICE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.CloudService
Parameter Sets: CloudService
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudServiceName
CloudServiceName.

```yaml
Type: System.String
Parameter Sets: CloudServiceName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
ResourceGroupName.

```yaml
Type: System.String
Parameter Sets: CloudServiceName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleInstanceName
RoleInstanceName.

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
Berlangganan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CLOUDSERVICE <CloudService>: Instans CloudService.
  - `Location <String>`: Lokasi sumber daya.
  - `[AllowModelOverride <Boolean?>]`: (Opsional) Menunjukkan apakah role sku properties (roleProfile.roles.sku) yang ditentukan dalam model/template harus mengganti jumlah contoh peran dan ukuran vm yang ditentukan dalam .cscfg dan .csdef secara berurutan.         Nilai defaultnya adalah `false`.
  - `[Configuration <String>]`: Menentukan konfigurasi layanan XML (.cscfg) untuk layanan awan.
  - `[ConfigurationUrl <String>]`: Menentukan URL yang merujuk ke lokasi konfigurasi layanan dalam layanan Blob. URL paket layanan dapat berupa URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun.         Ini adalah properti write-only dan tidak dikembalikan dalam panggilan GET.
  - `[ExtensionProfile <ICloudServiceExtensionProfile>]`: Menjelaskan profil ekstensi layanan awan.
    - `[Extension <IExtension[]>]`: Daftar ekstensi untuk layanan awan.
      - `[AutoUpgradeMinorVersion <Boolean?>]`: Secara eksplisit menentukan apakah platform dapat secara otomatis memutakhirkan typeHandlerVersion ke versi minor yang lebih tinggi ketika tersedia.
      - `[ForceUpdateTag <String>]`: Tag untuk menerapkan pengaturan publik dan terproteksi yang disediakan.         Mengubah nilai tag memungkinkan untuk menjalankan kembali ekstensi tanpa mengubah pengaturan publik atau yang diproteksi.         Jika forceUpdateTag tidak diubah, pembaruan untuk pengaturan publik atau terproteksi masih akan diterapkan oleh handler.         Jika tidak ada forceUpdateTag maupun perubahan pengaturan publik atau terproteksi, ekstensi akan mengalir ke contoh peran dengan nomor urutan yang sama, dan terserah implementasi handler apakah akan menjalankannya kembali atau tidak
      - `[Name <String>]`: Nama ekstensi.
      - `[ProtectedSetting <String>]`: Pengaturan terproteksi untuk ekstensi yang dienkripsi sebelum dikirim ke contoh peran.
      - `[ProtectedSettingFromKeyVaultSecretUrl <String>]`: 
      - `[Publisher <String>]`: Nama penerbit pengatur ekstensi.
      - `[RolesAppliedTo <String[]>]`: Daftar peran opsional untuk menerapkan ekstensi ini. Jika properti tidak ditentukan atau '*' ditentukan, ekstensi diterapkan ke semua peran dalam layanan awan.
      - `[Setting <String>]`: Pengaturan publik untuk ekstensi. Untuk ekstensi JSON, ini adalah pengaturan JSON untuk ekstensi. Untuk Ekstensi XML (seperti RDP), ini adalah pengaturan XML untuk ekstensi tersebut.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[Type <String>]`: Menentukan tipe ekstensi.
      - `[TypeHandlerVersion <String>]`: Menentukan versi ekstensi. Menentukan versi ekstensi. Jika elemen ini tidak ditentukan atau tanda bintang (*) digunakan sebagai nilai, versi terbaru ekstensi digunakan. Jika nilai ditentukan dengan nomor versi utama dan tanda bintang sebagai nomor versi minor (X.), versi minor terbaru dari versi utama yang ditentukan dipilih. Jika nomor versi utama dan nomor versi minor ditentukan (X.Y), versi ekstensi tertentu dipilih. Jika versi ditentukan, pemutakhiran otomatis dilakukan pada contoh peran.
  - `[NetworkProfile <ICloudServiceNetworkProfile>]`: Profil Jaringan untuk layanan awan.
    - `[LoadBalancerConfiguration <ILoadBalancerConfiguration[]>]`: Daftar konfigurasi Load balancer. Layanan cloud dapat memiliki hingga dua konfigurasi penyeimbang muatan, yang terkait dengan Load Balancer Publik dan Load Balancer Internal.
      - `FrontendIPConfiguration <ILoadBalancerFrontendIPConfiguration[]>`: Menentukan IP frontend yang akan digunakan untuk load balancer. Hanya alamat IP frontend IPv4 yang didukung. Setiap konfigurasi load balancer harus benar-benar memiliki satu konfigurasi IP frontend.
        - `Name <String>`: Nama sumber daya yang unik dalam rangkaian konfigurasi IP frontend yang digunakan oleh penyeimbang muatan. Nama ini bisa digunakan untuk mengakses sumber daya.
        - `[PrivateIPAddress <String>]`: Alamat IP privat jaringan virtual konfigurasi IP.
        - `[PublicIPAddressId <String>]`: Id Sumber Daya
        - `[SubnetId <String>]`: Id Sumber Daya
      - `Name <String>`: Nama Penyeimbang muat
      - `[Id <String>]`: Id Sumber Daya
    - `[SwappableCloudService <ISubResource>]`: Referensi id layanan awan yang berisi IP target tempat layanan cloud subjek dapat melakukan swap. Properti ini tidak dapat diperbarui setelah diatur. Layanan cloud yang dapat ditukar yang dirujuk oleh id ini harus ada jika tidak, kesalahan akan dilemparkan.
      - `[Id <String>]`: Id Sumber Daya
  - `[OSProfile <ICloudServiceOSProfile>]`: Menjelaskan profil OS untuk layanan awan.
    - `[Secret <ICloudServiceVaultSecretGroup[]>]`: Menentukan sekumpulan sertifikat yang harus diinstal ke contoh peran.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[VaultCertificate <ICloudServiceVaultCertificate[]>]`: Daftar referensi kubah kunci di SourceVault yang berisi sertifikat.
        - `[CertificateUrl <String>]`: Ini adalah URL sertifikat yang telah diunggah ke Key Vault sebagai rahasia.
  - `[PackageUrl <String>]`: Menentukan URL yang merujuk ke lokasi paket layanan dalam layanan Blob. URL paket layanan dapat berupa URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun.         Ini adalah properti write-only dan tidak dikembalikan dalam panggilan GET.
  - `[RoleProfile <ICloudServiceRoleProfile>]`: Menjelaskan profil peran untuk layanan awan.
    - `[Role <ICloudServiceRoleProfileProperties[]>]`: Daftar peran untuk layanan awan.
      - `[Name <String>]`: Nama sumber daya.
      - `[SkuCapacity <Int64?>]`: Menentukan jumlah contoh peran di layanan awan.
      - `[SkuName <String>]`: Nama sku. CATATAN: Jika SKU baru tidak didukung pada perangkat keras yang saat ini aktif, Anda perlu menghapus dan membuat ulang layanan awan atau kembali ke sku lama.
      - `[SkuTier <String>]`: Menentukan tingkat layanan cloud. Nilai yang Memungkinkan adalah <br /><br /> **Standar** <br /><br /> **Dasar**
  - `[StartCloudService <Boolean?>]`: (Opsional) Menunjukkan apakah akan memulai layanan awan segera setelah dibuat. Nilai defaultnya adalah `true`.         Jika false, model layanan masih digunakan, tetapi kode tidak segera dijalankan. Sebagai gantinya, layanan adalah PoweredOff hingga Anda menghubungi Mulai, pada saat itu layanan akan dimulai. Layanan yang disebarkan masih dikenakan biaya, bahkan jika dimatikan.
  - `[Tag <ICloudServiceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[UpgradeMode <CloudServiceUpgradeMode?>]`: Mode pembaruan untuk layanan awan. Contoh peran dialokasikan untuk memperbarui domain saat layanan digunakan. Pembaruan dapat dimulai secara manual di setiap domain pembaruan atau dimulai secara otomatis di semua domain pembaruan.         Nilai yang Memungkinkan adalah <br /><br />**Auto**<br /><br />**Manual** <br /><br />**Simultan**<br /><br />         Jika tidak ditentukan, nilai defaultnya adalah Otomatis. Jika diatur ke Manual, PUT UpdateDomain harus dipanggil untuk menerapkan pembaruan. Jika diatur ke Otomatis, pembaruan secara otomatis diterapkan ke setiap domain pembaruan secara berurutan.

## RELATED LINKS

