---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azadspcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADSpCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADSpCredential.md
ms.openlocfilehash: 775f4079a5edc6388cba9f380a1d5549f1bd23ac
ms.sourcegitcommit: b346b2fbd8b25f54759984e75ddbee3304921c43
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2022
ms.locfileid: "140664687"
---
# Remove-AzADSpCredential

## SYNOPSIS
Menghapus kredensial kunci atau kredensial kata sandi untuk prinsipal layanan.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

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

### Contoh 1: Remove service principal credentials by key id
```powershell
PS C:\> Remove-AzADSpCredential -DisplayName $name -KeyId $keyid
```

Remove service principal credentials by key id

### Contoh 2: Hapus semua kredensial dari prinsipal layanan
```powershell
PS C:\> Get-AzADServicePrincipal -DisplayName $name | Remove-AzADSpCredential
```

Hapus semua kredensial dari prinsipal layanan

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
Id objek prinsipal layanan.

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

### -ServicePrincipalName
Nama prinsipal layanan.

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
Objek prinsipal layanan, dapat digunakan sebagai input saluran.
Untuk membuat, lihat bagian CATATAN untuk properti SERVICEPRINCIPALOBJECT dan buat tabel hash.

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
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AccountEnabled <Boolean?>]`: true jika akun prinsipal layanan diaktifkan; jika tidak, false. Mendukung $filter (eq, ne, NOT, in).
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan oleh layanan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan Microsoft 365 anda panggil aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[AlternativeName <String[]>]`: Digunakan untuk mengambil prinsipal layanan menurut langganan, mengidentifikasi grup sumber daya dan id sumber daya lengkap untuk identitas yang dikelola. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[AppDescription <String>]`: Deskripsi yang diekspos oleh aplikasi terkait.
  - `[AppDisplayName <String>]`: Nama tampilan yang diekspos oleh aplikasi terkait.
  - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi terkait (properti appId-nya).
  - `[AppOwnerOrganizationId <String>]`: Berisi id penyewa tempat aplikasi didaftarkan. Hal ini hanya berlaku pada prinsipal layanan yang didukung oleh aplikasi. Mendukung $filter (eq, ne, NOT, ge, le).
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Peran yang diekspos oleh aplikasi yang diwakili prinsipal layanan ini. Untuk informasi selengkapnya, lihat definisi properti appRoles di entitas aplikasi. Not nullable.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lainnya (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lainnya juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditetapkan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran dan persetujuan aplikasi.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam kumpulan peran aplikasi. Ketika membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus sebuah peran, ini harus terlebih dahulu disetel ke false.  Pada tahap ini, dalam panggilan berikutnya, peran ini mungkin dihapus.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran di token ID dan token akses yang mengotentikan pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]`: Penugasan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan prinsipal layanan lainnya. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
    - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan sebagai pokok aplikasi. Peran aplikasi ini harus diekspos dalam properti appRoles pada prinsipal layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default dari 00000000-0000-0000-000000000000 bisa ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan untuk aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan pada saat membuat.
    - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup atau prinsipal layanan yang diberikan peran aplikasi. Diperlukan pada saat membuat.
    - `[ResourceDisplayName <String>]`: Nama tampilan prinsipal layanan aplikasi sumber daya tempat penetapan dilakukan.
    - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk prinsipal layanan sumber daya tempat penetapan dilakukan. Diperlukan pada saat membuat. Mendukung $filter (eq saja).
  - `[AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>]`: Penetapan peran aplikasi untuk aplikasi atau layanan lain, yang diberikan kepada prinsipal layanan ini. Mendukung $expand.
  - `[AppRoleAssignmentRequired <Boolean?>]`: Menentukan apakah pengguna atau prinsipal layanan lain perlu diberi penugasan peran aplikasi untuk prinsipal layanan ini sebelum pengguna bisa masuk atau aplikasi bisa mendapatkan token. Nilai default adalah false. Not nullable. Mendukung $filter (eq, ne, NOT).
  - `[ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]`: ClaimsMappingPolicies yang ditetapkan untuk prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]`: Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili oleh prinsipal layanan ini. Mendukung $expand.
    - `[Classification <String>]`: permissionClassificationType
    - `[PermissionId <String>]`: Pengidentifikasi unik (id) untuk izin yang didelegasikan tercantum dalam kumpulan servicePrincipal yang diterbitkanPermissionScopes. Diperlukan pada saat membuat. Tidak mendukung $filter.
    - `[PermissionName <String>]`: Nilai klaim (nilai) untuk izin yang didelegasikan tercantum dalam kumpulan servicePrincipal yang diterbitkanPermissionScopes. Tidak mendukung $filter.
  - `[Description <String>]`: Bidang teks gratis untuk memberikan deskripsi prinsipal layanan yang dihadapi pengguna akhir internal. Portal pengguna akhir seperti AplikasiSaya akan menampilkan deskripsi aplikasi dalam bidang ini. Ukuran maksimal yang diperbolehkan adalah 1024 karakter. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi yang terdaftar. Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasan dapat mencantumkan aktivitas yang mencurigakan, melecehkan, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[Endpoint <IMicrosoftGraphEndpoint[]>]`: Titik akhir yang tersedia untuk penemuan. Layanan seperti Sharepoint akan mengisi properti ini dengan titik akhir SharePoint penyewa yang dapat ditemukan dan digunakan aplikasi lain dalam pengalaman mereka.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: HomeRealmDiscoveryPolicies yang ditetapkan pada prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Homepage <String>]`: Laman atau halaman awal aplikasi.
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Menautkan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Menautkan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Menautkan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Menautkan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Kumpulan kredensial kunci yang terkait dengan prinsipal layanan. Not nullable. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kunci tersebut. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kredensial kedaluwarsa. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus merupakan nilai berkodekan 64 basis.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) kunci tersebut.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu saat kredensial menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Tipe kredensial kunci; misalnya, 'Simetri'.
    - `[Usage <String>]`: String yang menjelaskan tujuan untuk menggunakan kunci; misalnya, 'Verifikasi'.
  - `[LoginUrl <String>]`: Menentukan URL tempat penyedia layanan mengalihkan pengguna ke Azure AD untuk mengautentikasi. Azure AD menggunakan URL untuk meluncurkan aplikasi dari Microsoft 365 atau Aplikasi Azure AD Saya. Ketika kosong, Azure AD melakukan masuk yang dimulai IdP untuk aplikasi yang dikonfigurasi dengan akses masuk tunggal berbasis SAML. Pengguna meluncurkan aplikasi tersebut dari Microsoft 365, URL Aplikasi Saya Azure AD, atau URL SSO Azure AD.
  - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk membuat logo pengguna menggunakan protokol OpenId Koneksi saluran depan, saluran belakang, atau logout SAML.
  - `[Note <String>]`: Bidang teks gratis untuk merekam informasi tentang prinsipal layanan, biasanya digunakan untuk tujuan operasional. Ukuran maksimal yang diperbolehkan adalah 1024 karakter.
  - `[NotificationEmailAddress <String[]>]`: Menentukan daftar alamat email di mana Azure AD mengirimkan pemberitahuan ketika sertifikat aktif mendekati tanggal kedaluwarsa. Ini hanya untuk sertifikat yang digunakan untuk menandatangani token SAML yang dikeluarkan untuk aplikasi Galeri Azure AD.
  - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Izin yang didelegasikan diekspos oleh aplikasi. Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi. Not nullable.
    - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin tingkat penyewa.
    - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
    - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik dalam kumpulan izin yang didelegasikan yang ditetapkan untuk aplikasi sumber daya.
    - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus diatur ke salah terlebih dahulu.  Pada tahap ini, dalam panggilan berikutnya, izin mungkin dihapus.
    - `[Origin <String>]`: 
    - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diperlukan untuk menyetujui izin. Ini akan menjadi perilaku default, tapi setiap pelanggan bisa memilih untuk mengkustomisasi perilaku di organisasi mereka (dengan mengizinkan, membatasi atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
    - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberi izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
    - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (lingkup) di token akses. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Kumpulan kredensial kata sandi yang terkait dengan prinsipal layanan. Not nullable.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kata sandi kedaluwarsa yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu valid ketika kata sandi menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[PreferredSingleSignOnMode <String>]`: Menentukan mode masuk tunggal yang dikonfigurasi untuk aplikasi ini. Azure AD menggunakan mode masuk tunggal pilihan untuk meluncurkan aplikasi dari Microsoft 365 atau Aplikasi Saya Azure AD. Nilai yang didukung adalah kata sandi, saml, tidak Didukung, danoidc.
  - `[PreferredTokenSigningKeyThumbprint <String>]`: Khusus untuk penggunaan internal. Jangan menulis atau mengandalkan properti ini. Mungkin akan dihapus dalam versi yang akan datang.
  - `[ReplyUrl <String[]>]`: URL yang dikirimkan token pengguna untuk masuk dengan aplikasi terkait, atau URI pengalihan yang kode otorisasi dan token akses OAuth 2.0 dikirim ke aplikasi terkait. Not nullable.
  - `[SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>]`: samlSingleSignOnSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RelayState <String>]`: URI relatif dari penyedia layanan akan dialihkan setelah penyelesaian aliran masuk tunggal.
  - `[ServicePrincipalName <String[]>]`: Berisi daftar pengidentifikasiUris, disalin dari aplikasi terkait. Nilai tambahan dapat ditambahkan ke aplikasi hibrid. Nilai ini dapat digunakan untuk mengidentifikasi izin yang diekspos oleh aplikasi ini dalam Azure AD. Misalnya, aplikasi Klien dapat menentukan URI sumber daya yang didasarkan pada nilai properti ini untuk memperoleh token akses, yang merupakan URI yang dikembalikan dalam klaim 'aud'. Operator ini diperlukan untuk memfilter ekspresi pada properti multinilai. Not nullable.  Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[ServicePrincipalType <String>]`: Mengidentifikasi jika prinsipal layanan mewakili aplikasi atau identitas terkelola. Hal ini diatur oleh Azure AD secara internal. Untuk prinsipal layanan yang mewakili aplikasi, ini diatur sebagai Aplikasi. Untuk prinsipal layanan yang mewakili identitas terkelola ini diatur sebagai Identitas Terkelola.
  - `[Tag <String[]>]`: String kustom yang dapat digunakan untuk mengkategorikan dan mengidentifikasi prinsipal layanan. Not nullable. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId dari kunci publik dari koleksi keyCredentials. Saat dikonfigurasi, Azure AD memberikan token untuk aplikasi ini yang dienkripsi menggunakan kunci yang ditentukan oleh properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci pribadi yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: TokenIssuancePolicies yang ditetapkan pada prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies yang ditetapkan pada prinsipal layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>]`: 

## RELATED LINKS

## RELATED LINKS
