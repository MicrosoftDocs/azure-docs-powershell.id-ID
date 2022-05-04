---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/update-azcloudservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Update-AzCloudService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Update-AzCloudService.md
ms.openlocfilehash: a05d725ea790033cca33f4ccea5d6b2257818556
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144649660"
---
# Update-AzCloudService

## SYNOPSIS
Membuat atau memperbarui layanan awan.
Harap dicatat bahwa beberapa properti hanya dapat diatur selama pembuatan layanan awan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cloudservice/update-azcloudservice) untuk informasi terbaru.

## SYNTAX

```
Update-AzCloudService -InputObject <ICloudServiceIdentity> -Parameter <ICloudService>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui layanan awan.
Harap dicatat bahwa beberapa properti hanya dapat diatur selama pembuatan layanan awan.

## EXAMPLES

### Contoh 1: Menambahkan ekstensi RDP ke layanan cloud yang ada
```powershell
# Create RDP extension object
$rdpExtension = New-AzCloudServiceRemoteDesktopExtensionObject -Name "RDPExtension" -Credential $credential -Expiration $expiration -TypeHandlerVersion "1.2.1"
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"
# Add RDP extension to existing cloud service extension object
$cloudService.ExtensionProfile.Extension = $cloudService.ExtensionProfile.Extension + $rdpExtension
# Update cloud service
$cloudService | Update-AzCloudService
```

Kumpulan perintah di atas menambahkan ekstensi RDP ke layanan cloud yang sudah ada bernama ContosoCS yang termasuk dalam grup sumber daya bernama ContosOrg.

### Contoh 2: Menghapus semua ekstensi dari layanan cloud
```powershell
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"
# Set extension to empty list
$cloudService.ExtensionProfile.Extension = @()
# Update cloud service
$cloudService | Update-AzCloudService
```

Kumpulan perintah di atas menghapus semua ekstensi dari layanan cloud yang ada bernama ContosoCS yang termasuk dalam grup sumber daya bernama ContosOrg.

### Contoh 3: Menghapus ekstensi RDP dari layanan cloud
```powershell
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"
# Remove extension by name RDPExtension
$cloudService.ExtensionProfile.Extension = $cloudService.ExtensionProfile.Extension | Where-Object { $_.Name -ne "RDPExtension" }
# Update cloud service
$cloudService | Update-AzCloudService
```

Kumpulan perintah di atas menghapus ekstensi RDP dari layanan cloud yang ada bernama ContosoCS yang termasuk dalam grup sumber daya bernama ContosOrg.

### Contoh 4: instans peran Scale-Out / Scale-In
```powershell
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"

# Scale-out all role instance count by 1
$cloudService.RoleProfile.Role | ForEach-Object {$_.SkuCapacity += 1}

# Scale-in ContosoFrontend role instance count by 1
$role = $cloudService.RoleProfile.Role | Where-Object {$_.Name -eq "ContosoFrontend"}
$role.SkuCapacity -= 1

# Update cloud service configuration as per the new role instance count
$cloudService.Configuration = $configuration

# Update cloud service
$cloudService | Update-AzCloudService
```

Kumpulan perintah di atas menunjukkan cara menskalakan dan menskalakan jumlah instans peran untuk layanan cloud bernama ContosoCS yang termasuk dalam grup sumber daya bernama ContosOrg.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICloudServiceIdentity>: Parameter Identitas
  - `[CloudServiceName <String>]`: 
  - `[IPConfigurationName <String>]`: Nama konfigurasi IP.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi yang berkaitan dengan versi OS.
  - `[NetworkInterfaceName <String>]`: Nama antarmuka jaringan.
  - `[OSFamilyName <String>]`: Nama keluarga OS.
  - `[OSVersionName <String>]`: Nama versi OS.
  - `[PublicIPAddressName <String>]`: Nama Alamat IP publik.
  - `[ResourceGroupName <String>]`: 
  - `[RoleInstanceName <String>]`: Nama instans peran.
  - `[RoleName <String>]`: Nama peran.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[UpdateDomain <Int32?>]`: Menentukan nilai bilangan bulat yang mengidentifikasi domain pembaruan. Domain pembaruan diidentifikasi dengan indeks berbasis nol: domain pembaruan pertama memiliki ID 0, yang kedua memiliki ID 1, dan sebagainya.

PARAMETER <ICloudService>: Menjelaskan layanan cloud.
  - `Location <String>`: Lokasi sumber daya.
  - `[AllowModelOverride <Boolean?>]`: (Opsional) Menunjukkan apakah properti sku peran (roleProfile.roles.sku) yang ditentukan dalam model/templat harus mengganti jumlah instans peran dan ukuran vm yang ditentukan dalam .cscfg dan .csdef masing-masing.         Nilai default-nya adalah `false`.
  - `[Configuration <String>]`: Menentukan konfigurasi layanan XML (.cscfg) untuk layanan cloud.
  - `[ConfigurationUrl <String>]`: Menentukan URL yang mengacu pada lokasi konfigurasi layanan di Blob service. URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun.         Ini adalah properti hanya-tulis dan tidak dikembalikan dalam panggilan GET.
  - `[ExtensionProfile <ICloudServiceExtensionProfile>]`: Menjelaskan profil ekstensi layanan cloud.
    - `[Extension <IExtension[]>]`: Daftar ekstensi untuk layanan cloud.
      - `[AutoUpgradeMinorVersion <Boolean?>]`: Secara eksplisit menentukan apakah platform dapat secara otomatis meningkatkan typeHandlerVersion ke versi minor yang lebih tinggi ketika tersedia.
      - `[ForceUpdateTag <String>]`: Tag untuk memaksa menerapkan pengaturan publik dan terlindungi yang disediakan.         Mengubah nilai tag memungkinkan untuk menjalankan kembali ekstensi tanpa mengubah pengaturan publik atau terlindungi.         Jika forceUpdateTag tidak diubah, pembaruan untuk pengaturan publik atau terproteksi masih akan diterapkan oleh handler.         Jika tidak ada forceUpdateTag atau pengaturan publik atau terproteksi yang berubah, ekstensi akan mengalir ke instans peran dengan nomor urutan yang sama, dan terserah implementasi handler apakah akan menjalankannya kembali atau tidak
      - `[Name <String>]`: Nama ekstensi.
      - `[ProtectedSetting <String>]`: Pengaturan terproteksi untuk ekstensi yang dienkripsi sebelum dikirim ke instans peran.
      - `[ProtectedSettingFromKeyVaultSecretUrl <String>]`: 
      - `[Publisher <String>]`: Nama penerbit handler ekstensi.
      - `[RolesAppliedTo <String[]>]`: Daftar peran opsional untuk menerapkan ekstensi ini. Jika properti tidak ditentukan atau '*' ditentukan, ekstensi diterapkan ke semua peran dalam layanan cloud.
      - `[Setting <String>]`: Pengaturan publik untuk ekstensi. Untuk ekstensi JSON, ini adalah pengaturan JSON untuk ekstensi. Untuk Ekstensi XML (seperti RDP), ini adalah pengaturan XML untuk ekstensi.
      - `[SourceVaultId <String>]`: Id Sumber Daya
      - `[Type <String>]`: Menentukan jenis ekstensi.
      - `[TypeHandlerVersion <String>]`: Menentukan versi ekstensi. Menentukan versi ekstensi. Jika elemen ini tidak ditentukan atau tanda bintang (*) digunakan sebagai nilai, versi terbaru ekstensi digunakan. Jika nilai ditentukan dengan nomor versi utama dan tanda bintang sebagai nomor versi minor (X.), versi minor terbaru dari versi utama yang ditentukan dipilih. Jika nomor versi utama dan nomor versi minor ditentukan (X.Y), versi ekstensi tertentu dipilih. Jika versi ditentukan, peningkatan otomatis dilakukan pada instans peran.
  - `[NetworkProfile <ICloudServiceNetworkProfile>]`: Profil Jaringan untuk layanan cloud.
    - `[LoadBalancerConfiguration <ILoadBalancerConfiguration[]>]`: Daftar konfigurasi Load balancer. Layanan cloud dapat memiliki hingga dua konfigurasi penyeimbang beban, sesuai dengan Load Balancer Publik dan Load Balancer Internal.
      - `FrontendIPConfiguration <ILoadBalancerFrontendIPConfiguration[]>`: Menentukan IP frontend yang akan digunakan untuk load balancer. Hanya alamat IP frontend IPv4 yang didukung. Setiap konfigurasi load balancer harus memiliki tepat satu konfigurasi IP frontend.
        - `Name <String>`: Nama sumber daya yang unik dalam kumpulan konfigurasi IP frontend yang digunakan oleh load balancer. Nama ini dapat digunakan untuk mengakses sumber daya.
        - `[PrivateIPAddress <String>]`: Alamat IP privat jaringan virtual dari konfigurasi IP.
        - `[PublicIPAddressId <String>]`: Id Sumber Daya
        - `[SubnetId <String>]`: Id Sumber Daya
      - `Name <String>`: Nama Load balancer
      - `[Id <String>]`: Id Sumber Daya
    - `[SwappableCloudService <ISubResource>]`: Referensi id dari layanan awan yang berisi IP target tempat layanan cloud subjek dapat melakukan pertukaran. Properti ini tidak dapat diperbarui setelah diatur. Layanan cloud yang dapat ditukar yang dirujuk oleh id ini harus ada jika tidak, kesalahan akan dilemparkan.
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
  - `[StartCloudService <Boolean?>]`: (Opsional) Menunjukkan apakah akan segera memulai layanan cloud setelah dibuat. Nilai default-nya adalah `true`.         Jika false, model layanan masih disebarkan, tetapi kode tidak segera dijalankan. Sebagai gantinya, layanan ini Adalah PoweredOff sampai Anda memanggil Mulai, pada saat layanan akan dimulai. Layanan yang disebarkan masih dikenakan biaya, bahkan jika itu dimatikan.
  - `[Tag <ICloudServiceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[UpgradeMode <CloudServiceUpgradeMode?>]`: Perbarui mode untuk layanan awan. Instans peran dialokasikan untuk memperbarui domain saat layanan disebarkan. Pembaruan dapat dimulai secara manual di setiap domain pembaruan atau dimulai secara otomatis di semua domain pembaruan.         Nilai yang Mungkin adalah <br /><br />**Auto**<br /><br />**Manual** <br /><br />**Simultan**<br /><br />         Jika tidak ditentukan, nilai defaultnya adalah Otomatis. Jika diatur ke Manual, PUT UpdateDomain harus dipanggil untuk menerapkan pembaruan. Jika diatur ke Otomatis, pembaruan secara otomatis diterapkan ke setiap domain pembaruan secara berurutan.

## RELATED LINKS

