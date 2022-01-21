---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/get-azcloudservicenetworkinterfaces
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceNetworkInterfaces.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Get-AzCloudServiceNetworkInterfaces.md
ms.openlocfilehash: 5254696d257c3f612dbc102b2dee584ef4e2ee0f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136561526"
---
# Get-AzCloudServiceNetworkInterfaces

## SYNOPSIS
Dapatkan antarmuka jaringan dari layanan awan.

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
Dapatkan antarmuka jaringan dari layanan awan.

## EXAMPLES

### Contoh 1: Dapatkan antarmuka jaringan dengan nama layanan cloud
```powershell
PS C:\> Get-AzCloudServiceNetworkInterfaces -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca

```

Mendapatkan semua antarmuka jaringan untuk nama layanan awan tertentu.

### Contoh 2: Dapatkan antarmuka jaringan dengan objek layanan awan
```powershell
PS C:\> $cs = Get-AzCloudService -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
PS C:\> Get-AzCloudServiceNetworkInterfaces -CloudService $cs

```

Mendapatkan semua antarmuka jaringan untuk objek layanan awan tertentu.

### Contoh 3: Dapatkan antarmuka jaringan dengan objek layanan cloud dan nama contoh peran.
```powershell
PS C:\> Get-AzCloudServiceNetworkInterfaces -CloudService $cs -RoleInstanceName WebRole1_IN_0

```

Mendapatkan semua antarmuka jaringan untuk objek layanan awan dan nama contoh peran yang diberikan.

## PARAMETERS

### -CloudService
CloudService instance.
Untuk membuat, lihat bagian CATATAN untuk properti CLOUDSERVICE dan membuat tabel hash.

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
Langganan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CLOUDSERVICE <CloudService> : CloudService instance.
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

