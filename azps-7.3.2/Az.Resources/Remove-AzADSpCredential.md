---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azadspcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADSpCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADSpCredential.md
ms.openlocfilehash: 0169400ad7b1f090b2c14bb7fb434082c3e9a941
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142341647"
---
# Remove-AzADSpCredential

## SYNOPSIS
Menghapus kredensial kunci atau kredensial kata sandi untuk prinsipal layanan.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/remove-azadspcredential) untuk informasi terbaru.

## SYNTAX

### ObjectIdWithKeyIdParameterSet (Default)
```
Remove-AzADSpCredential -ObjectId <String> [-KeyId <Guid>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SPNWithKeyIdParameterSet
```
Remove-AzADSpCredential [-KeyId <Guid>] -ServicePrincipalName <String> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayNameWithKeyIdParameterSet
```
Remove-AzADSpCredential [-KeyId <Guid>] -DisplayName <String> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalObjectParameterSet
```
Remove-AzADSpCredential [-KeyId <Guid>] -ServicePrincipalObject <IMicrosoftGraphServicePrincipal>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus kredensial kunci atau kredensial kata sandi untuk prinsipal layanan.

## EXAMPLES

### Contoh 1: Hapus kredensial pokok layanan menurut id kunci
```powershell
PS C:\> Remove-AzADSpCredential -DisplayName $name -KeyId $keyid
```

Hapus kredensial utama layanan menurut id kunci

### Contoh 2: Hapus semua kredensial dari prinsipal layanan
```powershell
PS C:\> Get-AzADServicePrincipal -DisplayName $name | Remove-AzADSpCredential
```

Menghapus semua kredensial dari prinsipal layanan

## PARAMETERS

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
Nama tampilan prinsipal layanan.

```yaml
Type: System.String
Parameter Sets: DisplayNameWithKeyIdParameterSet
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
Id objek pokok layanan.

```yaml
Type: System.String
Parameter Sets: ObjectIdWithKeyIdParameterSet
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

### -ServicePrincipalName
Nama pokok layanan.

```yaml
Type: System.String
Parameter Sets: SPNWithKeyIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipalObject
Objek pokok layanan, dapat digunakan sebagai input saluran.
Untuk membangun, lihat bagian CATATAN untuk properti SERVICEPRINCIPALOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal
Parameter Sets: ServicePrincipalObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

Remove-AzADServicePrincipalCredential

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


SERVICEPRINCIPALOBJECT <IMicrosoftGraphServicePrincipal>: Objek prinsipal layanan, dapat digunakan sebagai input saluran.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AccountEnabled <Boolean?>]`: true jika akun pokok layanan diaktifkan; jika tidak, false. Mendukung $filter (eq, ne, NOT, in).
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan oleh layanan pengkonsumsi untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan seperti Microsoft 365 memanggil aplikasi dalam konteks dokumen yang sedang dikerjakan pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[AlternativeName <String[]>]`: Digunakan untuk mengambil pokok layanan berdasarkan langganan, mengidentifikasi grup sumber daya dan id sumber daya penuh untuk identitas terkelola. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[AppDescription <String>]`: Deskripsi yang diekspos oleh aplikasi terkait.
  - `[AppDisplayName <String>]`: Nama tampilan yang diekspos oleh aplikasi terkait.
  - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi terkait (properti appId-nya).
  - `[AppOwnerOrganizationId <String>]`: Berisi id penyewa tempat aplikasi didaftarkan. Hal ini hanya berlaku untuk prinsipal layanan yang didukung oleh aplikasi. Mendukung $filter (eq, ne, NOT, ge, le).
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Peran yang diekspos oleh aplikasi yang diwakili oleh prinsipal layanan ini. Untuk informasi selengkapnya, lihat definisi properti yang disetujui pada entitas aplikasi. Tidak bisa ditipu.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lain (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lain juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditentukan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran aplikasi dan persetujuan.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam koleksi setuju. Saat membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus peran, ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, peran ini mungkin dihapus.
    - `[Value <String>]`: Menentukan nilai untuk disertakan dalam peran yang diklaim dalam token ID dan token akses yang mengautentikasi pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]`: Penetapan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan prinsipal layanan lainnya. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan ke prinsipal. Peran aplikasi ini harus diekspos dalam properti appRoles pada prinsipal layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default 00000000-0000-0000-00000000000000 dapat ditentukan untuk mengisyaratkan bahwa prinsipal ditetapkan ke aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan untuk membuat.
    - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup, atau prinsipal layanan yang diberi peran aplikasi. Diperlukan untuk membuat.
    - `[ResourceDisplayName <String>]`: Nama tampilan dari prinsipal layanan aplikasi sumber daya tempat tugas dibuat.
    - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk prinsipal layanan sumber daya tempat penugasan dibuat. Diperlukan untuk membuat. Mendukung $filter (eq saja).
  - `[AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>]`: Penetapan peran aplikasi untuk aplikasi atau layanan lain, diberikan kepada prinsipal layanan ini. Mendukung $expand.
  - `[AppRoleAssignmentRequired <Boolean?>]`: Menentukan apakah pengguna atau prinsipal layanan lain perlu diberi penetapan peran aplikasi untuk prinsipal layanan ini sebelum pengguna dapat masuk atau aplikasi dapat memperoleh token. Nilai defaultnya adalah false. Tidak bisa ditipu. Mendukung $filter (eq, ne, NOT).
  - `[ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]`: KlaimMappingPolicies yang ditetapkan untuk prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]`: Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili oleh prinsipal layanan ini. Mendukung $expand.
    - `[Classification <String>]`: permissionClassificationType
    - `[PermissionId <String>]`: Pengidentifikasi unik (id) untuk izin yang didelegasikan yang tercantum dalam kumpulanPermissionScopes yang diterbitkan dari layananPrincipal. Diperlukan untuk membuat. Tidak mendukung $filter.
    - `[PermissionName <String>]`: Nilai klaim (nilai) untuk izin yang didelegasikan yang tercantum dalam kumpulan ServicePrincipal yang diterbitkanPermissionScopes. Tidak mendukung $filter.
  - `[Description <String>]`: Bidang teks gratis untuk memberikan deskripsi internal yang dihadapi pengguna akhir tentang prinsipal layanan. Portal pengguna akhir seperti MyApps akan menampilkan deskripsi aplikasi di bidang ini. Ukuran maksimum yang diperbolehkan adalah 1024 karakter. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi yang terdaftar. Nilai yang memungkinkan adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasannya mungkin termasuk aktivitas mencurigakan, kasar, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[Endpoint <IMicrosoftGraphEndpoint[]>]`: Titik akhir tersedia untuk penemuan. Layanan seperti Sharepoint mengisi properti ini dengan SharePoint titik akhir khusus penyewa yang dapat ditemukan dan digunakan oleh aplikasi lain dalam pengalaman mereka.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: HomeRealmDiscoveryPolicies yang ditetapkan ke prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Homepage <String>]`: Laman atau halaman awal aplikasi.
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Tautan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Tautan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Tautan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Tautan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Pengumpulan kredensial kunci yang terkait dengan prinsipal layanan. Tidak bisa ditipu. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah dikenali untuk kunci. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kredensial. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus berupa nilai dasar 64 yang dikodekan.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) untuk kunci tersebut.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu di mana kredensial menjadi valid. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Jenis kredensial kunci; misalnya, 'Simetris'.
    - `[Usage <String>]`: String yang menjelaskan tujuan penggunaan kunci; misalnya, 'Verifikasi'.
  - `[LoginUrl <String>]`: Menentukan URL tempat penyedia layanan mengalihkan pengguna ke Azure AD untuk mengautentikasi. Azure AD menggunakan URL untuk meluncurkan aplikasi dari Microsoft 365 atau Azure AD Aplikasi Saya. Ketika kosong, Azure AD melakukan masuk yang dimulai idP untuk aplikasi yang dikonfigurasi dengan masuk tunggal berbasis SAML. Pengguna meluncurkan aplikasi dari Microsoft 365, Azure AD Aplikasi Saya, atau URL SSO Azure AD.
  - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk membuat logout pengguna menggunakan OpenId Koneksi protokol logout saluran depan, saluran belakang, atau SAML.
  - `[Note <String>]`: Bidang teks gratis untuk mengambil informasi tentang prinsipal layanan, biasanya digunakan untuk tujuan operasional. Ukuran maksimum yang diperbolehkan adalah 1024 karakter.
  - `[NotificationEmailAddress <String[]>]`: Menentukan daftar alamat email tempat Azure AD mengirim pemberitahuan saat sertifikat aktif mendekati tanggal kedaluwarsa. Ini hanya untuk sertifikat yang digunakan untuk menandatangani token SAML yang dikeluarkan untuk aplikasi Galeri Azure AD.
  - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Izin yang didelegasikan diekspos oleh aplikasi. Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi. Tidak bisa ditipu.
    - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibacakan oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin berskala penyewa.
    - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
    - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik di dalam kumpulan izin yang didelegasikan yang ditentukan untuk aplikasi sumber daya.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, izin mungkin dihapus.
    - `[Origin <String>]`: 
    - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diwajibkan untuk persetujuan atas izin tersebut. Ini akan menjadi perilaku default, tetapi setiap pelanggan bisa memilih untuk mengkustomisasi perilaku di organisasi mereka (dengan memperbolehkan, membatasi atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
    - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
    - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
    - `[Value <String>]`: Menentukan nilai untuk disertakan dalam klaim scp (lingkup) dalam token akses. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Pengumpulan kredensial kata sandi yang terkait dengan prinsipal layanan. Tidak bisa ditipu.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah dikenali untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kata sandi yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu kata sandi menjadi valid. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[PreferredSingleSignOnMode <String>]`: Menentukan mode masuk tunggal yang dikonfigurasi untuk aplikasi ini. Azure AD menggunakan mode masuk tunggal pilihan untuk meluncurkan aplikasi dari Microsoft 365 atau Azure AD Aplikasi Saya. Nilai yang didukung adalah kata sandi, saml, notSupported, dan oidc.
  - `[PreferredTokenSigningKeyThumbprint <String>]`: Khusus untuk penggunaan internal. Jangan menulis atau mengandalkan properti ini. Mungkin dihapus dalam versi yang akan datang.
  - `[ReplyUrl <String[]>]`: URL tempat token pengguna dikirim untuk masuk dengan aplikasi terkait, atau URL pengalihan yang dikirimkan kode otorisasi OAuth 2.0 dan token akses untuk aplikasi terkait. Tidak bisa ditipu.
  - `[SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>]`: samlSingleSignOnSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RelayState <String>]`: URI relatif yang akan dialihkan penyedia layanan setelah penyelesaian alur masuk tunggal.
  - `[ServicePrincipalName <String[]>]`: Berisi daftar pengidentifikasiUris, yang disalin dari aplikasi terkait. Nilai tambahan dapat ditambahkan ke aplikasi hibrid. Nilai ini dapat digunakan untuk mengidentifikasi izin yang diekspos oleh aplikasi ini dalam Azure AD. Misalnya, Aplikasi klien dapat menentukan URI sumber daya yang didasarkan pada nilai properti ini untuk memperoleh token akses, yang merupakan URI yang dikembalikan dalam klaim 'aud'. Operator apa pun diperlukan untuk memfilter ekspresi pada properti multinilai. Tidak bisa ditipu.  Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[ServicePrincipalType <String>]`: Mengidentifikasi apakah prinsipal layanan mewakili aplikasi atau identitas terkelola. Ini diatur oleh Azure AD secara internal. Untuk prinsipal layanan yang mewakili aplikasi, ini diatur sebagai Aplikasi. Untuk prinsipal layanan yang mewakili identitas terkelola, ini diatur sebagai ManagedIdentity.
  - `[Tag <String[]>]`: String kustom yang dapat digunakan untuk mengkategorikan dan mengidentifikasi prinsipal layanan. Tidak bisa ditipu. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId kunci publik dari kumpulan keyCredentials. Ketika dikonfigurasi, Azure AD masalah token untuk aplikasi ini yang dienkripsi menggunakan kunci yang ditentukan oleh properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci privat yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: TokenIssuancePolicies yang ditetapkan untuk prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies yang ditetapkan ke prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Bisa ada banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>]`: 

## RELATED LINKS

## RELATED LINKS
