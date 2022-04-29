---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/Switch-AzCloudService
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Switch-AzCloudService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Switch-AzCloudService.md
ms.openlocfilehash: 8534469b984577e5b2e43cc67a57623f938088ea
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144240247"
---
# Switch-AzCloudService

## SYNOPSIS
Menukar VIP antara dua penyeimbang beban layanan cloud (dukungan diperpanjang).

## SYNTAX

### CloudServiceName (Default)
```
Switch-AzCloudService -CloudServiceName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Async] [-DefaultProfile <PSObject>] [-AsJob] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### CloudService
```
Switch-AzCloudService -CloudService <CloudService> [-SubscriptionId <String>] [-Async]
 [-DefaultProfile <PSObject>] [-AsJob] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menukar VIP antara dua penyeimbang beban layanan cloud (dukungan diperpanjang).

## EXAMPLES

### Contoh 1: Beralih layanan cloud menggunakan nama
```powershell
Switch-AzCloudService -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
```

Perintah di atas memanggil operasi vipswap pada layanan Cloud dengan nama 'BService' dan akan melakukan operasi setelah pengguna mengonfirmasi tindakan pada prompt konfirmasi.
'BService' dengan ditukar dengan layanan cloudnya yang dapat ditukar.

### Contoh 2: Beralih layanan cloud menggunakan objek layanan cloud
```powershell
$cs = Get-AzCloudService -ResourceGroupName "BRGThree" -CloudServiceName BService -SubscriptionId 1133e0eb-b53c-1234-b478-2eac8f04afca
Switch-AzCloudService -CloudService $cs
```

Perintah di atas memanggil operasi vipswap pada layanan Cloud dengan nama 'BService' dan akan melakukan operasi setelah pengguna mengonfirmasi tindakan pada prompt konfirmasi.
'BService' dengan ditukar dengan layanan cloudnya yang dapat ditukar.

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

### -Asinkron


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

### -CloudService
Untuk membuat, lihat bagian CATATAN untuk properti CLOUDSERVICE dan buat tabel hash.

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

### -ResourceGroupName


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

### -SubscriptionId
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CLOUDSERVICE <CloudService>: 
  - `Location <String>`: Lokasi sumber daya.
  - `[AllowModelOverride <Boolean?>]`: (Opsional) Menunjukkan apakah properti sku peran (roleProfile.roles.sku) yang ditentukan dalam model/templat harus mengganti jumlah instans peran dan ukuran vm yang ditentukan dalam .cscfg dan .csdef masing-masing.         Nilai default-nya adalah `false`.
  - `[Configuration <String>]`: Menentukan konfigurasi layanan XML (.cscfg) untuk layanan cloud.
  - `[ConfigurationUrl <String>]`: Menentukan URL yang mengacu pada lokasi konfigurasi layanan di blob service. URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun.         Ini adalah properti tulis-saja dan tidak dikembalikan dalam panggilan GET.
  - `[ExtensionProfile <ICloudServiceExtensionProfile>]`: Menjelaskan profil ekstensi layanan cloud.
    - `[Extension <IExtension[]>]`: Daftar ekstensi untuk layanan awan.
      - `[AutoUpgradeMinorVersion <Boolean?>]`: Secara eksplisit menentukan apakah platform dapat secara otomatis meningkatkan typeHandlerVersion ke versi minor yang lebih tinggi ketika tersedia.
      - `[ForceUpdateTag <String>]`: Tag untuk memaksa menerapkan pengaturan publik dan terlindungi yang disediakan.         Mengubah nilai tag memungkinkan untuk menjalankan kembali ekstensi tanpa mengubah pengaturan publik atau terlindungi.         Jika forceUpdateTag tidak diubah, pembaruan pada pengaturan publik atau terlindungi akan tetap diterapkan oleh handler.         Jika tidak ada forceUpdateTag atau pengaturan publik atau terproteksi yang berubah, ekstensi akan mengalir ke instans peran dengan nomor urutan yang sama, dan terserah implementasi handler apakah akan menjalankannya kembali atau tidak
      - `[Name <String>]`: Nama ekstensi.
      - `[ProtectedSetting <String>]`: Pengaturan terproteksi untuk ekstensi yang dienkripsi sebelum dikirim ke instans peran.
      - `[ProtectedSettingFromKeyVaultSecretUrl <String>]`: 
      - `[Publisher <String>]`: Nama penerbit handler ekstensi.
      - `[RolesAppliedTo <String[]>]`: Daftar peran opsional untuk menerapkan ekstensi ini. Jika properti tidak ditentukan atau '*' ditentukan, ekstensi diterapkan ke semua peran dalam layanan awan.
      - `[Setting <String>]`: Pengaturan publik untuk ekstensi. Untuk ekstensi JSON, ini adalah pengaturan JSON untuk ekstensi. Untuk Ekstensi XML (seperti RDP), ini adalah pengaturan XML untuk ekstensi.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[Type <String>]`: Menentukan jenis ekstensi.
      - `[TypeHandlerVersion <String>]`: Menentukan versi ekstensi. Menentukan versi ekstensi. Jika elemen ini tidak ditentukan atau tanda bintang (*) digunakan sebagai nilai, versi terbaru ekstensi akan digunakan. Jika nilai ditentukan dengan nomor versi utama dan tanda bintang sebagai nomor versi minor (X.), versi minor terbaru dari versi utama yang ditentukan dipilih. Jika nomor versi utama dan nomor versi minor ditentukan (X.Y), versi ekstensi tertentu dipilih. Jika versi ditentukan, peningkatan otomatis dilakukan pada instans peran.
  - `[NetworkProfile <ICloudServiceNetworkProfile>]`: Profil Jaringan untuk layanan cloud.
    - `[LoadBalancerConfiguration <ILoadBalancerConfiguration[]>]`: Daftar konfigurasi Load balancer. Layanan cloud dapat memiliki hingga dua konfigurasi load balancer, sesuai dengan Load Balancer Publik dan Load Balancer Internal.
      - `FrontendIPConfiguration <ILoadBalancerFrontendIPConfiguration[]>`: Menentukan IP frontend yang akan digunakan untuk load balancer. Hanya alamat IP frontend IPv4 yang didukung. Setiap konfigurasi load balancer harus memiliki tepat satu konfigurasi IP frontend.
        - `Name <String>`: Nama sumber daya yang unik dalam kumpulan konfigurasi IP frontend yang digunakan oleh load balancer. Nama ini dapat digunakan untuk mengakses sumber daya.
        - `[PrivateIPAddress <String>]`: Alamat IP privat jaringan virtual dari konfigurasi IP.
        - `[PublicIPAddressId <String>]`: Id Sumber Daya
        - `[SubnetId <String>]`: Id Sumber Daya
      - `Name <String>`: Nama Load balancer
      - `[Id <String>]`: Id Sumber Daya
    - `[SwappableCloudService <ISubResource>]`: Referensi id layanan awan yang berisi IP target tempat layanan cloud subjek dapat melakukan pertukaran. Properti ini tidak dapat diperbarui setelah diatur. Layanan cloud yang dapat ditukar yang dirujuk oleh id ini harus ada jika tidak, kesalahan akan dilemparkan.
      - `[Id <String>]`: Id Sumber Daya
  - `[OSProfile <ICloudServiceOSProfile>]`: Menjelaskan profil OS untuk layanan awan.
    - `[Secret <ICloudServiceVaultSecretGroup[]>]`: Menentukan sekumpulan sertifikat yang harus diinstal ke instans peran.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[VaultCertificate <ICloudServiceVaultCertificate[]>]`: Daftar referensi brankas kunci di SourceVault yang berisi sertifikat.
        - `[CertificateUrl <String>]`: Ini adalah URL sertifikat yang telah diunggah ke Key Vault sebagai rahasia.
  - `[PackageUrl <String>]`: Menentukan URL yang mengacu pada lokasi paket layanan di Blob service. URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun.         Ini adalah properti tulis-saja dan tidak dikembalikan dalam panggilan GET.
  - `[RoleProfile <ICloudServiceRoleProfile>]`: Menjelaskan profil peran untuk layanan awan.
    - `[Role <ICloudServiceRoleProfileProperties[]>]`: Daftar peran untuk layanan awan.
      - `[Name <String>]`: Nama sumber daya.
      - `[SkuCapacity <Int64?>]`: Menentukan jumlah instans peran di layanan cloud.
      - `[SkuName <String>]`: Nama sku. CATATAN: Jika SKU baru tidak didukung pada perangkat keras tempat layanan cloud saat ini aktif, Anda perlu menghapus dan membuat ulang layanan cloud atau kembali ke sku lama.
      - `[SkuTier <String>]`: Menentukan tingkat layanan cloud. Nilai yang Mungkin adalah <br /><br /> **Standard** <br /><br /> **Dasar**
  - `[StartCloudService <Boolean?>]`: (Opsional) Menunjukkan apakah akan memulai layanan cloud segera setelah dibuat. Nilai default-nya adalah `true`.         Jika false, model layanan masih disebarkan, tetapi kode tidak segera dijalankan. Sebagai gantinya, layanan ini adalah PoweredOff sampai Anda memanggil Mulai, pada saat itu layanan akan dimulai. Layanan yang disebarkan masih dikenakan biaya, bahkan jika diberdayakan.
  - `[Tag <ICloudServiceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[UpgradeMode <CloudServiceUpgradeMode?>]`: Perbarui mode untuk layanan awan. Instans peran dialokasikan untuk memperbarui domain saat layanan disebarkan. Pembaruan dapat dimulai secara manual di setiap domain pembaruan atau dimulai secara otomatis di semua domain pembaruan.         Nilai yang Mungkin adalah <br /><br />**Auto**<br /><br />**Manual** <br /><br />**Simultan**<br /><br />         Jika tidak ditentukan, nilai defaultnya adalah Otomatis. Jika diatur ke Manual, PUT UpdateDomain harus dipanggil untuk menerapkan pembaruan. Jika diatur ke Otomatis, pembaruan secara otomatis diterapkan ke setiap domain pembaruan secara berurutan.

## RELATED LINKS

