---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudService.md
ms.openlocfilehash: bcd5ba93ad265b2f94e7ade26ee3e3a8135e554f
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136357314"
---
# New-AzCloudService

## SYNOPSIS
Membuat atau memperbarui layanan awan.
Harap diperhatikan bahwa beberapa properti dapat diatur hanya selama pembuatan layanan awan.

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
Harap diperhatikan bahwa beberapa properti dapat diatur hanya selama pembuatan layanan awan.

## EXAMPLES

### Contoh 1: Buat layanan cloud baru dengan satu peran
```powershell
# Create role profile object
PS C:\> $role = New-AzCloudServiceRoleProfilePropertiesObject-Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
PS C:\> $roleProfile = @{role = @($role)}

# Create network profile object
PS C:\> $publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosOrg -Name ContosIp
PS C:\> $feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
PS C:\> $loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
PS C:\> $networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Read Configuration File
PS C:\> $cscfgFile = "<Path to cscfg configuration file>"
PS C:\> $cscfgContent = Get-Content $cscfgFile | Out-String

# Create cloud service
PS C:\> $cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -PackageUrl "https://xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"    `
                          -Configuration $cscfgContent                                  `
                          -UpgradeMode 'Auto'                                           `
                          -RoleProfile $roleProfile                                     `
                          -NetworkProfile $networkProfile
```

Kumpulan perintah di atas membuat layanan awan dengan satu peran

### Contoh 2: Buat layanan awan baru dengan satu peran dan ekstensi RDP
```powershell
# Create role profile object
PS C:\> $role = New-AzCloudServiceRoleProfilePropertiesObject-Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
PS C:\> $roleProfile = @{role = @($role)}

# Create network profile object
PS C:\> $publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosoOrg -Name ContosIp
PS C:\> $feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
PS C:\> $loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
PS C:\> $networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Create RDP extension object
PS C:\> $credential = Get-Credential
PS C:\> $expiration = (Get-Date).AddYears(1)
PS C:\> $extension = New-AzCloudServiceRemoteDesktopExtensionObject -Name 'RDPExtension' -Credential $credential -Expiration $expiration -TypeHandlerVersion '1.2.1'
PS C:\> $extensionProfile = @{extension = @($extension)}

# Read Configuration File
PS C:\> $cscfgFile = "<Path to cscfg configuration file>"
PS C:\> $cscfgContent = Get-Content $cscfgFile | Out-String

# Create cloud service
PS C:\> $cloudService = New-AzCloudService                                              `
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

Kumpulan perintah di atas membuat layanan awan dengan satu peran dan ekstensi RDP

### Contoh 3: Buat layanan cloud baru dengan peran dan sertifikat tunggal dari vault kunci
```powershell
# Create role profile object
PS C:\> $role = New-AzCloudServiceRoleProfilePropertiesObject-Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
PS C:\> $roleProfile = @{role = @($role)}

# Create OS profile object
PS C:\> $keyVault = Get-AzKeyVault -ResourceGroupName ContosOrg -VaultName ContosKeyVault
PS C:\> $certificate=Get-AzKeyVaultCertificate -VaultName ContosKeyVault -Name ContosCert
PS C:\> $secretGroup = New-AzCloudServiceVaultSecretGroupObject -Id $keyVault.ResourceId -CertificateUrl $certificate.SecretId
PS C:\> $osProfile = @{secret = @($secretGroup)}

# Create network profile object
PS C:\> $publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosOrg -Name ContosIp
PS C:\> $feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
PS C:\> $loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
PS C:\> $networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Read Configuration File
PS C:\> $cscfgFile = "<Path to cscfg configuration file>"
PS C:\>  = Get-Content $cscfgFile | Out-String

# Create cloud service
PS C:\> $cloudService = New-AzCloudService                                              `
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

Di atas kumpulan perintah akan membuat layanan cloud dengan peran dan sertifikat tunggal dari vault kunci.

### Contoh 4: Buat layanan cloud baru dengan beberapa peran dan ekstensi
```powershell
# Create role profile object
PS C:\> $role1 = New-AzCloudServiceRoleProfilePropertiesObject-Name 'ContosoFrontend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
PS C:\> $role2 = New-AzCloudServiceRoleProfilePropertiesObject-Name 'ContosoBackend' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
PS C:\> $roleProfile = @{role = @($role1, $role2)}

# Create network profile object
PS C:\> $publicIp = Get-AzPublicIpAddress -ResourceGroupName ContosOrg -Name ContosIp
PS C:\> $feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
PS C:\> $loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
PS C:\> $networkProfile = @{loadBalancerConfiguration = $loadBalancerConfig}

# Create RDP extension object
PS C:\> $credential = Get-Credential
PS C:\> $expiration = (Get-Date).AddYears(1)
PS C:\> $rdpExtension = New-AzCloudServiceRemoteDesktopExtensionObject -Name 'RDPExtension' -Credential $credential -Expiration $expiration -TypeHandlerVersion '1.2.1'

# Create Geneva extension object
PS C:\> $genevaExtension = New-AzCloudServiceExtensionObject -Name GenevaExtension -Publisher Microsoft.Azure.Geneva -Type GenevaMonitoringPaaS -TypeHandlerVersion "2.14.0.2"
PS C:\> $extensionProfile = @{extension = @($rdpExtension, $genevaExtension)}

# Add tags
PS C:\> $tag=@{"Owner" = "Contoso"}

# Read Configuration File
PS C:\> $cscfgFile = "<Path to cscfg configuration file>"
PS C:\> $cscfgContent = Get-Content $cscfgFile | Out-String

# Create cloud service
PS C:\> $cloudService = New-AzCloudService                                              `
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

Di atas kumpulan perintah akan membuat layanan cloud dengan peran dan sertifikat tunggal dari vault kunci.

### Contoh 5: Buat layanan awan baru dengan file CsCfg, CsDef, dan Cspkg menggunakan kumpulan parameter 'quickCreateParameterSetWithStorage'.
```powershell
# Set up a storage account if you have not
PS C:\> $storageAccount = New-AzStorageAccount -ResourceGroupName ContosoOrg -Name ContosoStorAcc -Location "East US" -SkuName "Standard_RAGRS" -Kind "StorageV2"

# Create cloud service
PS C:\> $cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -ConfigurationFile C:\files\CS.cscfg                          `
                          -DefinitionFile C:\files\CS.csdef                             `
                          -PackageFile C:\CS.cspkg                                      `
                          -StorageAccount ContosoStorAcc                                `
                          -KeyVaultName ContosoKV

```

Di atas kumpulan perintah akan membuat layanan awan dengan mengekstrak informasi NetworkProfile dan RoleProfile dari . CsCfg dan . File CsDef.

File tersebut juga akan menyediakan informasi OSProfile beserta Sertifikat dari keyvault yang disediakan dalam parameter '-KeyVaultName'.
Kumpulan parameter ini juga mengunggah . File CsPkg ke StorageAccount yang disediakan.

### Contoh 6: Buat layanan awan baru dengan file CsCfg, CsDef, dan Cspkg menggunakan kumpulan parameter 'quickCreateParameterSetWithoutStorage'.
```powershell
# getting Package URL
PS C:\> $tokenStartTime = Get-Date 
PS C:\> $tokenEndTime = $tokenStartTime.AddYears(1) 
PS C:\> $storAcc = Get-AzStorageAccount -ResourceGroupName ContosoOrg -Name ContosoStorAcc
PS C:\> $csPkgBlob = Get-AzStorageBlob -Container Contoso-Container -Blob ContosoBlob.cspkg -Context $storAcc.Context
PS C:\> $csPkgToken = New-AzStorageBlobSASToken -Container Contoso-Container -Blob ContosoBlob.cspkg -Permission rwd -StartTime $tokenStartTime -ExpiryTime $tokenEndTime -Context $storAcc.Context
PS C:\> $cspkgUrl = $csPkgBlob.ICloudBlob.Uri.AbsoluteUri + $csPkgToken 

# Create cloud service
PS C:\> $cloudService = New-AzCloudService                                              `
                          -Name ContosoCS                                               `
                          -ResourceGroupName ContosOrg                                  `
                          -Location EastUS                                              `
                          -ConfigurationFile C:\files\CS.cscfg                          `
                          -DefinitionFile C:\files\CS.csdef                             `
                          -packageUrl $cspkgUrl                                         `

```

Di atas kumpulan perintah akan membuat layanan awan dengan mengekstrak informasi NetworkProfile dan RoleProfile dari . CsCfg dan . File CsDef.

File tersebut juga akan menyediakan informasi OSProfile beserta Sertifikat dari keyvault yang disediakan dalam parameter '-KeyVaultName'.

## PARAMETERS

### -AllowModelOverride
(Opsional) Menunjukkan apakah properti sku peran (roleProfile.roles.sku) yang ditentukan dalam model/templat harus menimpa jumlah contoh peran dan ukuran vm yang ditentukan dalam masing-masing .cscfg dan .csdef. Nilai defaultnya adalah `false` .

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
Menjalankan perintah sebagai pekerjaan

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

### -Configuration
Menentukan konfigurasi layanan XML (.cscfg) untuk layanan awan.

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
Menentukan konfigurasi layanan XML (.cscfg) untuk layanan awan.

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
Menentukan URL yang merujuk ke lokasi konfigurasi layanan dalam layanan Blob.
URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (Sas, Shared Access Signature) dari akun penyimpanan apa pun. Ini adalah properti khusus untuk menulis dan tidak dikembalikan dalam panggilan GET.

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
Menjelaskan profil ekstensi layanan awan.
Untuk membuat, lihat bagian CATATAN untuk properti EXTENSIONPROFILE dan membuat tabel hash.

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

### -Nama
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
Profil Jaringan untuk layanan awan.
Untuk membuat, lihat bagian CATATAN untuk properti NETWORKPROFILE dan membuat tabel hash.

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
Menjalankan perintah secara asinkron

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
Untuk membuat, lihat bagian CATATAN untuk properti OSPROFILE dan membuat tabel hash.

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
File akan diunggah ke blob

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
Menentukan URL yang merujuk ke lokasi paket layanan dalam layanan Blob.
URL paket layanan dapat menjadi URI Tanda Tangan Akses Bersama (Sas, Shared Access Signature) dari akun penyimpanan apa pun. Ini adalah properti khusus untuk menulis dan tidak dikembalikan dalam panggilan GET.

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
Untuk membuat, lihat bagian CATATAN untuk properti ROLEPROFILE dan membuat tabel hash.

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
(Opsional) Menunjukkan apakah akan memulai layanan awan segera setelah dibuat.
Nilai defaultnya adalah `true` . Jika false, model layanan masih digunakan, tapi kode tidak langsung dijalankan.
Sebaliknya, layanan didukungOff hingga Anda menghubungi Mulai, pada saat layanan akan dimulai.
Layanan yang disebarkan masih menimbulkan biaya, bahkan jika didukung.

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure anda.
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
Contoh peran dialokasikan untuk memperbarui domain ketika layanan digunakan.
Pembaruan dapat dimulai secara manual dalam setiap domain pembaruan atau dimulai secara otomatis di semua domain pembaruan. Nilai yang Mungkin \<br /\> \<br /\> **Adalah** \<br /\> \<br /\> **Manual** \<br /\> \<br /\> **Otomatis** \<br /\> \<br /\> Secara Bersamaan Jika tidak ditentukan, nilai defaultnya adalah Otomatis. Jika diset ke Manual, PUT UpdateDomain harus dipanggil untuk menerapkan pembaruan.
Jika diset ke Otomatis, pembaruan otomatis diterapkan ke setiap pembaruan domain secara berurutan.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EXTENSIONPROFILE <ICloudServiceExtensionProfile> : Menjelaskan profil ekstensi layanan awan.
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

NETWORKPROFILE <ICloudServiceNetworkProfile> : Profil Jaringan untuk layanan awan.
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

OSPROFILE <ICloudServiceOSProfile> : Menjelaskan profil OS untuk layanan awan.
  - `[Secret <ICloudServiceVaultSecretGroup[]>]`: Menentukan kumpulan sertifikat yang harus diinstal menjadi contoh peran.
    - `[SourceVaultId <String>]`: Id Sumber Daya
    - `[VaultCertificate <ICloudServiceVaultCertificate[]>]`: Daftar referensi kunci vault dalam SourceVault yang berisi sertifikat.
      - `[CertificateUrl <String>]`: URL sertifikat berikut telah diunggah ke Key Vault sebagai rahasia.

ROLEPROFILE <ICloudServiceRoleProfile> : Menjelaskan profil peran untuk layanan awan.
  - `[Role <ICloudServiceRoleProfileProperties[]>]`: Daftar peran untuk layanan awan.
    - `[Name <String>]`: Nama sumber daya.
    - `[SkuCapacity <Int64?>]`: Menentukan jumlah instans peran di layanan awan.
    - `[SkuName <String>]`: Nama sku. CATATAN: Jika SKU baru tidak didukung pada perangkat keras layanan awan saat ini, Anda harus menghapus dan membuat ulang layanan awan atau kembali ke sku lama.
    - `[SkuTier <String>]`: Menentukan tingkatan layanan awan. Nilai yang Mungkin adalah <br /><br /> **Standar** <br /><br /> **Dasar**

## RELATED LINKS

