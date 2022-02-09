---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/stop-azfunctionapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Stop-AzFunctionApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Stop-AzFunctionApp.md
ms.openlocfilehash: a132c7cccaff267fb50fa349df681e199b163e71
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138272667"
---
# Stop-AzFunctionApp

## SYNOPSIS
Menghentikan aplikasi fungsi.

## SYNTAX

### StopByName (Default)
```
Stop-AzFunctionApp -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-Force]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ByObjectInput
```
Stop-AzFunctionApp -InputObject <ISite> [-Force] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Menghentikan aplikasi fungsi.

## EXAMPLES

### Contoh 1: Get a function app by name and stop it.
```powershell
PS C:\> Get-AzFunctionApp -Name MyAppName -ResourceGroupName MyResourceGroupName | Stop-AzFunctionApp -Force
```

Perintah ini mendapatkan aplikasi fungsi berdasarkan nama dan menghentikannya.

### Contoh 2: Hentikan fungsi aplikasi menurut nama.
```powershell
PS C:\> Stop-AzFunctionApp -Name MyAppName -ResourceGroupName MyResourceGroupName -Force
```

Perintah ini menghentikan aplikasi fungsi menurut nama.

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

### -Force
Memaksa cmdlet untuk menghentikan aplikasi fungsi tanpa meminta konfirmasi.

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

### -InputObject
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Nama
Nama aplikasi fungsi.

```yaml
Type: System.String
Parameter Sets: StopByName
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
Parameter Sets: StopByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure.

```yaml
Type: System.String
Parameter Sets: StopByName
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.ISite

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ISite>: 
  - `Location <String>`: Lokasi Sumber Daya.
  - `[Kind <String>]`: Jenis sumber daya.
  - `[Tag <IResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[ClientAffinityEnabled <Boolean?>]`: <code>true</code> untuk mengaktifkan afiliasi klien; <code>false</code> untuk menghentikan pengiriman cookie afiliasi sesi, yang merutekan permintaan klien dalam sesi yang sama ke contoh yang sama. Defaultnya adalah <code>true</code>.
  - `[ClientCertEnabled <Boolean?>]`: <code>true</code> untuk mengaktifkan autentikasi sertifikat klien (autentikasi bersama TLS); jika tidak, <code>false</code>. Defaultnya adalah <code>false</code>.
  - `[ClientCertExclusionPath <String>]`: jalur pengecualian yang dipisahkan oleh sertifikat klien
  - `[CloningInfoAppSettingsOverride <ICloningInfoAppSettingsOverrides>]`: Pengaturan aplikasi menjadi kesampingkan untuk aplikasi kloning. Jika ditentukan, pengaturan ini menimpa pengaturan yang dikloning dari aplikasi sumber. Jika tidak, pengaturan aplikasi dari aplikasi sumber akan dipertahankan.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[CloningInfoCloneCustomHostName <Boolean?>]`: <code>true</code> untuk kloning nama host kustom dari aplikasi sumber; jika tidak, <code>false</code>.
  - `[CloningInfoCloneSourceControl <Boolean?>]`: <code>true</code> untuk kloning kontrol sumber dari aplikasi sumber; jika tidak, <code>false</code>.
  - `[CloningInfoConfigureLoadBalancing <Boolean?>]`: <code>true</code> untuk mengonfigurasi keseimbangan muat untuk aplikasi sumber dan tujuan.
  - `[CloningInfoCorrelationId <String>]`: ID korelasi operasi mengkenggasi. ID ini ties beberapa operasi mengkliping bersamaan untuk menggunakan snapshot yang sama.
  - `[CloningInfoHostingEnvironment <String>]`: Lingkungan Layanan Aplikasi.
  - `[CloningInfoOverwrite <Boolean?>]`: <code>true</code> untuk menimpa aplikasi tujuan; jika tidak, <code>false</code>.
  - `[CloningInfoSourceWebAppId <String>]`: ARM resource ID dari aplikasi sumber. ID sumber daya aplikasi merupakan formulir /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/sites/{siteName} untuk slot produksi dan /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/sites/{siteName}/slot/{slotName} untuk slot lainnya.
  - `[CloningInfoSourceWebAppLocation <String>]`: Lokasi aplikasi sumber, mis: As Barat atau Eropa Utara
  - `[CloningInfoTrafficManagerProfileId <String>]`: ARM resource ID dari Traffic Manager profil untuk digunakan, jika ada. Traffic Manager ID sumber daya merupakan formulir /subscriptions/{subId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/trafficManagerProfiles/{profileName}.
  - `[CloningInfoTrafficManagerProfileName <String>]`: Nama Traffic Manager profil untuk dibuat. Hal ini hanya diperlukan Traffic Manager profil pengguna belum ada.
  - `[Config <ISiteConfig>]`: Konfigurasi aplikasi.
    - `[ActionMinProcessExecutionTime <String>]`: Waktu minimum proses harus dijalankan sebelum melakukan tindakan
    - `[ActionType <AutoHealActionType?>]`: Tindakan yang sudah ditentukan sebelumnya akan diambil.
    - `[AlwaysOn <Boolean?>]`: <code>true</code> jika Selalu Aktif diaktifkan; jika tidak, <code>false</code>.
    - `[ApiDefinitionUrl <String>]`: URL definisi API.
    - `[ApiManagementConfigId <String>]`: APIM-Api Pengidentifikasi.
    - `[AppCommandLine <String>]`: Baris perintah aplikasi untuk meluncurkan.
    - `[AppSetting <INameValuePair[]>]`: Pengaturan aplikasi.
      - `[Name <String>]`: Pasangkan nama.
      - `[Value <String>]`: Pasangkan nilai.
    - `[AutoHealEnabled <Boolean?>]`: <code>true</code> jika Deteksi Otomatis Diaktifkan; jika tidak, <code>false</code>.
    - `[AutoSwapSlotName <String>]`: Tukar nama slot otomatis.
    - `[ConnectionString <IConnStringInfo[]>]`: String koneksi.
      - `[ConnectionString <String>]`: Nilai string koneksi.
      - `[Name <String>]`: Nama string koneksi.
      - `[Type <ConnectionStringType?>]`: Tipe database.
    - `[CorAllowedOrigin <String[]>]`: Mendapatkan atau mengatur daftar asal yang seharusnya diperbolehkan melakukan panggilan lintas negara (misalnya: http://example.com:12345). Gunakan "*" untuk mengizinkan semua.
    - `[CorSupportCredentials <Boolean?>]`: Mendapatkan atau mengatur apakah permintaan CORS dengan kredensial diizinkan. Lihat         https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS#Requests_with_credentials         detail selengkapnya.
    - `[CustomActionExe <String>]`: Dapat dijalankan untuk dijalankan.
    - `[CustomActionParameter <String>]`: Parameter untuk file yang dapat dijalankan.
    - `[DefaultDocument <String[]>]`: Dokumen default.
    - `[DetailedErrorLoggingEnabled <Boolean?>]`: <code>true</code> jika pembuatan log kesalahan mendetail diaktifkan; jika tidak, <code>false</code>.
    - `[DocumentRoot <String>]`: Akar dokumen.
    - `[DynamicTagsJson <String>]`: Mendapatkan atau mengatur string JSON yang berisi daftar tag dinamis yang akan dievaluasi dari klaim pengguna dalam titik akhir pendaftaran push.
    - `[ExperimentRampUpRule <IRampUpRule[]>]`: Daftar aturan yang harus ditindaklanjuti.
      - `[ActionHostName <String>]`: Nama host slot yang akan dialihkan lalu lintas jika ditentukan. Misalnya myapp-stage.azurewebsites.net.
      - `[ChangeDecisionCallbackUrl <String>]`: Custom decision algorithm can be provided in TiPCallback site extension which URL can be specified. See TiPCallback site extension for the scaffold and contracts.         https://www.siteextensions.net/packages/TiPCallback/
      - `[ChangeIntervalInMinute <Int32?>]`: Menentukan interval dalam menit untuk mengevaluasi ulang ReroutePercentage.
      - `[ChangeStep <Double?>]`: Dalam skenario naik secara otomatis ini adalah langkah untuk menambahkan/menghapus <code>ReroutePercentage</code> dari sampai mencapai \n<code>MinReroutePercentage</code> atau         <code>MaxReroutePercentage</code>. Site metrics are checked every N minutes specified in <code>ChangeIntervalInMinutes</code>.\nCustom decision algorithm can be provided in TiPCallback site extension which URL can be specified in <code>ChangeDecisionCallbackUrl</code>.
      - `[MaxReroutePercentage <Double?>]`: Menentukan batas atas di bawah di mana Perekanan Ulang akan tetap ada.
      - `[MinReroutePercentage <Double?>]`: Menentukan batas bawah di atas di mana Perekanan Ulang akan tetap ada.
      - `[Name <String>]`: Nama aturan perutean. Nama yang disarankan harus mengarah ke slot yang akan menerima lalu lintas dalam eksperimen.
      - `[ReroutePercentage <Double?>]`: Persentase lalu lintas yang akan dialihkan ke <code>ActionHostName</code>.
    - `[FtpsState <FtpsState?>]`: Status layanan FTP / FTPS
    - `[HandlerMapping <IHandlerMapping[]>]`: Pemetaan penanganan.
      - `[Argument <String>]`: Argumen baris perintah untuk diteruskan ke prosesor skrip.
      - `[Extension <String>]`: Permintaan dengan ekstensi ini akan ditangani menggunakan aplikasi FastCGI yang ditentukan.
      - `[ScriptProcessor <String>]`: Jalur absolut ke aplikasi FastCGI.
    - `[HealthCheckPath <String>]`: Jalur pemeriksaan kesehatan
    - `[Http20Enabled <Boolean?>]`: Http20Enabled: mengonfigurasi situs web untuk memungkinkan klien tersambung melalui http2.0
    - `[HttpLoggingEnabled <Boolean?>]`: <code>true</code> jika pembuatan log HTTP diaktifkan; jika tidak, <code>false</code>.
    - `[IPSecurityRestriction <IIPSecurityRestriction[]>]`: Pembatasan keamanan IP untuk utama.
      - `[Action <String>]`: Memperbolehkan atau Menolak akses untuk rentang IP ini.
      - `[Description <String>]`: Deskripsi aturan pembatasan IP.
      - `[IPAddress <String>]`: Alamat IP pembatasan keamanan berlaku untuk.         Alamat dapat berupa alamat ipv4 murni (properti SubnetMask yang diperlukan) atau notasi CIDR seperti ipv4/mask (kecocokan bit awal). Untuk properti CIDR, properti SubnetMask tidak harus ditentukan.
      - `[Name <String>]`: Nama aturan pembatasan IP.
      - `[Priority <Int32?>]`: Prioritas aturan pembatasan IP.
      - `[SubnetMask <String>]`: Masker subnet untuk rentang alamat IP yang memiliki batasan berlaku untuk.
      - `[SubnetTrafficTag <Int32?>]`: tag lalu lintas subnet (internal)
      - `[Tag <IPFilterTag?>]`: Menentukan untuk apa filter IP ini akan digunakan. Ini untuk mendukung pemfilteran IP di proksi.
      - `[VnetSubnetResourceId <String>]`: Id sumber daya jaringan virtual
      - `[VnetTrafficTag <Int32?>]`: tag lalu lintas Vnet (internal)
    - `[IsPushEnabled <Boolean?>]`: Mendapatkan atau mengatur bendera yang mengindikasikan apakah titik akhir Push diaktifkan.
    - `[JavaContainer <String>]`: Java container.
    - `[JavaContainerVersion <String>]`: Versi kontainer Java.
    - `[JavaVersion <String>]`: Versi Java.
    - `[LimitMaxDiskSizeInMb <Int64?>]`: Penggunaan ukuran disk maksimal yang diperbolehkan dalam MB.
    - `[LimitMaxMemoryInMb <Int64?>]`: Penggunaan maksimum memori yang diperbolehkan dalam MB.
    - `[LimitMaxPercentageCpu <Double?>]`: Maksimum persentase penggunaan CPU yang diperbolehkan.
    - `[LinuxFxVersion <String>]`: Linux App Framework dan versi
    - `[LoadBalancing <SiteLoadBalancing?>]`: Penyeimbangan muat situs.
    - `[LocalMySqlEnabled <Boolean?>]`: <code>true</code> untuk mengaktifkan MySQL lokal; jika tidak, <code>false</code>.
    - `[LogsDirectorySizeLimit <Int32?>]`: Log HTTP batas ukuran direktori.
    - `[MachineKeyDecryption <String>]`: Algoritma yang digunakan untuk dekripsi.
    - `[MachineKeyDecryptionKey <String>]`: Kunci dekripsi.
    - `[MachineKeyValidation <String>]`: Validasi MachineKey.
    - `[MachineKeyValidationKey <String>]`: Kunci validasi.
    - `[ManagedPipelineMode <ManagedPipelineMode?>]`: Mode saluran terkelola.
    - `[ManagedServiceIdentityId <Int32?>]`: ID Identitas Layanan Terkelola
    - `[MinTlsVersion <SupportedTlsVersions?>]`: MinTlsVersion: mengonfigurasi versi minimum TLS yang diperlukan untuk permintaan SSL
    - `[NetFrameworkVersion <String>]`: .NET Framework baru.
    - `[NodeVersion <String>]`: Versi Node.js.
    - `[NumberOfWorker <Int32?>]`: Jumlah pekerja.
    - `[PhpVersion <String>]`: Versi PHP.
    - `[PowerShellVersion <String>]`: Versi PowerShell.
    - `[PreWarmedInstanceCount <Int32?>]`: Jumlah instans yang ada di tempat ini.         Pengaturan ini hanya berlaku untuk Paket Konsumsi dan Elastis
    - `[PublishingUsername <String>]`: Nama pengguna penerbitan.
    - `[PushKind <String>]`: Jenis sumber daya.
    - `[PythonVersion <String>]`: Versi Python.
    - `[RemoteDebuggingEnabled <Boolean?>]`: <code>true</code> jika penelusuran kesalahan jarak jauh diaktifkan; jika tidak, <code>false</code>.
    - `[RemoteDebuggingVersion <String>]`: Versi penelusuran kesalahan jarak jauh.
    - `[RequestCount <Int32?>]`: Jumlah Permintaan.
    - `[RequestTimeInterval <String>]`: Interval waktu.
    - `[RequestTracingEnabled <Boolean?>]`: <code>true</code> jika penelusuran permintaan diaktifkan; jika tidak, <code>false</code>.
    - `[RequestTracingExpirationTime <DateTime?>]`: Meminta waktu kedaluwarsa.
    - `[ScmIPSecurityRestriction <IIPSecurityRestriction[]>]`: Pembatasan keamanan IP untuk scm.
    - `[ScmIPSecurityRestrictionsUseMain <Boolean?>]`: Pembatasan keamanan IP agar scm digunakan utama.
    - `[ScmType <ScmType?>]`: Tipe SCM.
    - `[SlowRequestCount <Int32?>]`: Jumlah Permintaan.
    - `[SlowRequestTimeInterval <String>]`: Interval waktu.
    - `[SlowRequestTimeTaken <String>]`: Waktu yang diambil.
    - `[TagWhitelistJson <String>]`: Mendapatkan atau mengatur string JSON yang berisi daftar tag yang diizinkan untuk digunakan oleh titik akhir pendaftaran push.
    - `[TagsRequiringAuth <String>]`: Mendapatkan atau mengatur string JSON yang berisi daftar tag yang memerlukan autentikasi pengguna untuk digunakan dalam titik akhir pendaftaran push.         Tag dapat terdiri dari karakter alfanumerik dan yang berikut ini: '_', '@', '#', '.', ':', '-'.         Validasi harus dilakukan di PushRequestHandler.
    - `[TracingOption <String>]`: Opsi penelusuran.
    - `[TriggerPrivateBytesInKb <Int32?>]`: Aturan berdasarkan byte privat.
    - `[TriggerStatusCode <IStatusCodesBasedTrigger[]>]`: Aturan berdasarkan kode status.
      - `[Count <Int32?>]`: Jumlah Permintaan.
      - `[Status <Int32?>]`: Kode status HTTP.
      - `[SubStatus <Int32?>]`: Meminta Sub Status.
      - `[TimeInterval <String>]`: Interval waktu.
      - `[Win32Status <Int32?>]`: Kode kesalahan Win32.
    - `[Use32BitWorkerProcess <Boolean?>]`: <code>true</code> untuk menggunakan proses pekerja 32-bit; jika tidak, <code>false</code>.
    - `[VirtualApplication <IVirtualApplication[]>]`: Aplikasi virtual.
      - `[PhysicalPath <String>]`: Jalur fisik.
      - `[PreloadEnabled <Boolean?>]`: <code>true</code> jika pra-muat diaktifkan; jika tidak, <code>false</code>.
      - `[VirtualDirectory <IVirtualDirectory[]>]`: Direktori virtual untuk aplikasi virtual.
        - `[PhysicalPath <String>]`: Jalur fisik.
        - `[VirtualPath <String>]`: Jalur ke aplikasi virtual.
      - `[VirtualPath <String>]`: Jalur virtual.
    - `[VnetName <String>]`: Nama Jaringan Virtual.
    - `[WebSocketsEnabled <Boolean?>]`: <code>true</code> jika WebSocket diaktifkan; jika tidak, <code>false</code>.
    - `[WindowsFxVersion <String>]`: Dashboard App Framework dan versi
    - `[XManagedServiceIdentityId <Int32?>]`: Id Identitas Layanan terkelola eksplisit
  - `[ContainerSize <Int32?>]`: Ukuran wadah fungsi.
  - `[DailyMemoryTimeQuota <Int32?>]`: Maksimum kuota waktu memori harian yang diperbolehkan (hanya berlaku di aplikasi dinamis).
  - `[Enabled <Boolean?>]`: <code>true</code> jika aplikasi diaktifkan; jika tidak, <code>false</code>. Mengatur nilai ini ke false akan menonaktifkan aplikasi (membuat aplikasi offline).
  - `[HostNameSslState <IHostNameSslState[]>]`: Negara bagian SSL nama host digunakan untuk mengelola pengikatan SSL untuk nama host aplikasi.
    - `[HostType <HostType?>]`: Menunjukkan apakah nama host adalah nama host standar atau tempat penyimpanan.
    - `[Name <String>]`: Nama host.
    - `[SslState <SslState?>]`: Tipe SSL.
    - `[Thumbprint <String>]`: Thumbprint sertifikat SSL.
    - `[ToUpdate <Boolean?>]`: Atur untuk memperbarui <code>true</code> nama host yang sudah ada.
    - `[VirtualIP <String>]`: Alamat IP virtual ditetapkan ke nama host jika SSL berbasis IP diaktifkan.
  - `[HostNamesDisabled <Boolean?>]`: <code>true</code> untuk menonaktifkan nama host publik aplikasi; jika tidak, <code>false</code>.          Jika <code>true</code>, aplikasi hanya dapat diakses melalui proses manajemen API.
  - `[HostingEnvironmentProfileId <String>]`: ID Sumber Daya Dari Lingkungan Layanan Aplikasi.
  - `[HttpsOnly <Boolean?>]`: HttpsOnly: mengonfigurasi situs web untuk menerima permintaan https saja. Masalah pengalihan untuk permintaan http
  - `[HyperV <Boolean?>]`: Sandbox Hyper-V.
  - `[IdentityType <ManagedServiceIdentityType?>]`: Tipe identitas layanan terkelola.
  - `[IdentityUserAssignedIdentity <IManagedServiceIdentityUserAssignedIdentities>]`: Daftar identitas yang ditetapkan pengguna yang terkait dengan sumber daya. Referensi kunci kamus identitas pengguna akan menjadi ID sumber daya ARM di formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}
    - `[(Any) <IComponents1Jq1T4ISchemasManagedserviceidentityPropertiesUserassignedidentitiesAdditionalproperties>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[IsXenon <Boolean?>]`: Usang: sandbox Hyper-V.
  - `[RedundancyMode <RedundancyMode?>]`: Mode kelebihan situs
  - `[Reserved <Boolean?>]`: <code>true</code> jika dilindungi undang-undang; jika tidak, <code>false</code>.
  - `[ScmSiteAlsoStopped <Boolean?>]`: <code>true</code> untuk menghentikan situs SCM (KUDU) ketika aplikasi dihentikan; jika tidak, <code>false</code>. Defaultnya adalah <code>false</code>.
  - `[ServerFarmId <String>]`: ID Sumber Daya dari paket Layanan Aplikasi terkait, diformat sebagai: "/subscriptions/{subscriptionID}/resourceGroups/{groupName}/providers/Microsoft.Web/serverfarms/{appServicePlanName}".

## RELATED LINKS

