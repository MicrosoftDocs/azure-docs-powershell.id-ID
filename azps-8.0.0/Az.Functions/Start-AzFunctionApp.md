---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/start-azfunctionapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Start-AzFunctionApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Start-AzFunctionApp.md
ms.openlocfilehash: 06a2737fe4a84ef7aa7c1253728fd6c5aa45e698
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145510858"
---
# Start-AzFunctionApp

## SYNOPSIS
Memulai aplikasi fungsi.

## SYNTAX

### StartByName (Default)
```
Start-AzFunctionApp -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ByObjectInput
```
Start-AzFunctionApp -InputObject <ISite> [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Memulai aplikasi fungsi.

## EXAMPLES

### Contoh 1: Dapatkan aplikasi fungsi berdasarkan nama dan mulai.
```powershell
Get-AzFunctionApp -Name MyAppName -ResourceGroupName MyResourceGroupName | Start-AzFunctionApp
```

Perintah ini mendapatkan aplikasi fungsi berdasarkan nama dan memulainya.

### Contoh 2: Mulai aplikasi fungsi berdasarkan nama.
```powershell
Start-AzFunctionApp -Name MyAppName -ResourceGroupName MyResourceGroupName
```

Perintah ini memulai aplikasi fungsi berdasarkan nama.

## PARAMETERS

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
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.ISite
Parameter Sets: ByObjectInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama aplikasi fungsi.

```yaml
Type: System.String
Parameter Sets: StartByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil.

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

### -ResourceGroupName


```yaml
Type: System.String
Parameter Sets: StartByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Atur ID Langganan Azure.

```yaml
Type: System.String
Parameter Sets: StartByName
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

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.ISite

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ISite>: 
  - `Location <String>`: Lokasi Sumber Daya.
  - `[Kind <String>]`: Jenis sumber daya.
  - `[Tag <IResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[ClientAffinityEnabled <Boolean?>]`: <code>true</code> untuk mengaktifkan afinitas klien; <code>false</code> untuk berhenti mengirim cookie afinitas sesi, yang merutekan permintaan klien dalam sesi yang sama ke instans yang sama. Defaultnya adalah <code>true</code>.
  - `[ClientCertEnabled <Boolean?>]`: <code>true</code> untuk mengaktifkan autentikasi sertifikat klien (autentikasi bersama TLS); jika tidak, <code>false</code>. Defaultnya adalah <code>false</code>.
  - `[ClientCertExclusionPath <String>]`: jalur pengecualian yang dipisahkan koma autentikasi sertifikat klien
  - `[CloningInfoAppSettingsOverride <ICloningInfoAppSettingsOverrides>]`: Penimpaan pengaturan aplikasi untuk aplikasi kloning. Jika ditentukan, pengaturan ini akan mengambil alih pengaturan yang dikloning dari aplikasi sumber. Jika tidak, pengaturan aplikasi dari aplikasi sumber dipertahankan.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[CloningInfoCloneCustomHostName <Boolean?>]`: <code>true</code> untuk mengkloning nama host kustom dari aplikasi sumber; jika tidak, <code>false</code>.
  - `[CloningInfoCloneSourceControl <Boolean?>]`: <code>true</code> untuk mengkloning kontrol sumber dari aplikasi sumber; jika tidak, <code>false</code>.
  - `[CloningInfoConfigureLoadBalancing <Boolean?>]`: <code>true</code> untuk mengonfigurasi penyeimbangan beban untuk aplikasi sumber dan tujuan.
  - `[CloningInfoCorrelationId <String>]`: ID korelasi operasi kloning. ID ini mengikat beberapa operasi kloning bersama-sama untuk menggunakan rekam jepret yang sama.
  - `[CloningInfoHostingEnvironment <String>]`: lingkungan App Service.
  - `[CloningInfoOverwrite <Boolean?>]`: <code>true</code> untuk menimpa aplikasi tujuan; jika tidak, <code>false</code>.
  - `[CloningInfoSourceWebAppId <String>]`: ID sumber daya ARM dari aplikasi sumber. ID sumber daya aplikasi adalah formulir /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/sites/{siteName} untuk slot produksi dan /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/sites/{siteName}/slots/{slotName} untuk slot lain.
  - `[CloningInfoSourceWebAppLocation <String>]`: Lokasi aplikasi sumber misalnya: US Barat atau Eropa Utara
  - `[CloningInfoTrafficManagerProfileId <String>]`: ID sumber daya ARM dari profil Traffic Manager untuk digunakan, jika ada. Traffic Manager ID sumber daya adalah formulir /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/trafficManagerProfiles/{profileName}.
  - `[CloningInfoTrafficManagerProfileName <String>]`: Nama profil Traffic Manager untuk dibuat. Ini hanya diperlukan jika profil Traffic Manager belum ada.
  - `[Config <ISiteConfig>]`: Konfigurasi aplikasi.
    - `[AcrUseManagedIdentityCred <Boolean?>]`: Bendera untuk menggunakan Kredensial Identitas Terkelola untuk penarikan ACR
    - `[AcrUserManagedIdentityId <String>]`: Jika menggunakan identitas terkelola pengguna, identitas terkelola pengguna ClientId
    - `[ActionMinProcessExecutionTime <String>]`: Waktu minimum proses harus dijalankan sebelum mengambil tindakan
    - `[ActionType <AutoHealActionType?>]`: Tindakan yang telah ditentukan sebelumnya yang akan diambil.
    - `[AlwaysOn <Boolean?>]`: <code>true</code> jika Always On diaktifkan; jika tidak, <code>false</code>.
    - `[ApiDefinitionUrl <String>]`: URL definisi API.
    - `[ApiManagementConfigId <String>]`: pengidentifikasi APIM-Api.
    - `[AppCommandLine <String>]`: Baris perintah aplikasi untuk diluncurkan.
    - `[AppSetting <INameValuePair[]>]`: Pengaturan aplikasi.
      - `[Name <String>]`: Nama pasangan.
      - `[Value <String>]`: Nilai pasangan.
    - `[AutoHealEnabled <Boolean?>]`: <code>true</code> jika Auto Heal diaktifkan; jika tidak, <code>false</code>.
    - `[AutoSwapSlotName <String>]`: Nama slot pertukaran otomatis.
    - `[ConnectionString <IConnStringInfo[]>]`: String koneksi.
      - `[ConnectionString <String>]`: Nilai string koneksi.
      - `[Name <String>]`: Nama string koneksi.
      - `[Type <ConnectionStringType?>]`: Jenis database.
    - `[CorAllowedOrigin <String[]>]`: Mendapatkan atau menetapkan daftar asal yang harus diizinkan untuk melakukan panggilan lintas asal (misalnya: http://example.com:12345). Gunakan "*" untuk mengizinkan semua.
    - `[CorSupportCredentials <Boolean?>]`: Mendapatkan atau mengatur apakah permintaan CORS dengan kredensial diizinkan. Lihat         https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS#Requests_with_credentials         untuk detail selengkapnya.
    - `[CustomActionExe <String>]`: Dapat dieksekusi untuk dijalankan.
    - `[CustomActionParameter <String>]`: Parameter untuk executable.
    - `[DefaultDocument <String[]>]`: Dokumen default.
    - `[DetailedErrorLoggingEnabled <Boolean?>]`: <code>true</code> jika pencatatan kesalahan terperinci diaktifkan; jika tidak, <code>false</code>.
    - `[DocumentRoot <String>]`: Akar dokumen.
    - `[DynamicTagsJson <String>]`: Mendapatkan atau menetapkan string JSON yang berisi daftar tag dinamis yang akan dievaluasi dari klaim pengguna di titik akhir pendaftaran pendorongan.
    - `[ExperimentRampUpRule <IRampUpRule[]>]`: Daftar aturan ramp-up.
      - `[ActionHostName <String>]`: Nama host slot tempat lalu lintas akan dialihkan jika diputuskan. Mis. myapp-stage.azurewebsites.net.
      - `[ChangeDecisionCallbackUrl <String>]`: Algoritma keputusan kustom dapat disediakan di ekstensi situs TiPCallback url mana yang dapat ditentukan. Lihat Ekstensi situs TiPCallback untuk perancah dan kontrak.         https://www.siteextensions.net/packages/TiPCallback/
      - `[ChangeIntervalInMinute <Int32?>]`: Menentukan interval dalam menit untuk mengevaluasi ulang ReroutePercentage.
      - `[ChangeStep <Double?>]`: Dalam skenario peningkatan otomatis, ini adalah langkah untuk menambahkan/menghapus dari <code>ReroutePercentage</code> sampai mencapai \n<code>MinReroutePercentage</code> atau         <code>MaxReroutePercentage</code>. Metrik situs diperiksa setiap N menit yang ditentukan dalam <code>ChangeIntervalInMinutes</code>algoritma keputusan .\nKustom dapat disediakan di ekstensi situs TiPCallback yang URLnya dapat ditentukan di <code>ChangeDecisionCallbackUrl</code>.
      - `[MaxReroutePercentage <Double?>]`: Menentukan batas atas di bawah reroutePercentage yang akan tetap ada.
      - `[MinReroutePercentage <Double?>]`: Menentukan batas bawah di atas mana ReroutePercentage akan tetap ada.
      - `[Name <String>]`: Nama aturan perutean. Nama yang direkomendasikan adalah menunjuk ke slot yang akan menerima lalu lintas dalam eksperimen.
      - `[ReroutePercentage <Double?>]`: Persentase lalu lintas yang akan dialihkan ke <code>ActionHostName</code>.
    - `[FtpsState <FtpsState?>]`: Status layanan FTP/FTPS
    - `[HandlerMapping <IHandlerMapping[]>]`: Pemetaan handler.
      - `[Argument <String>]`: Argumen baris perintah yang akan diteruskan ke prosesor skrip.
      - `[Extension <String>]`: Permintaan dengan ekstensi ini akan ditangani menggunakan aplikasi FastCGI yang ditentukan.
      - `[ScriptProcessor <String>]`: Jalur absolut ke aplikasi FastCGI.
    - `[HealthCheckPath <String>]`: Jalur pemeriksaan kesehatan
    - `[Http20Enabled <Boolean?>]`: Http20Enabled: mengonfigurasi situs web untuk memungkinkan klien terhubung melalui http2.0
    - `[HttpLoggingEnabled <Boolean?>]`: <code>true</code> jika pengelogan HTTP diaktifkan; jika tidak, <code>false</code>.
    - `[IPSecurityRestriction <IIPSecurityRestriction[]>]`: Pembatasan keamanan IP untuk utama.
      - `[Action <String>]`: Izinkan atau Tolak akses untuk rentang IP ini.
      - `[Description <String>]`: Deskripsi aturan pembatasan IP.
      - `[IPAddress <String>]`: Alamat IP yang berlaku untuk pembatasan keamanan.         Ini bisa dalam bentuk alamat ipv4 murni (properti SubnetMask yang diperlukan) atau notasi CIDR seperti ipv4/mask (kecocokan bit terdepan). Untuk CIDR, properti SubnetMask tidak boleh ditentukan.
      - `[Name <String>]`: Nama aturan pembatasan IP.
      - `[Priority <Int32?>]`: Prioritas aturan pembatasan IP.
      - `[SubnetMask <String>]`: Subnet mask untuk rentang alamat IP yang berlaku untuk pembatasan.
      - `[SubnetTrafficTag <Int32?>]`: (internal) Tag lalu lintas subnet
      - `[Tag <IPFilterTag?>]`: Menentukan untuk apa filter IP ini akan digunakan. Ini untuk mendukung pemfilteran IP pada proksi.
      - `[VnetSubnetResourceId <String>]`: Id sumber daya jaringan virtual
      - `[VnetTrafficTag <Int32?>]`: (internal) tag lalu lintas Vnet
    - `[IsPushEnabled <Boolean?>]`: Mendapatkan atau mengatur bendera yang menunjukkan apakah titik akhir Push diaktifkan.
    - `[JavaContainer <String>]`: Kontainer Java.
    - `[JavaContainerVersion <String>]`: Versi kontainer Java.
    - `[JavaVersion <String>]`: Versi Java.
    - `[LimitMaxDiskSizeInMb <Int64?>]`: Penggunaan ukuran disk maksimum yang diizinkan dalam MB.
    - `[LimitMaxMemoryInMb <Int64?>]`: Penggunaan memori maksimum yang diizinkan dalam MB.
    - `[LimitMaxPercentageCpu <Double?>]`: Persentase penggunaan CPU maksimum yang diizinkan.
    - `[LinuxFxVersion <String>]`: Linux App Framework dan versi
    - `[LoadBalancing <SiteLoadBalancing?>]`: Penyeimbangan beban situs.
    - `[LocalMySqlEnabled <Boolean?>]`: <code>true</code> untuk mengaktifkan MySQL lokal; jika tidak, <code>false</code>.
    - `[LogsDirectorySizeLimit <Int32?>]`: Batas ukuran direktori log HTTP.
    - `[MachineKeyDecryption <String>]`: Algoritma yang digunakan untuk dekripsi.
    - `[MachineKeyDecryptionKey <String>]`: Kunci dekripsi.
    - `[MachineKeyValidation <String>]`: Validasi MachineKey.
    - `[MachineKeyValidationKey <String>]`: Kunci validasi.
    - `[ManagedPipelineMode <ManagedPipelineMode?>]`: Mode alur terkelola.
    - `[ManagedServiceIdentityId <Int32?>]`: Id Identitas Layanan Terkelola
    - `[MinTlsVersion <SupportedTlsVersions?>]`: MinTlsVersion: mengonfigurasi versi minimum TLS yang diperlukan untuk permintaan SSL
    - `[NetFrameworkVersion <String>]`: versi .NET Framework.
    - `[NodeVersion <String>]`: Versi Node.js.
    - `[NumberOfWorker <Int32?>]`: Jumlah pekerja.
    - `[PhpVersion <String>]`: Versi PHP.
    - `[PowerShellVersion <String>]`: Versi PowerShell.
    - `[PreWarmedInstanceCount <Int32?>]`: Jumlah instans preWarmed.         Pengaturan ini hanya berlaku untuk Paket Konsumsi dan Elastis
    - `[PublishingUsername <String>]`: Menerbitkan nama pengguna.
    - `[PushKind <String>]`: Jenis sumber daya.
    - `[PythonVersion <String>]`: Versi Python.
    - `[RemoteDebuggingEnabled <Boolean?>]`: <code>true</code> jika penelusuran kesalahan jarak jauh diaktifkan; jika tidak, <code>false</code>.
    - `[RemoteDebuggingVersion <String>]`: Versi penelusuran kesalahan jarak jauh.
    - `[RequestCount <Int32?>]`: Jumlah Permintaan.
    - `[RequestTimeInterval <String>]`: Interval waktu.
    - `[RequestTracingEnabled <Boolean?>]`: <code>true</code> jika pelacakan permintaan diaktifkan; jika tidak, <code>false</code>.
    - `[RequestTracingExpirationTime <DateTime?>]`: Meminta waktu kedaluwarsa pelacakan.
    - `[ScmIPSecurityRestriction <IIPSecurityRestriction[]>]`: Pembatasan keamanan IP untuk scm.
    - `[ScmIPSecurityRestrictionsUseMain <Boolean?>]`: Pembatasan keamanan IP untuk scm untuk menggunakan utama.
    - `[ScmType <ScmType?>]`: Jenis SCM.
    - `[SlowRequestCount <Int32?>]`: Jumlah Permintaan.
    - `[SlowRequestTimeInterval <String>]`: Interval waktu.
    - `[SlowRequestTimeTaken <String>]`: Waktu yang dibutuhkan.
    - `[TagWhitelistJson <String>]`: Mendapatkan atau mengatur string JSON yang berisi daftar tag yang diizinkan untuk digunakan oleh titik akhir pendaftaran push.
    - `[TagsRequiringAuth <String>]`: Mendapatkan atau mengatur string JSON yang berisi daftar tag yang mengharuskan autentikasi pengguna digunakan di titik akhir pendaftaran push.         Tag dapat terdiri dari karakter alfanumerik dan berikut ini: '_', '@', '#', '.', ':', '-'.         Validasi harus dilakukan di PushRequestHandler.
    - `[TracingOption <String>]`: Opsi pelacakan.
    - `[TriggerPrivateBytesInKb <Int32?>]`: Aturan berdasarkan byte privat.
    - `[TriggerStatusCode <IStatusCodesBasedTrigger[]>]`: Aturan berdasarkan kode status.
      - `[Count <Int32?>]`: Jumlah Permintaan.
      - `[Status <Int32?>]`: Kode status HTTP.
      - `[SubStatus <Int32?>]`: Minta Sub Status.
      - `[TimeInterval <String>]`: Interval waktu.
      - `[Win32Status <Int32?>]`: Kode kesalahan Win32.
    - `[Use32BitWorkerProcess <Boolean?>]`: <code>true</code> untuk menggunakan proses pekerja 32-bit; jika tidak, <code>false</code>.
    - `[VirtualApplication <IVirtualApplication[]>]`: Aplikasi virtual.
      - `[PhysicalPath <String>]`: Jalur fisik.
      - `[PreloadEnabled <Boolean?>]`: <code>true</code> jika pramuat diaktifkan; jika tidak, <code>false</code>.
      - `[VirtualDirectory <IVirtualDirectory[]>]`: Direktori virtual untuk aplikasi virtual.
        - `[PhysicalPath <String>]`: Jalur fisik.
        - `[VirtualPath <String>]`: Jalur ke aplikasi virtual.
      - `[VirtualPath <String>]`: Jalur virtual.
    - `[VnetName <String>]`: nama Virtual Network.
    - `[WebSocketsEnabled <Boolean?>]`: <code>true</code> jika WebSocket diaktifkan; jika tidak, <code>false</code>.
    - `[WindowsFxVersion <String>]`: Xenon App Framework dan versi
    - `[XManagedServiceIdentityId <Int32?>]`: Id Identitas Layanan Terkelola Eksplisit
  - `[ContainerSize <Int32?>]`: Ukuran kontainer fungsi.
  - `[DailyMemoryTimeQuota <Int32?>]`: Kuota waktu memori harian maksimum yang diizinkan (hanya berlaku pada aplikasi dinamis).
  - `[Enabled <Boolean?>]`: <code>true</code> jika aplikasi diaktifkan; jika tidak, <code>false</code>. Mengatur nilai ini ke false menonaktifkan aplikasi (membuat aplikasi offline).
  - `[HostNameSslState <IHostNameSslState[]>]`: Status SSL nama host digunakan untuk mengelola pengikatan SSL untuk nama host aplikasi.
    - `[HostType <HostType?>]`: Menunjukkan apakah nama host adalah nama host standar atau repositori.
    - `[Name <String>]`: Nama host.
    - `[SslState <SslState?>]`: Jenis SSL.
    - `[Thumbprint <String>]`: Thumbprint sertifikat SSL.
    - `[ToUpdate <Boolean?>]`: Atur ke <code>true</code> untuk memperbarui nama host yang ada.
    - `[VirtualIP <String>]`: Alamat IP virtual yang ditetapkan ke nama host jika SSL berbasis IP diaktifkan.
  - `[HostNamesDisabled <Boolean?>]`: <code>true</code> untuk menonaktifkan nama host publik aplikasi; jika tidak, <code>false</code>.          Jika <code>true</code>, aplikasi hanya dapat diakses melalui proses manajemen API.
  - `[HostingEnvironmentProfileId <String>]`: ID sumber daya lingkungan App Service.
  - `[HttpsOnly <Boolean?>]`: HttpsOnly: mengonfigurasi situs web untuk hanya menerima permintaan https. Masalah pengalihan untuk permintaan http
  - `[HyperV <Boolean?>]`: Kotak pasir Hyper-V.
  - `[IdentityType <ManagedServiceIdentityType?>]`: Jenis identitas layanan terkelola.
  - `[IdentityUserAssignedIdentity <IManagedServiceIdentityUserAssignedIdentities>]`: Daftar identitas yang ditetapkan pengguna yang terkait dengan sumber daya. Referensi kunci kamus identitas pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}
    - `[(Any) <IComponents1Jq1T4ISchemasManagedserviceidentityPropertiesUserassignedidentitiesAdditionalproperties>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[IsXenon <Boolean?>]`: Usang: Kotak pasir Hyper-V.
  - `[RedundancyMode <RedundancyMode?>]`: Mode redundansi situs
  - `[Reserved <Boolean?>]`: <code>true</code> jika dicadangkan; jika tidak, <code>false</code>.
  - `[ScmSiteAlsoStopped <Boolean?>]`: <code>true</code> untuk menghentikan situs SCM (KUDU) ketika aplikasi dihentikan; jika tidak, <code>false</code>. Defaultnya adalah <code>false</code>.
  - `[ServerFarmId <String>]`: ID sumber daya dari paket App Service terkait, diformat sebagai: "/subscriptions/{subscriptionID}/resourceGroups/{groupName}/providers/Microsoft.Web/serverfarms/{appServicePlanName}".

## RELATED LINKS

