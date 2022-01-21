---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/new-azcontainergroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroup.md
ms.openlocfilehash: fe7f5f0d6744b11d39738be3097aad2459a05b63
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136556847"
---
# New-AzContainerGroup

## SYNOPSIS
Membuat atau memperbarui grup wadah dengan konfigurasi tertentu.

## SYNTAX

```
New-AzContainerGroup -Name <String> -ResourceGroupName <String> -Container <IContainer[]> -Location <String>
 [-SubscriptionId <String>] [-DnsConfigNameServer <String[]>] [-DnsConfigOption <String>]
 [-DnsConfigSearchDomain <String>] [-EncryptionPropertyKeyName <String>]
 [-EncryptionPropertyKeyVersion <String>] [-EncryptionPropertyVaultBaseUrl <String>]
 [-IdentityType <ResourceIdentityType>] [-IdentityUserAssignedIdentity <Hashtable>]
 [-ImageRegistryCredential <IImageRegistryCredential[]>] [-InitContainer <IInitContainerDefinition[]>]
 [-IPAddressDnsNameLabel <String>] [-IPAddressIP <String>] [-IPAddressPort <IPort[]>]
 [-IPAddressType <ContainerGroupIPAddressType>] [-LogAnalyticLogType <LogAnalyticsLogType>]
 [-LogAnalyticMetadata <Hashtable>] [-LogAnalyticWorkspaceId <String>] [-LogAnalyticWorkspaceKey <String>]
 [-LogAnalyticWorkspaceResourceId <String>] [-OSType <OperatingSystemTypes>]
 [-RestartPolicy <ContainerGroupRestartPolicy>] [-Sku <ContainerGroupSku>]
 [-SubnetId <IContainerGroupSubnetId[]>] [-Tag <Hashtable>] [-Volume <IVolume[]>] [-Zone <String[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui grup wadah dengan konfigurasi tertentu.

## EXAMPLES

### Contoh 1: Buat grup wadah dengan contoh wadah dan minta alamat IP publik dengan port terbuka
```powershell
PS C:\> $port1 = New-AzContainerInstancePortObject -Port 8000 -Protocol TCP
PS C:\> $port2 = New-AzContainerInstancePortObject -Port 8001 -Protocol TCP
PS C:\> $container = New-AzContainerInstanceObject -Name test-container -Image nginx -RequestCpu 1 -RequestMemoryInGb 1.5 -Port @($port1, $port2)
PS C:\> $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux -RestartPolicy "Never" -IpAddressType Public

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya nginx terbaru, dan meminta alamat IP publik dengan membuka port 8000 dan 8001.

### Contoh 2: Buat grup wadah dan jalankan skrip kustom di dalam wadah.
```powershell
PS C:\>  $env1 = New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"
PS C:\>  $env2 = New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "value2" -AsPlainText -Force)
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine -Command "/bin/sh -c myscript.sh" -EnvironmentVariable @($env1, $env2)
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini akan membuat grup wadah dan menjalankan skrip kustom dalam wadah.

### Contoh 3: Buat grup wadah run-to-completion
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine -Command "echo hello" 
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup wadah yang mencetak 'halo' dan perhentian.

### Contoh 4: Buat grup wadah dengan contoh wadah menggunakan nginx gambar di Azure Container Registry
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image myacr.azurecr.io/nginx:latest
PS C:\>  $imageRegistryCredential = New-AzContainerGroupImageRegistryCredentialObject -Server "myacr.azurecr.io" -Username "username" -Password (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force) 
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -ImageRegistryCredential $imageRegistryCredential

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya nginx di Azure Container Registry.

### Contoh 5: Buat grup wadah dengan contoh wadah menggunakan nginx gambar dalam registri gambar wadah kustom
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image myserver.com/nginx:latest
PS C:\>  $imageRegistryCredential = New-AzContainerGroupImageRegistryCredentialObject -Server "myserver.com" -Username "username" -Password (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force) 
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -ImageRegistryCredential $imageRegistryCredential

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya adalah gambar kustom dari registri gambar wadah kustom.

### Contoh 6: Membuat grup wadah yang terpasang volume File Azure
```powershell
PS C:\>  $volume = New-AzContainerGroupVolumeObject -Name "myvolume" -AzureFileShareName "myshare" -AzureFileStorageAccountName "username" -AzureFileStorageAccountKey (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force)
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -Volume $volume

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya adalah gambar kustom dari registri gambar wadah kustom.

### Contoh 7: Buat grup wadah dengan identitas yang ditetapkan sistem dan ditetapkan pengguna
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -IdentityType "SystemAssigned, UserAssigned" -IdentityUserAssignedIdentity /subscriptions/<subscriptionId>/resourceGroups/<resourceGroup>/providers/Microsoft.ManagedIdentity/userAssignedIdentities/<UserIdentityName>

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup wadah dengan identitas sistem yang ditetapkan dan ditetapkan pengguna.

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

### -Container
Wadah dalam grup wadah.
Untuk membuat, lihat bagian CATATAN untuk properti CONTAINER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainer[]
Parameter Sets: (All)
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

### -DnsConfigNameServer
Server DNS untuk grup wadah.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsConfigOption
Opsi DNS untuk grup wadah.

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

### -DnsConfigSearchDomain
Domain pencarian DNS untuk pencarian nama host dalam grup wadah.

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

### -EncryptionPropertyKeyName
Nama kunci enkripsi.

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

### -EncryptionPropertyKeyVersion
Versi kunci enkripsi.

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

### -EncryptionPropertyVaultBaseUrl
URL dasar keyvault.

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

### -IdentityType
Tipe identitas yang digunakan untuk grup wadah.
Tipe 'SystemAssigned, UserAssigned' menyertakan identitas yang dibuat secara implisit dan kumpulan identitas yang ditetapkan pengguna.
Tipe 'Tidak Ada' akan menghapus identitas apa pun dari grup wadah.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Support.ResourceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityUserAssignedIdentity
Daftar identitas pengguna yang terkait dengan grup wadah.
Referensi kunci kamus identitas pengguna akan menjadi ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}'.

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

### -ImageRegistryCredential
Kredensial registri gambar tempat grup wadah dibuat.
Untuk membuat, lihat bagian CATATAN untuk properti IMAGEREGISTRYCREDENTIAL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IImageRegistryCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitContainer
Wadah init untuk grup wadah.
Untuk membuat, lihat bagian CATATAN untuk properti INITCONTAINER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IInitContainerDefinition[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressDnsNameLabel
Label nama Dns untuk IP tersebut.

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

### -IPAddressIP
IP yang diekspos ke internet publik.

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

### -IPAddressPort
Daftar port yang diekspos pada grup wadah.
Untuk membuat, lihat bagian CATATAN untuk properti IPADDRESSPORT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IPort[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressType
Menentukan apakah IP diekspos ke internet publik atau VNET privat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Support.ContainerGroupIPAddressType
Parameter Sets: (All)
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

### -LogAnalyticLogType
Tipe log yang akan digunakan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Support.LogAnalyticsLogType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogAnalyticMetadata
Metadata untuk analitik log.

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

### -LogAnalyticWorkspaceId
Id ruang kerja untuk analitik log

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

### -LogAnalyticWorkspaceKey
Kunci ruang kerja untuk analitik log

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

### -LogAnalyticWorkspaceResourceId
Id sumber daya ruang kerja untuk analitik log

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

### -Nama
Nama grup wadah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ContainerGroupName

Required: True
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

### -OSType
Tipe sistem operasi diperlukan oleh wadah dalam grup wadah.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Support.OperatingSystemTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "Linux"
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

### -RestartPolicy
Mulai ulang kebijakan untuk semua wadah dalam grup wadah.
- `Always` Selalu mulai ulang- `OnFailure` Mulai ulang saat kegagalan- Jangan pernah mulai `Never` ulang

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Support.ContainerGroupRestartPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
SKU untuk grup wadah.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Support.ContainerGroupSku
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
ID sumber daya subnet untuk grup wadah.
Untuk membuat, lihat bagian CATATAN untuk properti SUBNETID dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerGroupSubnetId[]
Parameter Sets: (All)
Aliases:

Required: False
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

### -Volume
Daftar volume yang dapat terpasang menurut wadah dalam grup wadah ini.
Untuk membuat, lihat bagian CATATAN untuk properti VOLUME dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IVolume[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zone
Zona untuk grup wadah.

```yaml
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerGroup

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONTAINER <IContainer[]>: Wadah dalam grup wadah.
  - `Image <String>`: Nama gambar yang digunakan untuk membuat contoh wadah.
  - `Name <String>`: Nama contoh wadah yang diberikan pengguna.
  - `RequestCpu <Double>`: Permintaan CPU instans wadah ini.
  - `RequestMemoryInGb <Double>`: Permintaan memori dalam GB contoh wadah ini.
  - `[Command <String[]>]`: Perintah untuk dijalankan dalam wadah contoh dalam bentuk exec.
  - `[EnvironmentVariable <IEnvironmentVariable[]>]`: Variabel lingkungan yang diatur dalam contoh wadah.
    - `Name <String>`: Nama variabel lingkungan.
    - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
    - `[Value <String>]`: Nilai variabel lingkungan.
  - `[LimitCpu <Double?>]`: Batasan CPU instans wadah ini.
  - `[LimitMemoryInGb <Double?>]`: Batas memori dalam GB contoh wadah ini.
  - `[LimitsGpuCount <Int32?>]`: Jumlah sumber daya GPU.
  - `[LimitsGpuSku <GpuSku?>]`: SKU sumber daya GPU.
  - `[LivenessProbeExecCommand <String[]>]`: Perintah untuk dijalankan dalam wadah.
  - `[LivenessProbeFailureThreshold <Int32?>]`: Ambang kegagalan.
  - `[LivenessProbeHttpGetHttpHeader <IHttpHeader[]>]`: Header HTTP.
    - `[Name <String>]`: Nama header.
    - `[Value <String>]`: Nilai header.
  - `[LivenessProbeHttpGetPath <String>]`: Jalur ke path ke file tersebut.
  - `[LivenessProbeHttpGetPort <Int32?>]`: Nomor port ke laut.
  - `[LivenessProbeHttpGetScheme <Scheme?>]`: Skema.
  - `[LivenessProbeInitialDelaySecond <Int32?>]`: Detik penundaan awal.
  - `[LivenessProbePeriodSecond <Int32?>]`: Periode detik.
  - `[LivenessProbeSuccessThreshold <Int32?>]`: Ambang keberhasilan.
  - `[LivenessProbeTimeoutSecond <Int32?>]`: Waktu habis detik.
  - `[Port <IContainerPort[]>]`: Port yang diekspos pada contoh wadah.
    - `Port <Int32>`: Nomor port yang diekspos dalam grup wadah.
    - `[Protocol <ContainerNetworkProtocol?>]`: Protokol yang terkait dengan port.
  - `[ReadinessProbeExecCommand <String[]>]`: Perintah untuk dijalankan dalam wadah.
  - `[ReadinessProbeFailureThreshold <Int32?>]`: Ambang kegagalan.
  - `[ReadinessProbeHttpGetHttpHeader <IHttpHeader[]>]`: Header HTTP.
  - `[ReadinessProbeHttpGetPath <String>]`: Jalur ke path ke file tersebut.
  - `[ReadinessProbeHttpGetPort <Int32?>]`: Nomor port ke laut.
  - `[ReadinessProbeHttpGetScheme <Scheme?>]`: Skema.
  - `[ReadinessProbeInitialDelaySecond <Int32?>]`: Detik penundaan awal.
  - `[ReadinessProbePeriodSecond <Int32?>]`: Periode detik.
  - `[ReadinessProbeSuccessThreshold <Int32?>]`: Ambang keberhasilan.
  - `[ReadinessProbeTimeoutSecond <Int32?>]`: Waktu habis detik.
  - `[RequestsGpuCount <Int32?>]`: Jumlah sumber daya GPU.
  - `[RequestsGpuSku <GpuSku?>]`: SKU sumber daya GPU.
  - `[VolumeMount <IVolumeMount[]>]`: Volume yang terpasang pada contoh wadah.
    - `MountPath <String>`: Jalur di dalam wadah tempat volume harus terpasang. Tidak boleh berisi titik dua (:).
    - `Name <String>`: Nama volume yang naik.
    - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah volume naik merupakan baca-saja.

IMAGEREGISTRYCREDENTIAL <IImageRegistryCredential[]>: Kredensial registri gambar tempat grup wadah dibuat.
  - `Server <String>`: Server registri gambar Docker tanpa protokol seperti "http" dan "https".
  - `Username <String>`: Nama pengguna untuk registri privat.
  - `[Identity <String>]`: Identitas untuk registri privat.
  - `[IdentityUrl <String>]`: URL identitas untuk registri privat.
  - `[Password <String>]`: Kata sandi untuk registri privat.

INITCONTAINER <IInitContainerDefinition[]>: Wadah init untuk grup wadah.
  - `Name <String>`: Nama untuk wadah init.
  - `[Command <String[]>]`: Perintah untuk dijalankan dalam wadah init dalam bentuk exec.
  - `[EnvironmentVariable <IEnvironmentVariable[]>]`: Variabel lingkungan yang diatur dalam wadah init.
    - `Name <String>`: Nama variabel lingkungan.
    - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
    - `[Value <String>]`: Nilai variabel lingkungan.
  - `[Image <String>]`: Gambar wadah init.
  - `[VolumeMount <IVolumeMount[]>]`: Volume yang terpasang pada wadah init.
    - `MountPath <String>`: Jalur di dalam wadah tempat volume harus terpasang. Tidak boleh berisi titik dua (:).
    - `Name <String>`: Nama volume yang naik.
    - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah volume naik merupakan baca-saja.

IPADDRESSPORT <IPort[]>: Daftar port yang diekspos pada grup wadah.
  - `Port1 <Int32>`: Nomor port.
  - `[Protocol <ContainerGroupNetworkProtocol?>]`: Protokol yang terkait dengan port.

SUBNETID <IContainerGroupSubnetId[]>: ID sumber daya subnet untuk grup wadah.
  - `Id <String>`: ID Sumber Daya jaringan virtual dan subnet.
  - `[Name <String>]`: Nama yang mudah digunakan untuk subnet.

VOLUME <IVolume[]>: Daftar volume yang dapat terpasang menurut wadah dalam grup wadah ini.
  - `Name <String>`: Nama volume.
  - `[AzureFileReadOnly <Boolean?>]`: Bendera menunjukkan apakah File Azure yang dibagikan terpasang sebagai volume bersifat baca-saja.
  - `[AzureFileShareName <String>]`: Nama berbagi File Azure yang akan terpasang sebagai volume.
  - `[AzureFileStorageAccountKey <String>]`: Kunci akses akun penyimpanan yang digunakan untuk mengakses berbagi File Azure.
  - `[AzureFileStorageAccountName <String>]`: Nama akun penyimpanan yang berisi berbagi File Azure.
  - `[EmptyDir <IAny>]`: Volume direktori kosong.
  - `[GitRepoDirectory <String>]`: Nama direktori target. Tidak boleh berisi atau dimulai dengan '..'.  Jika '.' disertakan, direktori volume akan menjadi repositori git.  Jika tidak, jika ditentukan, volume akan berisi repositori git dalam subarah dengan nama yang diberikan.
  - `[GitRepoRepository <String>]`: URL Penyimpanan
  - `[GitRepoRevision <String>]`: Menerapkan hash untuk revisi tertentu.
  - `[Secret <ISecretVolume>]`: Volume rahasia.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

