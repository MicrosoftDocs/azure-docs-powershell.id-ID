---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/Remove-azadappcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADAppCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADAppCredential.md
ms.openlocfilehash: 12d4f535150aec8a707dc86a41dc32de4637347b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140049755"
---
# Remove-AzADAppCredential

## SYNOPSIS
Menghapus kredensial kunci atau kredensial kata sandi untuk aplikasi.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/remove-azadappcredential) untuk informasi terkini.

## SYNTAX

### ApplicationObjectIdWithKeyIdParameterSet (Default)
```
Remove-AzADAppCredential -ObjectId <String> [-KeyId <Guid>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ApplicationIdWithKeyIdParameterSet
```
Remove-AzADAppCredential [-KeyId <Guid>] -ApplicationId <Guid> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationDisplayNameParameterSet
```
Remove-AzADAppCredential [-KeyId <Guid>] -DisplayName <String> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithKeyIdParameterSet
```
Remove-AzADAppCredential [-KeyId <Guid>] -ApplicationObject <IMicrosoftGraphApplication>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus kredensial kunci atau kredensial kata sandi untuk aplikasi.

## EXAMPLES

### Contoh 1: Hapus kredensial dari aplikasi dengan id kunci
```powershell
PS C:\> Remove-AzADAppCredential -DisplayName $name -KeyId $keyid
```

Hapus kredensial dari aplikasi dengan id kunci

### Contoh 2: Hapus semua kredensial dari aplikasi
```powershell
PS C:\> Get-AzADApplication -DisplayName $name | Remove-AzADAppCredential
```

Hapus semua kredensial dari aplikasi

## PARAMETERS

### -ApplicationId
Id aplikasi.

```yaml
Type: System.Guid
Parameter Sets: ApplicationIdWithKeyIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationObject
Objek aplikasi, dapat digunakan sebagai input saluran.
Untuk membuat, lihat bagian CATATAN untuk properti APPLICATIONOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication
Parameter Sets: ApplicationObjectWithKeyIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Nama tampilan aplikasi.

```yaml
Type: System.String
Parameter Sets: ApplicationDisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyId
Id kunci kredensial yang akan dihapus.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Id objek aplikasi.

```yaml
Type: System.String
Parameter Sets: ApplicationObjectIdWithKeyIdParameterSet
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


APPLICATIONOBJECT <IMicrosoftGraphApplication>: Objek aplikasi, bisa digunakan sebagai input saluran.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan oleh layanan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan Office 365 panggilan aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[Api <IMicrosoftGraphApiApplication>]`: apiApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AcceptMappedClaim <Boolean?>]`: Bila benar, memperbolehkan aplikasi menggunakan pemetaan klaim tanpa menentukan kunci penandatanganan kustom.
    - `[KnownClientApplication <String[]>]`: Digunakan untuk persetujuan bunding jika Anda mempunyai solusi yang berisi dua komponen: aplikasi klien dan aplikasi web API kustom. Jika Anda menetapkan ID aplikasi aplikasi klien ke nilai ini, pengguna hanya menyetujui satu kali untuk aplikasi klien. Azure AD mengetahui bahwa persetujuan terhadap klien berarti secara implisit menyetujui API web dan secara otomatis menyediakan prinsipal layanan untuk kedua API secara bersamaan. Klien dan aplikasi API web harus terdaftar dalam penyewa yang sama.
    - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Definisi izin yang didelegasikan yang diekspos oleh API web yang diwakili oleh pendaftaran aplikasi ini. Izin yang didelegasikan ini mungkin diminta oleh aplikasi klien, dan dapat diberikan oleh pengguna atau administrator selama persetujuan. Izin yang didelegasikan terkadang disebut sebagai lingkup OAuth 2.0.
      - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin tingkat penyewa.
      - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
      - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik dalam kumpulan izin yang didelegasikan yang ditetapkan untuk aplikasi sumber daya.
      - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus diatur ke salah terlebih dahulu.  Pada tahap ini, dalam panggilan berikutnya, izin mungkin dihapus.
      - `[Origin <String>]`: 
      - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diperlukan untuk menyetujui izin. Ini akan menjadi perilaku default, tapi setiap pelanggan bisa memilih untuk mengkustomisasi perilaku di organisasi mereka (dengan mengizinkan, membatasi atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
      - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberi izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
      - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
      - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (lingkup) di token akses. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
    - `[PreAuthorizedApplication <IMicrosoftGraphPreAuthorizedApplication[]>]`: Mencantumkan aplikasi klien yang telah diberi otorisasi sebelumnya dengan izin delegasi tertentu untuk mengakses API aplikasi ini. Pengguna tidak diharuskan untuk menyetujui aplikasi apa pun yang telah diotorisasi (untuk izin yang ditentukan). Namun, setiap izin tambahan yang tidak tercantum dalam preAuthorizedApplications (diminta melalui persetujuan bertahap misalnya) akan memerlukan persetujuan pengguna.
      - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi.
      - `[DelegatedPermissionId <String[]>]`: Pengidentifikasi unik untuk oauth2PermissionScopes yang diperlukan aplikasi.
    - `[RequestedAccessTokenVersion <Int32?>]`: Menentukan versi token akses yang diharapkan oleh sumber daya ini. Hal ini akan mengubah versi dan format JWT yang dihasilkan terpisah dari titik akhir atau klien yang digunakan untuk meminta token akses.  Titik akhir yang digunakan, v1.0 atau v2.0, dipilih oleh klien dan hanya akan memengaruhi versi id_tokens. Sumber daya harus mengonfigurasi secara eksplisit requestedAccessTokenVersion untuk menunjukkan format token akses yang didukung.  Nilai yang mungkin untuk requestedAccessTokenVersion adalah 1, 2, atau null. Jika nilai null, defaultnya adalah 1, yang terkait dengan titik akhir v1.0.  Jika signInAudience pada aplikasi dikonfigurasi sebagai AzureADandPersonalMicrosoftAccount, nilai untuk properti ini harus 2
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Kumpulan peran yang ditetapkan pada aplikasi. Dengan penetapan peran aplikasi, peran ini dapat ditetapkan kepada pengguna, grup, atau prinsipal layanan yang terkait dengan aplikasi lainnya. Not nullable.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lainnya (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lainnya juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditetapkan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran dan persetujuan aplikasi.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam kumpulan peran aplikasi. Ketika membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus sebuah peran, ini harus terlebih dahulu disetel ke false.  Pada tahap ini, dalam panggilan berikutnya, peran ini mungkin dihapus.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran di token ID dan token akses yang mengotentikan pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[ApplicationTemplateId <String>]`: Pengidentifikasi unik aplikasiTemplate.
  - `[CreatedOnBehalfOfDeletedDateTime <DateTime?>]`: 
  - `[CreatedOnBehalfOfDisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional dari aplikasi. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi yang terdaftar. Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasan dapat mencantumkan aktivitas yang mencurigakan, melecehkan, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[GroupMembershipClaim <String>]`: Mengonfigurasi klaim grup yang diterbitkan di pengguna atau token akses OAuth 2.0 yang diharapkan oleh aplikasi. Untuk mengatur atribut ini, gunakan salah satu dari nilai string berikut ini: Tidak Ada, Grup Keamanan (untuk grup keamanan dan peran Azure AD), Semua (ini mendapatkan semua grup keamanan, grup distribusi, dan peran direktori Azure AD di mana pengguna yang masuk adalah anggotanya).
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[IdentifierUri <String[]>]`: URI yang mengidentifikasi aplikasi di dalam penyewa Azure AD-nya, atau di dalam domain kustom terverifikasi jika aplikasi tersebut multi-penyewa. Untuk informasi selengkapnya, lihat Objek Aplikasi dan Objek Prinsipal Layanan. Operator ini diperlukan untuk memfilter ekspresi pada properti multinilai. Not nullable. Mendukung $filter (eq, ne, ge, le, startsWith).
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Menautkan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Menautkan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Menautkan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Menautkan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[IsDeviceOnlyAuthSupported <Boolean?>]`: Menentukan apakah aplikasi ini mendukung autentikasi perangkat tanpa pengguna. Defaultnya adalah false.
  - `[IsFallbackPublicClient <Boolean?>]`: Menentukan tipe aplikasi fallback sebagai klien publik, seperti aplikasi terinstal yang berjalan pada perangkat seluler. Nilai default adalah false, yang berarti tipe aplikasi merupakan klien rahasia seperti aplikasi web. Terdapat skenario tertentu ketika Azure AD tidak dapat menentukan tipe aplikasi klien. Misalnya, aliran ROPC tempat aplikasi dikonfigurasi tanpa menentukan URI pengalihan. Dalam kasus tersebut, Azure AD menginterpretasikan tipe aplikasi berdasarkan nilai properti ini.
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Kumpulan kredensial kunci yang terkait dengan aplikasi. Not nullable. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kunci tersebut. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kredensial kedaluwarsa. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus merupakan nilai berkodekan 64 basis.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) kunci tersebut.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu saat kredensial menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Tipe kredensial kunci; misalnya, 'Simetri'.
    - `[Usage <String>]`: String yang menjelaskan tujuan untuk menggunakan kunci; misalnya, 'Verifikasi'.
  - `[Logo <Byte[]>]`: Logo utama aplikasi. Not nullable.
  - `[Note <String>]`: Catatan yang relevan untuk manajemen aplikasi.
  - `[Oauth2RequirePostResponse <Boolean?>]`: 
  - `[OptionalClaim <IMicrosoftGraphOptionalClaims>]`: optionalClaims
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AccessToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan di token akses JWT.
      - `[AdditionalProperty <String[]>]`: Properti tambahan klaim. Jika ada properti dalam kumpulan ini, properti ini mengubah perilaku klaim opsional yang ditentukan dalam properti nama.
      - `[Essential <Boolean?>]`: Jika nilai tersebut benar, klaim yang ditentukan oleh klien diperlukan untuk memastikan pengalaman otorisasi yang lancar untuk tugas tertentu yang diminta oleh pengguna akhir. Nilai default adalah false.
      - `[Name <String>]`: Nama klaim opsional.
      - `[Source <String>]`: Sumber (objek direktori) klaim. Ada klaim yang sudah ditentukan sebelumnya dan klaim yang ditentukan pengguna dari properti ekstensi. Jika nilai sumber null, klaim adalah klaim opsional yang sudah ditentukan sebelumnya. Jika nilai sumber adalah pengguna, nilai dalam properti nama adalah properti ekstensi dari objek pengguna.
    - `[IdToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan di token JWT ID.
    - `[Saml2Token <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional dikembalikan dalam token SAML.
  - `[ParentalControlSetting <IMicrosoftGraphParentalControlSettings>]`: parentalControlSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[CountriesBlockedForMinor <String[]>]`: Menentukan kode negara ISO dua huruf. Akses ke aplikasi akan diblokir untuk pengguna di bawah umur dari negara yang ditentukan dalam daftar ini.
    - `[LegalAgeGroupRule <String>]`: Menentukan aturan grup usia legal yang berlaku bagi pengguna aplikasi. Dapat diatur ke salah satu nilai berikut: ValueDescriptionAllowDefault. Menerapkan minimum hukum. Ini berarti persetujuan orang tua diperlukan untuk anak di bawah umur di Uni Eropa dan Korea.RequireConsentForPrivacyServicesEnforces pengguna untuk menentukan tanggal lahir untuk mematuhi aturan COPPA. RequireConsentForMinorsRequires parental consent for ages below 18, regardless of country minor rules. RequireConsentForKidsRequires parental consent for ages below 14, regardless of country minor rules. BlockMinorsBlocks minors tidak menggunakan aplikasi.
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Kumpulan kredensial kata sandi yang terkait dengan aplikasi. Not nullable.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kata sandi kedaluwarsa yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu valid ketika kata sandi menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[PublicClient <IMicrosoftGraphPublicClientApplication>]`: publicClientApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.
  - `[RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>]`: Menentukan sumber daya yang perlu diakses oleh aplikasi. Properti ini juga menentukan kumpulan lingkup izin OAuth dan peran aplikasi yang diperlukannya untuk setiap sumber daya tersebut. Konfigurasi akses ke sumber daya yang diperlukan ini akan mendorong pengalaman persetujuan. Not nullable. Mendukung $filter (eq, NOT, ge, le).
    - `[ResourceAccess <IMicrosoftGraphResourceAccess[]>]`: Daftar lingkup izin OAuth2.0 dan peran aplikasi yang diperlukan aplikasi dari sumber daya yang ditentukan.
      - `[Id <String>]`: Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang digunakan oleh aplikasi sumber daya.
      - `[Type <String>]`: Menentukan apakah properti id merujuk pada oauth2PermissionScopes atau appRole. Nilai yang mungkin adalah Lingkup atau Peran.
    - `[ResourceAppId <String>]`: Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.  Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.
  - `[SignInAudience <String>]`: Menentukan akun Microsoft yang didukung untuk aplikasi saat ini. Nilai yang didukung adalah: AzureADMyOrg, AzureADMultipleOrgs, AzureADandPersonalMicrosoftAccount, PersonalMicrosoftAccount. Lihat selengkapnya dalam tabel di bawah ini. Mendukung $filter (eq, ne, NOT).
  - `[Spa <IMicrosoftGraphSpaApplication>]`: spaApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.
  - `[Tag <String[]>]`: String kustom yang bisa digunakan untuk mengkategorikan dan mengidentifikasi aplikasi. Not nullable. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId dari kunci publik dari koleksi keyCredentials. Ketika dikonfigurasi, Azure AD mengenkripsi semua token yang disimpan dengan menggunakan kunci yang ditugasi properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci pribadi yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies ditetapkan untuk aplikasi ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Web <IMicrosoftGraphWebApplication>]`: webApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[HomePageUrl <String>]`: Laman atau halaman awal aplikasi.
    - `[ImplicitGrantSetting <IMicrosoftGraphImplicitGrantSettings>]`: implisitGrantSettings
      - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
      - `[EnableAccessTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token akses menggunakan aliran implisit OAuth 2.0.
      - `[EnableIdTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token ID menggunakan aliran implisit OAuth 2.0.
    - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk membuat logo pengguna menggunakan protokol logout saluran depan, saluran belakang, atau SAML.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.

## RELATED LINKS

## RELATED LINKS
