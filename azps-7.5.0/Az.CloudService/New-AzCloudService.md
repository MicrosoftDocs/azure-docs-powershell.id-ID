---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudService.md
ms.openlocfilehash: 23b15dfa8b5ffa2019ac86c474234c323b3ac1a4
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145738054"
---
# New-AzCloudService

## SYNOPSIS
Membuat atau memperbarui layanan awan.
Harap dicatat bahwa beberapa properti hanya dapat diatur selama pembuatan layanan cloud.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cloudservice/new-azcloudservice) untuk informasi terbaru.

## SYNTAX

### CreateExpanded (Default)
```
New-AzCloudService -Name <String> -ResourceGroupName <String> -Location <String> [-SubscriptionId <String>]
 [-AllowModelOverride] [-Configuration <String>] [-ConfigurationUrl <String>]
 [-ExtensionProfile <ICloudServiceExtensionProfile>] [-NetworkProfile <ICloudServiceNetworkProfile>]
 [-OSProfile <ICloudServiceOSProfile>] [-PackageUrl <String>] [-RoleProfile <ICloudServiceRoleProfile>]
 [-StartCloudService] [-Tag <Hashtable>] [-UpgradeMode <CloudServiceUpgradeMode>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### quickCreateParameterSetWithoutStorage
```
New-AzCloudService -Name <String> -ResourceGroupName <String> -ConfigurationFile <String>
 -DefinitionFile <String> -Location <String> -PackageUrl <String> [-SubscriptionId <String>]
 [-DnsName <String>] [-ExtensionProfile <ICloudServiceExtensionProfile>] [-KeyVaultName <String>]
 [-StartCloudService] [-Tag <Hashtable>] [-UpgradeMode <CloudServiceUpgradeMode>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### quickCreateParameterSetWithStorage
```
New-AzCloudService -Name <String> -ResourceGroupName <String> -ConfigurationFile <String>
 -DefinitionFile <String> -Location <String> -PackageFile <String> -StorageAccount <String>
 [-SubscriptionId <String>] [-DnsName <String>] [-ExtensionProfile <ICloudServiceExtensionProfile>]
 [-KeyVaultName <String>] [-StartCloudService] [-Tag <Hashtable>] [-UpgradeMode <CloudServiceUpgradeMode>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui layanan awan.
Harap dicatat bahwa beberapa properti hanya dapat diatur selama pembuatan layanan cloud.

## EXAMPLES

### Contoh 1: Membuat layanan awan baru dengan peran tunggal
```powershell
# Create role profile object
$role = New-AzCloudServiceRoleProfilePropertiesObject -Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
$roleProfile = @{role = @($role)}

# Create network profile object
$publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosOrg -Name ContosIp
$feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
$loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
$networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Read Configuration File
$cscfgFile = "<Path to cscfg configuration file>"
$cscfgContent = Get-Content $cscfgFile | Out-String

# Create cloud service
$cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -PackageUrl "https://xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"    `
                          -Configuration $cscfgContent                                  `
                          -UpgradeMode 'Auto'                                           `
                          -RoleProfile $roleProfile                                     `
                          -NetworkProfile $networkProfile
```

Set perintah di atas membuat layanan awan dengan peran tunggal

### Contoh 2: Membuat layanan awan baru dengan peran tunggal dan ekstensi RDP
```powershell
# Create role profile object
$role = New-AzCloudServiceRoleProfilePropertiesObject -Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
$roleProfile = @{role = @($role)}

# Create network profile object
$publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosoOrg -Name ContosIp
$feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
$loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
$networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Create RDP extension object
$credential = Get-Credential
$expiration = (Get-Date).AddYears(1)
$extension = New-AzCloudServiceRemoteDesktopExtensionObject -Name 'RDPExtension' -Credential $credential -Expiration $expiration -TypeHandlerVersion '1.2.1'
$extensionProfile = @{extension = @($extension)}

# Read Configuration File
$cscfgFile = "<Path to cscfg configuration file>"
$cscfgContent = Get-Content $cscfgFile | Out-String

# Create cloud service
$cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -PackageUrl "https://xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"    `
                          -Configuration $cscfgContent                                  `
                          -UpgradeMode 'Auto'                                           `
                          -RoleProfile $roleProfile                                     `
                          -NetworkProfile $networkProfile                               `
                          -ExtensionProfile $extensionProfile
```

Set perintah di atas membuat layanan cloud dengan peran tunggal dan ekstensi RDP

### Contoh 3: Membuat layanan cloud baru dengan peran tunggal dan sertifikat dari brankas kunci
```powershell
# Create role profile object
$role = New-AzCloudServiceRoleProfilePropertiesObject -Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
$roleProfile = @{role = @($role)}

# Create OS profile object
$keyVault = Get-AzKeyVault -ResourceGroupName ContosOrg -VaultName ContosKeyVault
$certificate=Get-AzKeyVaultCertificate -VaultName ContosKeyVault -Name ContosCert
$secretGroup = New-AzCloudServiceVaultSecretGroupObject -Id $keyVault.ResourceId -CertificateUrl $certificate.SecretId
$osProfile = @{secret = @($secretGroup)}

# Create network profile object
$publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosOrg -Name ContosIp
$feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
$loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
$networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Read Configuration File
$cscfgFile = "<Path to cscfg configuration file>"
 = Get-Content $cscfgFile | Out-String

# Create cloud service
$cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -PackageUrl "https://xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"    `
                          -Configuration $cscfgContent                                  `
                          -UpgradeMode 'Auto'                                           `
                          -RoleProfile $roleProfile                                     `
                          -NetworkProfile $networkProfile                               `
                          -OSProfile $osProfile
```

Set perintah di atas membuat layanan cloud dengan peran tunggal dan sertifikat dari brankas kunci.

### Contoh 4: Membuat layanan cloud baru dengan beberapa peran dan ekstensi
```powershell
# Create role profile object
$role1 = New-AzCloudServiceRoleProfilePropertiesObject -Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
$role2 = New-AzCloudServiceRoleProfilePropertiesObject -Name 'ContosoBackend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
$roleProfile = @{role = @($role1, $role2)}

# Create network profile object
$publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosOrg -Name ContosIp
$feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
$loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
$networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Create RDP extension object
$credential = Get-Credential
$expiration = (Get-Date).AddYears(1)
$rdpExtension = New-AzCloudServiceRemoteDesktopExtensionObject -Name 'RDPExtension' -Credential $credential -Expiration $expiration -TypeHandlerVersion '1.2.1'

# Create Geneva extension object
$genevaExtension = New-AzCloudServiceExtensionObject -Name GenevaExtension -Publisher Microsoft.Azure.Geneva -Type GenevaMonitoringPaaS -TypeHandlerVersion "2.14.0.2"
$extensionProfile = @{extension = @($rdpExtension, $genevaExtension)}

# Add tags
$tag=@{"Owner" = "Contoso"}

# Read Configuration File
$cscfgFile = "<Path to cscfg configuration file>"
$cscfgContent = Get-Content $cscfgFile | Out-String

# Create cloud service
$cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -PackageUrl "https://xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"    `
                          -Configuration $cscfgContent                                  `
                          -UpgradeMode 'Auto'                                           `
                          -RoleProfile $roleProfile                                     `
                          -NetworkProfile $networkProfile                               `
                          -ExtensionProfile $extensionProfile                           `
                          -Tag $tag
```

Set perintah di atas membuat layanan cloud dengan peran tunggal dan sertifikat dari brankas kunci.

### Contoh 5: Buat layanan cloud baru dengan file CsCfg, CsDef, dan Cspkg menggunakan set parameter 'quickCreateParameterSetWithStorage'.
```powershell
# Set up a storage account if you have not
$storageAccount = New-AzStorageAccount -ResourceGroupName ContosoOrg -Name ContosoStorAcc -Location "East US" -SkuName "Standard_RAGRS" -Kind "StorageV2"

# Create cloud service
$cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -ConfigurationFile C:\files\CS.cscfg                          `
                          -DefinitionFile C:\files\CS.csdef                             `
                          -PackageFile C:\CS.cspkg                                      `
                          -StorageAccount ContosoStorAcc                                `
                          -KeyVaultName ContosoKV

```

Set perintah di atas membuat layanan cloud dengan mengekstrak informasi NetworkProfile dan RoleProfile dari . CsCfg dan . File CsDef.

File-file tersebut juga akan memberikan informasi OSProfile bersama dengan Sertifikat dari keyvault yang disediakan dalam parameter '-KeyVaultName'.
Set parameter ini juga mengunggah . File CsPkg ke StorageAccount yang disediakan.

### Contoh 6: Buat layanan cloud baru dengan file CsCfg, CsDef, dan Cspkg menggunakan set parameter 'quickCreateParameterSetWithoutStorage'.
```powershell
# getting Package URL
$tokenStartTime = Get-Date 
$tokenEndTime = $tokenStartTime.AddYears(1) 
$storAcc = Get-AzStorageAccount -ResourceGroupName ContosoOrg -Name ContosoStorAcc
$csPkgBlob = Get-AzStorageBlob -Container Contoso-Container -Blob ContosoBlob.cspkg -Context $storAcc.Context
$csPkgToken = New-AzStorageBlobSASToken -Container Contoso-Container -Blob ContosoBlob.cspkg -Permission rwd -StartTime $tokenStartTime -ExpiryTime $tokenEndTime -Context $storAcc.Context
$cspkgUrl = $csPkgBlob.ICloudBlob.Uri.AbsoluteUri + $csPkgToken 

# Create cloud service
$cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -ConfigurationFile C:\files\CS.cscfg                          `
                          -DefinitionFile C:\files\CS.csdef                             `
                          -packageUrl $cspkgUrl                                         `

```

Set perintah di atas membuat layanan cloud dengan mengekstrak informasi NetworkProfile dan RoleProfile dari . CsCfg dan . File CsDef.

File-file tersebut juga akan memberikan informasi OSProfile bersama dengan Sertifikat dari keyvault yang disediakan dalam parameter '-KeyVaultName'.

## PARAMETERS

### -AllowModelOverride
(Opsional) Menunjukkan apakah properti sku peran (roleProfile.roles.sku) yang ditentukan dalam model/templat harus mengambil alih jumlah instans peran dan ukuran vm yang ditentukan dalam .cscfg dan .csdef masing-masing. Nilai defaultnya adalah `false`.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Jalankan perintah sebagai pekerjaan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfigurasi
Menentukan konfigurasi layanan XML (.cscfg) untuk layanan cloud.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationFile
Menentukan konfigurasi layanan XML (.cscfg) untuk layanan cloud.

```yaml
Type: System.String
Parameter Sets: quickCreateParameterSetWithoutStorage, quickCreateParameterSetWithStorage
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationUrl
Menentukan URL yang mengacu pada lokasi konfigurasi layanan di blob service.
URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun. Ini adalah properti tulis-saja dan tidak dikembalikan dalam panggilan GET.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
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
Parameter Sets: CreateExpanded
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionFile
Jalur ke file .csdef.

```yaml
Type: System.String
Parameter Sets: quickCreateParameterSetWithoutStorage, quickCreateParameterSetWithStorage
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsName
Nama Dns yang akan digunakan untuk sumber daya CloudService.

```yaml
Type: System.String
Parameter Sets: quickCreateParameterSetWithoutStorage, quickCreateParameterSetWithStorage
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionProfile
Menjelaskan profil ekstensi layanan cloud.
Untuk membuat, lihat bagian CATATAN untuk properti EXTENSIONPROFILE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudServiceExtensionProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultName
Nama KeyVault yang akan digunakan untuk sumber daya CloudService.

```yaml
Type: System.String
Parameter Sets: quickCreateParameterSetWithoutStorage, quickCreateParameterSetWithStorage
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

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

### -Name
Nama layanan awan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CloudServiceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkProfile
Profil Jaringan untuk layanan cloud.
Untuk membuat, lihat bagian NOTES untuk properti NETWORKPROFILE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudServiceNetworkProfile
Parameter Sets: CreateExpanded
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
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSProfile
Menjelaskan profil OS untuk layanan awan.
Untuk membuat, lihat bagian NOTES untuk properti OSPROFILE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudServiceOSProfile
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageFile
Jalur ke file .cspkg.
Ini akan diunggah ke blob

```yaml
Type: System.String
Parameter Sets: quickCreateParameterSetWithStorage
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageUrl
Menentukan URL yang mengacu pada lokasi paket layanan di blob service.
URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (SAS) dari akun penyimpanan apa pun. Ini adalah properti tulis-saja dan tidak dikembalikan dalam panggilan GET.

```yaml
Type: System.String
Parameter Sets: CreateExpanded, quickCreateParameterSetWithoutStorage
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -RoleProfile
Menjelaskan profil peran untuk layanan awan.
Untuk membuat, lihat bagian CATATAN untuk properti ROLEPROFILE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudServiceRoleProfile
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartCloudService
(Opsional) Menunjukkan apakah akan memulai layanan cloud segera setelah dibuat.
Nilai defaultnya adalah `true`. Jika false, model layanan masih disebarkan, tetapi kode tidak segera dijalankan.
Sebagai gantinya, layanan ini Adalah PoweredOff sampai Anda memanggil Mulai, pada saat layanan akan dimulai.
Layanan yang disebarkan masih dikenakan biaya, bahkan jika itu dimatikan.

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

### -StorageAccount
Nama akun penyimpanan yang akan menyimpan file Paket.

```yaml
Type: System.String
Parameter Sets: quickCreateParameterSetWithStorage
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

### -Tag
Tag sumber daya.

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

### -UpgradeMode
Mode pembaruan untuk layanan awan.
Instans peran dialokasikan untuk memperbarui domain saat layanan disebarkan.
Pembaruan dapat dimulai secara manual di setiap domain pembaruan atau dimulai secara otomatis di semua domain pembaruan. Nilai yang Mungkin Adalah \<br /\>\<br /\>**Manual** \<br /\>\<br /\>**Otomatis**\<br /\>\<br /\> **Simultan**\<br /\>\<br /\>Jika tidak ditentukan, nilai defaultnya adalah Otomatis. Jika diatur ke Manual, PUT UpdateDomain harus dipanggil untuk menerapkan pembaruan.
Jika diatur ke Otomatis, pembaruan secara otomatis diterapkan ke setiap domain pembaruan secara berurutan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Support.CloudServiceUpgradeMode
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

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EXTENSIONPROFILE <ICloudServiceExtensionProfile>: Menjelaskan profil ekstensi layanan cloud.
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

NETWORKPROFILE <ICloudServiceNetworkProfile>: Profil Jaringan untuk layanan cloud.
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

OSPROFILE <ICloudServiceOSProfile>: Menjelaskan profil OS untuk layanan cloud.
  - `[Secret <ICloudServiceVaultSecretGroup[]>]`: Menentukan sekumpulan sertifikat yang harus diinstal ke instans peran.
    - `[SourceVaultId <String>]`: Id Sumber Daya
    - `[VaultCertificate <ICloudServiceVaultCertificate[]>]`: Daftar referensi brankas kunci di SourceVault yang berisi sertifikat.
      - `[CertificateUrl <String>]`: Ini adalah URL sertifikat yang telah diunggah ke Key Vault sebagai rahasia.

ROLEPROFILE <ICloudServiceRoleProfile>: Menjelaskan profil peran untuk layanan cloud.
  - `[Role <ICloudServiceRoleProfileProperties[]>]`: Daftar peran untuk layanan awan.
    - `[Name <String>]`: Nama sumber daya.
    - `[SkuCapacity <Int64?>]`: Menentukan jumlah instans peran di layanan cloud.
    - `[SkuName <String>]`: Nama sku. CATATAN: Jika SKU baru tidak didukung pada perangkat keras tempat layanan cloud saat ini aktif, Anda perlu menghapus dan membuat ulang layanan cloud atau kembali ke sku lama.
    - `[SkuTier <String>]`: Menentukan tingkat layanan cloud. Nilai yang Mungkin adalah <br /><br /> **Standard** <br /><br /> **Dasar**

## RELATED LINKS

