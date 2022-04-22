---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/new-azcontainergroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroup.md
ms.openlocfilehash: b367d486040bf7d823900b86b91ad7dcad12cf7a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142904303"
---
# New-AzContainerGroup

## SYNOPSIS
Membuat atau memperbarui grup kontainer dengan konfigurasi tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainergroup) untuk informasi terbaru.

## SYNTAX

```
New-AzContainerGroup -Name <String> -ResourceGroupName <String> -Container <IContainer[]> -Location <String>
 [-SubscriptionId <String>] [-DnsConfigNameServer <String[]>] [-DnsConfigOption <String>]
 [-DnsConfigSearchDomain <String>] [-EncryptionPropertyKeyName <String>]
 [-EncryptionPropertyKeyVersion <String>] [-EncryptionPropertyVaultBaseUrl <String>] [-IdentityType <String>]
 [-IdentityUserAssignedIdentity <String[]>] [-ImageRegistryCredential <IImageRegistryCredential[]>]
 [-InitContainer <IInitContainerDefinition[]>] [-IPAddressDnsNameLabel <String>] [-IPAddressIP <String>]
 [-IPAddressPort <IPort[]>] [-IPAddressType <String>] [-LogAnalyticLogType <String>]
 [-LogAnalyticMetadata <Hashtable>] [-LogAnalyticWorkspaceId <String>] [-LogAnalyticWorkspaceKey <String>]
 [-LogAnalyticWorkspaceResourceId <Hashtable>] [-NetworkProfileId <String>] [-OSType <String>]
 [-RestartPolicy <String>] [-Sku <String>] [-Tag <Hashtable>] [-Volume <IVolume[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui grup kontainer dengan konfigurasi tertentu.

## EXAMPLES

### Contoh 1: Membuat grup kontainer dengan instans kontainer dan meminta alamat IP publik dengan port pembuka
```powershell
PS C:\> $port1 = New-AzContainerInstancePortObject -Port 8000 -Protocol TCP
PS C:\> $port2 = New-AzContainerInstancePortObject -Port 8001 -Protocol TCP
PS C:\> $container = New-AzContainerInstanceObject -Name test-container -Image nginx -RequestCpu 1 -RequestMemoryInGb 1.5 -Port @($port1, $port2)
PS C:\> $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux -RestartPolicy "Never" -IpAddressType Public

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup kontainer dengan instance container, yang gambarnya adalah nginx terbaru, dan meminta alamat IP publik dengan port pembukaan 8000 dan 8001.

### Contoh 2: Membuat grup kontainer dan menjalankan skrip kustom di dalam wadah.
```powershell
PS C:\>  $env1 = New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"
PS C:\>  $env2 = New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "value2" -AsPlainText -Force)
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine -Command "/bin/sh -c myscript.sh" -EnvironmentVariable @($env1, $env2)
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup wadah dan menjalankan skrip kustom di dalam wadah.

### Contoh 3: Membuat grup kontainer run-to-completion
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine -Command "echo hello" 
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup wadah yang mencetak 'halo' dan berhenti.

### Contoh 4: Membuat grup kontainer dengan instance container menggunakan image nginx di Azure Container Registry
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image myacr.azurecr.io/nginx:latest
PS C:\>  $imageRegistryCredential = New-AzContainerGroupImageRegistryCredentialObject -Server "myacr.azurecr.io" -Username "username" -Password (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force) 
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -ImageRegistryCredential $imageRegistryCredential

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya nginx dalam Azure Container Registry.

### Contoh 5: Membuat grup wadah dengan contoh kontainer menggunakan nginx gambar dalam registri gambar wadah kustom
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image myserver.com/nginx:latest
PS C:\>  $imageRegistryCredential = New-AzContainerGroupImageRegistryCredentialObject -Server "myserver.com" -Username "username" -Password (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force) 
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -ImageRegistryCredential $imageRegistryCredential

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya adalah gambar kustom dari registri gambar wadah kustom.

### Contoh 6: Membuat grup kontainer yang memasang volume File Azure
```powershell
PS C:\>  $volume = New-AzContainerGroupVolumeObject -Name "myvolume" -AzureFileShareName "myshare" -AzureFileStorageAccountName "username" -AzureFileStorageAccountKey (ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force)
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -Volume $volume

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup wadah dengan contoh wadah, yang gambarnya adalah gambar kustom dari registri gambar wadah kustom.

### Contoh 7: Membuat grup kontainer dengan sistem yang ditetapkan dan identitas yang ditetapkan pengguna
```powershell
PS C:\>  $container = New-AzContainerInstanceObject -Name test-container -Image alpine
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -IdentityType "SystemAssigned, UserAssigned" -IdentityUserAssignedIdentity /subscriptions/<subscriptionId>/resourceGroups/<resourceGroup>/providers/Microsoft.ManagedIdentity/userAssignedIdentities/<UserIdentityName>

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

Perintah ini membuat grup kontainer dengan sistem yang ditetapkan dan identitas yang ditetapkan pengguna.

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

### -Kontainer
Kontainer dalam grup wadah.
Untuk membangun, lihat bagian CATATAN untuk properti CONTAINER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IContainer[]
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
Tipe identitas yang digunakan untuk grup kontainer.
Tipe 'SystemAssigned, UserAssigned' mencakup identitas yang dibuat secara implisit dan sekumpulan identitas yang ditetapkan pengguna.
Tipe 'Tidak Ada' akan menghapus identitas apa pun dari grup kontainer.

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

### -IdentityUserAssignedIdentity
Daftar identitas pengguna yang terkait dengan grup kontainer.
Referensi kunci kamus identitas pengguna akan berupa id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}'.

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

### -ImageRegistryCredential
Kredensial registri gambar tempat grup kontainer dibuat.
Untuk membangun, lihat bagian CATATAN untuk properti IMAGEREGISTRYCREDENTIALS dan membuat tabel hash.
Untuk membangun, lihat bagian CATATAN untuk properti IMAGEREGISTRYCREDENTIAL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IImageRegistryCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitContainer
Wadah init untuk grup kontainer.
Untuk membangun, lihat bagian CATATAN untuk properti INITCONTAINER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IInitContainerDefinition[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressDnsNameLabel
Label Nama dns untuk IP.

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
IP terekspos ke internet publik.

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
Daftar port yang diekspos pada grup kontainer.
Untuk membuat, lihat bagian CATATAN untuk properti IPADDRESSPORT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IPort[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressType
Menentukan apakah IP diekspos ke internet publik atau VNET pribadi.

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
Type: System.String
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
Type: System.Collections.Hashtable
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

### -NetworkProfileId
Pengidentifikasi untuk profil jaringan.

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
Tipe sistem operasi yang diperlukan oleh wadah dalam grup wadah.

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
Mulai ulang kebijakan untuk semua kontainer dalam grup kontainer.
- `Always` Selalu hidupkan ulang- `OnFailure` Mulai ulang pada kegagalan- `Never` Jangan pernah memulai ulang

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

### -Sku
SKU untuk grup wadah.

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
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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
Daftar volume yang dapat dikaitkan oleh kontainer dalam grup kontainer ini.
Untuk membangun, lihat bagian CATATAN untuk properti VOLUME dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IVolume[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IContainerGroup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONTAINER <IContainer[]>: Kontainer dalam grup kontainer.
  - `Image <String>`: Nama gambar yang digunakan untuk membuat instance container.
  - `Name <String>`: Nama kontainer yang disediakan pengguna.
  - `RequestCpu <Double>`: Permintaan CPU dari instance container ini.
  - `RequestMemoryInGb <Double>`: Permintaan memori dalam GB instans kontainer ini.
  - `[Command <String[]>]`: Perintah untuk dijalankan dalam instance container dalam formulir exec.
  - `[EnvironmentVariable <IEnvironmentVariable[]>]`: Variabel lingkungan yang diatur dalam instance kontainer.
    - `Name <String>`: Nama variabel lingkungan.
    - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
    - `[Value <String>]`: Nilai variabel lingkungan.
  - `[LimitCpu <Double?>]`: Batas CPU dari instans kontainer ini.
  - `[LimitMemoryInGb <Double?>]`: Batas memori dalam GB instans kontainer ini.
  - `[LimitsGpuCount <Int32?>]`: Hitungan sumber daya GPU.
  - `[LimitsGpuSku <GpuSku?>]`: SKU sumber daya GPU.
  - `[LivenessProbeExecCommand <String[]>]`: Perintah untuk dijalankan dalam wadah.
  - `[LivenessProbeFailureThreshold <Int32?>]`: Ambang batas kegagalan.
  - `[LivenessProbeHttpGetHttpHeadersName <String>]`: Nama header.
  - `[LivenessProbeHttpGetHttpHeadersValue <String>]`: Nilai header.
  - `[LivenessProbeHttpGetPath <String>]`: Jalur menuju probe.
  - `[LivenessProbeHttpGetPort <Int32?>]`: Nomor port untuk diprobes.
  - `[LivenessProbeHttpGetScheme <Scheme?>]`: Skemanya.
  - `[LivenessProbeInitialDelaySecond <Int32?>]`: Detik penundaan awal.
  - `[LivenessProbePeriodSecond <Int32?>]`: Detik periode.
  - `[LivenessProbeSuccessThreshold <Int32?>]`: Ambang keberhasilan.
  - `[LivenessProbeTimeoutSecond <Int32?>]`: Waktu habis detik.
  - `[Port <IContainerPort[]>]`: Port yang terbuka pada instance container.
    - `Port <Int32>`: Nomor port yang diekspos dalam grup kontainer.
    - `[Protocol <ContainerNetworkProtocol?>]`: Protokol yang terkait dengan port.
  - `[ReadinessProbeExecCommand <String[]>]`: Perintah untuk dijalankan dalam wadah.
  - `[ReadinessProbeFailureThreshold <Int32?>]`: Ambang batas kegagalan.
  - `[ReadinessProbeHttpGetHttpHeadersName <String>]`: Nama header.
  - `[ReadinessProbeHttpGetHttpHeadersValue <String>]`: Nilai header.
  - `[ReadinessProbeHttpGetPath <String>]`: Jalur menuju probe.
  - `[ReadinessProbeHttpGetPort <Int32?>]`: Nomor port untuk diprobes.
  - `[ReadinessProbeHttpGetScheme <Scheme?>]`: Skemanya.
  - `[ReadinessProbeInitialDelaySecond <Int32?>]`: Detik penundaan awal.
  - `[ReadinessProbePeriodSecond <Int32?>]`: Detik periode.
  - `[ReadinessProbeSuccessThreshold <Int32?>]`: Ambang keberhasilan.
  - `[ReadinessProbeTimeoutSecond <Int32?>]`: Waktu habis detik.
  - `[RequestsGpuCount <Int32?>]`: Hitungan sumber daya GPU.
  - `[RequestsGpuSku <GpuSku?>]`: SKU sumber daya GPU.
  - `[VolumeMount <IVolumeMount[]>]`: Volume terpasang yang tersedia untuk instance container.
    - `MountPath <String>`: Jalur dalam wadah tempat volume harus dipasang. Tidak boleh mengandung titik dua (:).
    - `Name <String>`: Nama dudukan volume.
    - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah dudukan volume bersifat baca-saja.

IMAGEREGISTRYCREDENTIAL <IImageRegistryCredential[]>: Kredensial registri gambar tempat grup kontainer dibuat. Untuk membangun, lihat bagian CATATAN untuk properti IMAGEREGISTRYCREDENTIALS dan membuat tabel hash.
  - `Server <String>`: Server registri gambar Docker tanpa protokol seperti "http" dan "https".
  - `Username <String>`: Nama pengguna untuk registri privat.
  - `[Password <String>]`: Kata sandi untuk registri privat.

INITCONTAINER <IInitContainerDefinition[]>: Wadah init untuk grup kontainer.
  - `Name <String>`: Nama untuk wadah init.
  - `[Command <String[]>]`: Perintah untuk menjalankan dalam wadah init dalam formulir exec.
  - `[EnvironmentVariable <IEnvironmentVariable[]>]`: Variabel lingkungan yang diatur dalam wadah init.
    - `Name <String>`: Nama variabel lingkungan.
    - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
    - `[Value <String>]`: Nilai variabel lingkungan.
  - `[Image <String>]`: Gambar wadah init.
  - `[VolumeMount <IVolumeMount[]>]`: Dudukan volume yang tersedia untuk wadah init.
    - `MountPath <String>`: Jalur dalam wadah tempat volume harus dipasang. Tidak boleh mengandung titik dua (:).
    - `Name <String>`: Nama dudukan volume.
    - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah dudukan volume bersifat baca-saja.

IPADDRESSPORT <IPort[]>: Daftar port yang diekspos pada grup kontainer.
  - `Port1 <Int32>`: Nomor port.
  - `[Protocol <ContainerGroupNetworkProtocol?>]`: Protokol yang terkait dengan port.

VOLUME <IVolume[]>: Daftar volume yang dapat dipasang oleh kontainer dalam grup kontainer ini.
  - `Name <String>`: Nama volume.
  - `[AzureFileReadOnly <Boolean?>]`: Bendera yang menunjukkan apakah File Azure yang dibagikan dipasang sebagai volume bersifat baca-saja.
  - `[AzureFileShareName <String>]`: Nama berbagi File Azure yang akan dikaitkan sebagai volume.
  - `[AzureFileStorageAccountKey <String>]`: Kunci akses akun penyimpanan yang digunakan untuk mengakses berbagi File Azure.
  - `[AzureFileStorageAccountName <String>]`: Nama akun penyimpanan yang berisi berbagi File Azure.
  - `[EmptyDir <IAny>]`: Volume direktori kosong.
  - `[GitRepoDirectory <String>]`: Nama direktori target. Tidak boleh memuat atau memulai dengan '..'.  Jika '.' disertakan, direktori volume akan menjadi repository git.  Jika tidak, jika ditentukan, volume akan berisi repository git dalam subdirektori dengan nama tertentu.
  - `[GitRepoRepository <String>]`: URL Repository
  - `[GitRepoRevision <String>]`: Melakukan hash untuk revisi yang ditentukan.
  - `[Secret <ISecretVolume>]`: Volume rahasia.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

