---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/new-azcontainergroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroup.md
ms.openlocfilehash: 8903628cdc7937f9304301c7594d423ac521e198
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144573266"
---
# New-AzContainerGroup

## SYNOPSIS
Membuat atau memperbarui grup kontainer dengan konfigurasi tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainergroup) untuk informasi terbaru.

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
Membuat atau memperbarui grup kontainer dengan konfigurasi tertentu. Untuk Volume properti, kami mendukung pemasangan berbagi File Azure sebagai volume atau menentukan repositori git sebagai direktori volume. Volume direktori kosong dan volume rahasia belum didukung.

## EXAMPLES

### Contoh 1: Membuat grup kontainer dengan instans kontainer dan meminta alamat IP publik dengan port pembuka
```powershell
$port1 = New-AzContainerInstancePortObject -Port 8000 -Protocol TCP
$port2 = New-AzContainerInstancePortObject -Port 8001 -Protocol TCP
$container = New-AzContainerInstanceObject -Name test-container -Image nginx -RequestCpu 1 -RequestMemoryInGb 1.5 -Port @($port1, $port2)
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux -RestartPolicy "Never" -IpAddressType Public
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer dengan instans kontainer, yang gambarnya adalah nginx terbaru, dan meminta alamat IP publik dengan membuka port 8000 dan 8001.

### Contoh 2: Membuat grup kontainer dan menjalankan skrip kustom di dalam kontainer.
```powershell
$env1 = New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"
$env2 = New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "value2" -AsPlainText -Force)
$container = New-AzContainerInstanceObject -Name test-container -Image alpine -Command "/bin/sh -c myscript.sh" -EnvironmentVariable @($env1, $env2)
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer dan menjalankan skrip kustom di dalam kontainer.

### Contoh 3: Membuat grup kontainer run-to-completion
```powershell
$container = New-AzContainerInstanceObject -Name test-container -Image alpine -Command "echo hello" 
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer yang mencetak 'halo' dan berhenti.

### Contoh 4: Membuat grup kontainer dengan instans kontainer menggunakan image nginx di Azure Container Registry
```powershell
$container = New-AzContainerInstanceObject -Name test-container -Image myacr.azurecr.io/nginx:latest
$imageRegistryCredential = New-AzContainerGroupImageRegistryCredentialObject -Server "myacr.azurecr.io" -Username "username" -Password (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force) 
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -ImageRegistryCredential $imageRegistryCredential
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer dengan instans kontainer, yang gambarnya nginx dalam Azure Container Registry.

### Contoh 5: Membuat grup kontainer dengan instans kontainer menggunakan image nginx di registri gambar kontainer kustom
```powershell
$container = New-AzContainerInstanceObject -Name test-container -Image myserver.com/nginx:latest
$imageRegistryCredential = New-AzContainerGroupImageRegistryCredentialObject -Server "myserver.com" -Username "username" -Password (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force) 
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -ImageRegistryCredential $imageRegistryCredential
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer dengan instans kontainer, yang gambarnya adalah gambar kustom dari registri gambar kontainer kustom.

### Contoh 6: Membuat grup kontainer yang memasang volume File Azure
```powershell
$volume = New-AzContainerGroupVolumeObject -Name "myvolume" -AzureFileShareName "myshare" -AzureFileStorageAccountName "username" -AzureFileStorageAccountKey (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force)
$mount = New-AzContainerInstanceVolumeMountObject -MountPath "/aci/logs" -Name "myvolume"
$container = New-AzContainerInstanceObject -Name test-container -Image alpine -VolumeMount $mount
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -Volume $volume
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer dengan instans kontainer, yang gambarnya adalah gambar kustom dari registri gambar kontainer kustom.

### Contoh 7: Membuat grup kontainer dengan sistem yang ditetapkan dan identitas yang ditetapkan pengguna
```powershell
$container = New-AzContainerInstanceObject -Name test-container -Image alpine
$containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -IdentityType "SystemAssigned, UserAssigned" -IdentityUserAssignedIdentity /subscriptions/<subscriptionId>/resourceGroups/<resourceGroup>/providers/Microsoft.ManagedIdentity/userAssignedIdentities/<UserIdentityName>
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Perintah ini membuat grup kontainer dengan sistem yang ditetapkan dan identitas yang ditetapkan pengguna.

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

### -Kontainer
Kontainer dalam grup kontainer.
Untuk membuat, lihat bagian CATATAN untuk properti KONTAINER dan buat tabel hash.

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
Server DNS untuk grup kontainer.

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
Opsi DNS untuk grup kontainer.

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
Domain pencarian DNS untuk pencarian nama host di grup kontainer.

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
Url dasar keyvault.

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
Jenis identitas yang digunakan untuk grup kontainer.
Jenis 'SystemAssigned, UserAssigned' mencakup identitas yang dibuat secara implisit dan sekumpulan identitas yang ditetapkan pengguna.
Jenis 'None' akan menghapus identitas apa pun dari grup kontainer.

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
Daftar identitas pengguna yang terkait dengan grup kontainer.
Referensi kunci kamus identitas pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}'.

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
Kredensial registri gambar tempat grup kontainer dibuat.
Untuk membuat, lihat bagian CATATAN untuk properti IMAGEREGISTRYCREDENTIAL dan buat tabel hash.

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
Kontainer init untuk grup kontainer.
Untuk membuat, lihat bagian CATATAN untuk properti INITCONTAINER dan buat tabel hash.

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
Label nama dns untuk IP.

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
IP yang terekspos ke internet publik.

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
Daftar port yang terekspos di grup kontainer.
Untuk membuat, lihat bagian CATATAN untuk properti IPADDRESSPORT dan buat tabel hash.

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
Menentukan apakah IP terekspos ke internet publik atau VNET pribadi.

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
Jenis log yang akan digunakan.

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

### -Name
Nama grup kontainer.

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

### -OSType
Jenis sistem operasi yang diperlukan oleh kontainer dalam grup kontainer.

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
Kebijakan hidupkan ulang untuk semua kontainer dalam grup kontainer.
- `Always` Selalu hidupkan ulang- `OnFailure` Hidupkan ulang pada kegagalan- `Never` Jangan pernah memulai ulang

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
SKU untuk grup kontainer.

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
ID sumber daya subnet untuk grup kontainer.
Untuk membuat, lihat bagian NOTES untuk properti SUBNETID dan membuat tabel hash.

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

### -Volume
Daftar volume yang dapat dipasang oleh kontainer dalam grup kontainer ini.
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

### -Zona
Zona untuk grup kontainer.

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerGroup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KONTAINER <IContainer[]>: Kontainer dalam grup kontainer.
  - `Image <String>`: Nama gambar yang digunakan untuk membuat instans kontainer.
  - `Name <String>`: Nama instans kontainer yang disediakan pengguna.
  - `RequestCpu <Double>`: Permintaan CPU dari instans kontainer ini.
  - `RequestMemoryInGb <Double>`: Permintaan memori dalam GB instans kontainer ini.
  - `[Command <String[]>]`: Perintah untuk dijalankan dalam instans kontainer dalam bentuk exec.
  - `[EnvironmentVariable <IEnvironmentVariable[]>]`: Variabel lingkungan yang akan diatur dalam instans kontainer.
    - `Name <String>`: Nama variabel lingkungan.
    - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
    - `[Value <String>]`: Nilai variabel lingkungan.
  - `[LimitCpu <Double?>]`: Batas CPU instans kontainer ini.
  - `[LimitMemoryInGb <Double?>]`: Batas memori dalam GB instans kontainer ini.
  - `[LimitsGpuCount <Int32?>]`: Jumlah sumber daya GPU.
  - `[LimitsGpuSku <GpuSku?>]`: SKU sumber daya GPU.
  - `[LivenessProbeExecCommand <String[]>]`: Perintah untuk dijalankan dalam kontainer.
  - `[LivenessProbeFailureThreshold <Int32?>]`: Ambang kegagalan.
  - `[LivenessProbeHttpGetHttpHeader <IHttpHeader[]>]`: Header HTTP.
    - `[Name <String>]`: Nama header.
    - `[Value <String>]`: Nilai header.
  - `[LivenessProbeHttpGetPath <String>]`: Jalur menuju probe.
  - `[LivenessProbeHttpGetPort <Int32?>]`: Nomor port untuk pemeriksaan.
  - `[LivenessProbeHttpGetScheme <Scheme?>]`: Skemanya.
  - `[LivenessProbeInitialDelaySecond <Int32?>]`: Detik penundaan awal.
  - `[LivenessProbePeriodSecond <Int32?>]`: Detik periode.
  - `[LivenessProbeSuccessThreshold <Int32?>]`: Ambang keberhasilan.
  - `[LivenessProbeTimeoutSecond <Int32?>]`: Detik waktu habis.
  - `[Port <IContainerPort[]>]`: Port yang diekspos pada instans kontainer.
    - `Port <Int32>`: Nomor port yang terekspos dalam grup kontainer.
    - `[Protocol <ContainerNetworkProtocol?>]`: Protokol yang terkait dengan port.
  - `[ReadinessProbeExecCommand <String[]>]`: Perintah untuk dijalankan dalam kontainer.
  - `[ReadinessProbeFailureThreshold <Int32?>]`: Ambang kegagalan.
  - `[ReadinessProbeHttpGetHttpHeader <IHttpHeader[]>]`: Header HTTP.
  - `[ReadinessProbeHttpGetPath <String>]`: Jalur menuju probe.
  - `[ReadinessProbeHttpGetPort <Int32?>]`: Nomor port untuk pemeriksaan.
  - `[ReadinessProbeHttpGetScheme <Scheme?>]`: Skemanya.
  - `[ReadinessProbeInitialDelaySecond <Int32?>]`: Detik penundaan awal.
  - `[ReadinessProbePeriodSecond <Int32?>]`: Detik periode.
  - `[ReadinessProbeSuccessThreshold <Int32?>]`: Ambang keberhasilan.
  - `[ReadinessProbeTimeoutSecond <Int32?>]`: Detik waktu habis.
  - `[RequestsGpuCount <Int32?>]`: Jumlah sumber daya GPU.
  - `[RequestsGpuSku <GpuSku?>]`: SKU sumber daya GPU.
  - `[VolumeMount <IVolumeMount[]>]`: Pemasangan volume tersedia untuk instans kontainer.
    - `MountPath <String>`: Jalur dalam kontainer tempat volume harus dipasang. Tidak boleh ada titik dua (:).
    - `Name <String>`: Nama pemasangan volume.
    - `[ReadOnly <Boolean?>]`: Bendera yang menunjukkan apakah pemasangan volume bersifat baca-saja.

IMAGEREGISTRYCREDENTIAL <IImageRegistryCredential[]>: Kredensial registri gambar tempat grup kontainer dibuat.
  - `Server <String>`: Server registri gambar Docker tanpa protokol seperti "http" dan "https".
  - `Username <String>`: Nama pengguna untuk registri privat.
  - `[Identity <String>]`: Identitas untuk registri privat.
  - `[IdentityUrl <String>]`: URL identitas untuk registri privat.
  - `[Password <String>]`: Kata sandi untuk registri privat.

INITCONTAINER <IInitContainerDefinition[]>: Kontainer init untuk grup kontainer.
  - `Name <String>`: Nama untuk kontainer init.
  - `[Command <String[]>]`: Perintah untuk menjalankan dalam kontainer init dalam bentuk exec.
  - `[EnvironmentVariable <IEnvironmentVariable[]>]`: Variabel lingkungan yang akan diatur dalam kontainer init.
    - `Name <String>`: Nama variabel lingkungan.
    - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
    - `[Value <String>]`: Nilai variabel lingkungan.
  - `[Image <String>]`: Gambar kontainer init.
  - `[VolumeMount <IVolumeMount[]>]`: Pemasangan volume tersedia untuk kontainer init.
    - `MountPath <String>`: Jalur dalam kontainer tempat volume harus dipasang. Tidak boleh ada titik dua (:).
    - `Name <String>`: Nama pemasangan volume.
    - `[ReadOnly <Boolean?>]`: Bendera yang menunjukkan apakah pemasangan volume bersifat baca-saja.

IPADDRESSPORT <IPort[]>: Daftar port yang terekspos pada grup kontainer.
  - `Port1 <Int32>`: Nomor port.
  - `[Protocol <ContainerGroupNetworkProtocol?>]`: Protokol yang terkait dengan port.

SUBNETID <IContainerGroupSubnetId[]>: ID sumber daya subnet untuk grup kontainer.
  - `Id <String>`: ID sumber daya jaringan virtual dan subnet.
  - `[Name <String>]`: Nama yang mudah diingat untuk subnet.

VOLUME <IVolume[]>: Daftar volume yang dapat dipasang oleh kontainer dalam grup kontainer ini.
  - `Name <String>`: Nama volume.
  - `[AzureFileReadOnly <Boolean?>]`: Bendera yang menunjukkan apakah File Azure yang dibagikan dipasang sebagai volume bersifat baca-saja.
  - `[AzureFileShareName <String>]`: Nama berbagi File Azure yang akan dipasang sebagai volume.
  - `[AzureFileStorageAccountKey <String>]`: Kunci akses akun penyimpanan yang digunakan untuk mengakses berbagi File Azure.
  - `[AzureFileStorageAccountName <String>]`: Nama akun penyimpanan yang berisi berbagi File Azure.
  - `[EmptyDir <IAny>]`: Volume direktori kosong.
  - `[GitRepoDirectory <String>]`: Nama direktori target. Tidak boleh berisi atau dimulai dengan '..'.  Jika '.' disediakan, direktori volume akan menjadi repositori git.  Jika tidak, jika ditentukan, volume akan berisi repositori git di subdirektori dengan nama yang diberikan.
  - `[GitRepoRepository <String>]`: URL Repositori
  - `[GitRepoRevision <String>]`: Terapkan hash untuk revisi yang ditentukan.
  - `[Secret <ISecretVolume>]`: Volume rahasia.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

