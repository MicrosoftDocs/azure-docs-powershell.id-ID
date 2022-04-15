---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azadapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADApplication.md
ms.openlocfilehash: 19bd3be45a2799b7d293dcc77e8c03866dcd1b08
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142429824"
---
# Remove-AzADApplication

## SYNOPSIS
Menghapus entitas dari aplikasi

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

## SYNTAX

### ObjectIdParameterSet (Default)
```
Remove-AzADApplication -ObjectId <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationIdParameterSet
```
Remove-AzADApplication -ApplicationId <Guid> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationDisplayNameParameterSet
```
Remove-AzADApplication -DisplayName <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectParameterSet
```
Remove-AzADApplication -InputObject <IMicrosoftGraphApplication> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus entitas dari aplikasi

## EXAMPLES

### Contoh 1: Hapus aplikasi menurut nama tampilan
```powershell
Remove-AzADApplication -DisplayName $name
```

Menghapus aplikasi menurut nama tampilan

### Contoh 2: Hapus aplikasi menurut input pipeline
```powershell
Get-AzADApplication -ObjectId $id | Remove-AzADApplication
```

Hapus aplikasi menurut input saluran

## PARAMETERS

### -ApplicationId
kunci: id aplikasi

```yaml
Type: System.Guid
Parameter Sets: ApplicationIdParameterSet
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
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
kunci: nama tampilan aplikasi

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

### -InputObject
Objek aplikasi, dapat digunakan sebagai input saluran.
Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
kunci: id objek aplikasi

```yaml
Type: System.String
Parameter Sets: ObjectIdParameterSet
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMicrosoftGraphApplication>: Objek aplikasi, dapat digunakan sebagai input pipeline.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan oleh layanan pengkonsumsi untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan seperti Office 365 memanggil aplikasi dalam konteks dokumen yang sedang dikerjakan pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[Api <IMicrosoftGraphApiApplication>]`: apiAplikasi
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AcceptMappedClaim <Boolean?>]`: Bila true, memungkinkan aplikasi untuk menggunakan pemetaan klaim tanpa menentukan kunci penandatanganan kustom.
    - `[KnownClientApplication <String[]>]`: Digunakan untuk persetujuan pembundelan jika Anda memiliki solusi yang berisi dua bagian: aplikasi klien dan aplikasi API web kustom. Jika Anda mengatur ID aplikasi klien ke nilai ini, pengguna hanya menyetujui satu kali ke aplikasi klien. Azure AD tahu bahwa menyetujui klien berarti secara implisit menyetujui API web dan secara otomatis menyediakan pokok layanan untuk kedua API pada saat yang sama. Baik klien maupun aplikasi API web harus didaftarkan dalam penyewa yang sama.
    - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Definisi izin yang didelegasikan yang diekspos oleh API web yang diwakili oleh pendaftaran aplikasi ini. Izin yang didelegasikan ini dapat diminta oleh aplikasi klien, dan dapat diberikan oleh pengguna atau administrator selama persetujuan. Izin yang didelegasikan terkadang disebut sebagai lingkup OAuth 2.0.
      - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibacakan oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin berskala penyewa.
      - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
      - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik di dalam kumpulan izin yang didelegasikan yang ditentukan untuk aplikasi sumber daya.
      - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, izin mungkin dihapus.
      - `[Origin <String>]`: 
      - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diwajibkan untuk persetujuan atas izin tersebut. Ini akan menjadi perilaku default, tetapi setiap pelanggan bisa memilih untuk mengkustomisasi perilaku di organisasi mereka (dengan memperbolehkan, membatasi atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
      - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
      - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
      - `[Value <String>]`: Menentukan nilai untuk disertakan dalam klaim scp (lingkup) dalam token akses. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
    - `[PreAuthorizedApplication <IMicrosoftGraphPreAuthorizedApplication[]>]`: Mencantumkan aplikasi klien yang telah diotorisasi sebelumnya dengan izin yang didelegasikan yang ditentukan untuk mengakses API aplikasi ini. Pengguna tidak diharuskan untuk menyetujui aplikasi apa pun yang telah diotorisasi sebelumnya (untuk izin yang ditentukan). Namun, izin tambahan apa pun yang tidak tercantum dalam Aplikasi PraOtorisasi (diminta melalui persetujuan tambahan misalnya) akan memerlukan persetujuan pengguna.
      - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi.
      - `[DelegatedPermissionId <String[]>]`: Pengidentifikasi unik untuk oauth2PermissionScopes aplikasi memerlukan.
    - `[RequestedAccessTokenVersion <Int32?>]`: Menentukan versi token akses yang diharapkan oleh sumber daya ini. Tindakan ini mengubah versi dan format JWT yang dihasilkan terpisah dari titik akhir atau klien yang digunakan untuk meminta token akses.  Titik akhir yang digunakan, v1.0 atau v2.0, dipilih oleh klien dan hanya memengaruhi versi id_tokens. Sumber daya perlu secara eksplisit mengonfigurasi RequestedAccessTokenVersion untuk menunjukkan format token akses yang didukung.  Nilai yang mungkin untuk requestedAccessTokenVersion adalah 1, 2, atau null. Jika nilainya null, nilai ini defaultnya adalah 1, yang terkait dengan titik akhir v1.0.  Jika signInAudience pada aplikasi dikonfigurasi sebagai AzureADandPersonalMicrosoftAccount, nilai untuk properti ini harus 2
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Kumpulan peran yang ditetapkan pada aplikasi. Dengan penetapan peran aplikasi, peran ini dapat ditetapkan kepada pengguna, grup, atau prinsipal layanan yang terkait dengan aplikasi lain. Tidak bisa ditipu.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lain (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lain juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditentukan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran aplikasi dan persetujuan.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam koleksi setuju. Saat membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus peran, ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, peran ini mungkin dihapus.
    - `[Value <String>]`: Menentukan nilai untuk disertakan dalam peran yang diklaim dalam token ID dan token akses yang mengautentikasi pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[ApplicationTemplateId <String>]`: Pengidentifikasi unik aplikasiTemplate.
  - `[CreatedOnBehalfOfDeletedDateTime <DateTime?>]`: 
  - `[CreatedOnBehalfOfDisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional aplikasi. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi yang terdaftar. Nilai yang memungkinkan adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasannya mungkin termasuk aktivitas mencurigakan, kasar, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[GroupMembershipClaim <String>]`: Mengonfigurasi klaim grup yang dikeluarkan dalam pengguna atau token akses OAuth 2.0 yang diharapkan oleh aplikasi. Untuk mengatur atribut ini, gunakan salah satu nilai string berikut ini: Tidak ada, Grup Keamanan (untuk grup keamanan dan peran Azure AD), Semua (ini mendapatkan semua grup keamanan, grup distribusi, dan peran direktori Azure AD bahwa pengguna yang masuk adalah anggotanya).
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[IdentifierUri <String[]>]`: URI yang mengidentifikasi aplikasi dalam penyewa Azure AD, atau dalam domain kustom terverifikasi jika aplikasi multi-penyewa. Untuk informasi selengkapnya, lihat Objek Aplikasi dan Objek Pokok Layanan. Operator apa pun diperlukan untuk memfilter ekspresi pada properti multinilai. Tidak bisa ditipu. Mendukung $filter (eq, ne, ge, le, startsWith).
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Tautan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Tautan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Tautan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Tautan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[IsDeviceOnlyAuthSupported <Boolean?>]`: Menentukan apakah aplikasi ini mendukung autentikasi perangkat tanpa pengguna. Defaultnya adalah false.
  - `[IsFallbackPublicClient <Boolean?>]`: Menentukan tipe aplikasi fallback sebagai klien publik, seperti aplikasi yang diinstal yang berjalan di perangkat seluler. Nilai default adalah false yang berarti tipe aplikasi fallback adalah klien rahasia seperti aplikasi web. Terdapat skenario tertentu ketika Azure AD tidak dapat menentukan tipe aplikasi klien. Misalnya, alur ROPC tempat aplikasi dikonfigurasi tanpa menentukan URI pengalihan. Dalam kasus tersebut Azure AD menginterpretasikan tipe aplikasi berdasarkan nilai properti ini.
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Kumpulan kredensial kunci yang terkait dengan aplikasi. Tidak bisa ditipu. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah dikenali untuk kunci. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kredensial. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus berupa nilai dasar 64 yang dikodekan.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) untuk kunci tersebut.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu di mana kredensial menjadi valid. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Jenis kredensial kunci; misalnya, 'Simetris'.
    - `[Usage <String>]`: String yang menjelaskan tujuan penggunaan kunci; misalnya, 'Verifikasi'.
  - `[Logo <Byte[]>]`: Logo utama untuk aplikasi. Tidak bisa ditipu.
  - `[Note <String>]`: Catatan yang relevan untuk manajemen aplikasi.
  - `[Oauth2RequirePostResponse <Boolean?>]`: 
  - `[OptionalClaim <IMicrosoftGraphOptionalClaims>]`: OpsionalClaims
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AccessToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token akses JWT.
      - `[AdditionalProperty <String[]>]`: Properti tambahan klaim. Jika ada properti dalam koleksi ini, properti mengubah perilaku klaim opsional yang ditentukan dalam properti nama.
      - `[Essential <Boolean?>]`: Jika nilainya benar, klaim yang ditentukan oleh klien diperlukan untuk memastikan pengalaman otorisasi yang lancar untuk tugas tertentu yang diminta oleh pengguna akhir. Nilai defaultnya adalah false.
      - `[Name <String>]`: Nama klaim opsional.
      - `[Source <String>]`: Sumber (objek direktori) klaim. Ada klaim yang sudah ditentukan sebelumnya dan klaim yang ditentukan pengguna dari properti ekstensi. Jika nilai sumber null, klaim adalah klaim opsional yang sudah ditentukan sebelumnya. Jika nilai sumber adalah pengguna, nilai dalam properti nama adalah properti ekstensi dari objek pengguna.
    - `[IdToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token JWT ID.
    - `[Saml2Token <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token SAML.
  - `[ParentalControlSetting <IMicrosoftGraphParentalControlSettings>]`: parentalControlSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[CountriesBlockedForMinor <String[]>]`: Menentukan kode negara ISO dua huruf. Akses ke aplikasi akan diblokir untuk anak di bawah umur dari negara yang ditentukan dalam daftar ini.
    - `[LegalAgeGroupRule <String>]`: Menentukan aturan grup usia hukum yang berlaku untuk pengguna aplikasi. Dapat diatur ke salah satu nilai berikut: ValueDescriptionAllowDefault. Memberlakukan minimum hukum. Ini berarti persetujuan orang tua diperlukan untuk anak di bawah umur di Uni Eropa dan Korea.RequireConsentForPrivacyServicesEnforces pengguna untuk menentukan tanggal lahir agar mematuhi aturan COPPA. RequireConsentForMinorsPerlukan persetujuan orang tua untuk usia di bawah 18 tahun, terlepas dari aturan minor negara. RequireConsentForKidsPersyaratkan persetujuan orang tua untuk usia di bawah 14 tahun, terlepas dari aturan minor negara. BlockMinorsBlocks minors from using the app.
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Kumpulan kredensial kata sandi yang terkait dengan aplikasi. Tidak bisa ditipu.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah dikenali untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kata sandi yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu kata sandi menjadi valid. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[PublicClient <IMicrosoftGraphPublicClientApplication>]`: publicClientApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URL pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.
  - `[RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>]`: Menentukan sumber daya yang perlu diakses oleh aplikasi. Properti ini juga menentukan kumpulan lingkup izin OAuth dan peran aplikasi yang dibutuhkan untuk setiap sumber daya tersebut. Konfigurasi akses ke sumber daya yang diperlukan ini akan mendorong pengalaman persetujuan. Tidak bisa ditipu. Mendukung $filter (eq, NOT, ge, le).
    - `[ResourceAccess <IMicrosoftGraphResourceAccess[]>]`: Daftar lingkup izin OAuth2.0 dan peran aplikasi yang diperlukan aplikasi dari sumber daya yang ditentukan.
      - `[Id <String>]`: Pengidentifikasi unik untuk salah satu oauth2PermissionScopes atau instance appRole yang diekspos aplikasi sumber daya.
      - `[Type <String>]`: Menentukan apakah properti id mereferensikan oauth2PermissionScopes atau appRole. Nilai yang memungkinkan adalah Lingkup atau Peran.
    - `[ResourceAppId <String>]`: Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.  Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.
  - `[SignInAudience <String>]`: Menentukan akun Microsoft yang didukung untuk aplikasi saat ini. Nilai yang didukung adalah: AzureADMyOrg, AzureADMultipleOrgs, AzureADandPersonalMicrosoftAccount, PersonalMicrosoftAccount. Lihat selengkapnya dalam tabel di bawah ini. Mendukung $filter (eq, ne, NOT).
  - `[Spa <IMicrosoftGraphSpaApplication>]`: spaAplikasi
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URL pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.
  - `[Tag <String[]>]`: String kustom yang dapat digunakan untuk mengkategorikan dan mengidentifikasi aplikasi. Tidak bisa ditipu. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId kunci publik dari kumpulan keyCredentials. Ketika dikonfigurasi, Azure AD mengenkripsi semua token yang dipancarkannya menggunakan kunci tujuan properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci privat yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies yang ditetapkan ke aplikasi ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Web <IMicrosoftGraphWebApplication>]`: webAplikasi
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[HomePageUrl <String>]`: Laman atau halaman awal aplikasi.
    - `[ImplicitGrantSetting <IMicrosoftGraphImplicitGrantSettings>]`: implicitGrantSettings
      - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
      - `[EnableAccessTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token akses menggunakan alur implisit OAuth 2.0.
      - `[EnableIdTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token ID menggunakan alur implisit OAuth 2.0.
    - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk logout pengguna menggunakan protokol logout saluran depan, saluran belakang, atau SAML.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URL pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.

## RELATED LINKS

## RELATED LINKS
