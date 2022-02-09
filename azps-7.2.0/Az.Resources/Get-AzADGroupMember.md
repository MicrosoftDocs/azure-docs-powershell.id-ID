---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azadgroupmember
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADGroupMember.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADGroupMember.md
ms.openlocfilehash: ed573dc5c6ddaeabc66be91dae13220cf38398f1
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138287468"
---
# Get-AzADGroupMember

## SYNOPSIS
Mencantumkan anggota dari grup.

## SYNTAX

### ObjectIdParameterSet (Default)
```
Get-AzADGroupMember -GroupObjectId <String> [-Expand <String[]>] [-Filter <String>] [-Orderby <String[]>]
 [-Search <String>] [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzADGroupMember [-Expand <String[]>] [-Filter <String>] [-Orderby <String[]>] [-Search <String>]
 [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] -GroupDisplayName <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GroupObjectParameterSet
```
Get-AzADGroupMember [-Expand <String[]>] [-Filter <String>] [-Orderby <String[]>] [-Search <String>]
 [-Select <String[]>] [-First <UInt64>] [-Skip <UInt64>] -GroupObject <IMicrosoftGraphGroup>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan anggota dari grup.

## EXAMPLES

### Contoh 1:  List members by group display name
```powershell
PS C:\> Get-AzADGroupMember -GroupDisplayName $name
```

List members by group display name

### Contoh 2:  List members by pipeline input
```powershell
PS C:\> Get-AzADGroup -DisplayName $name | Get-AzADGroupMember
```

Anggota daftar menurut input saluran

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

### -Perluas
Memperluas entitas terkait

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

### -Filter
Memfilter item menurut nilai properti

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

### -GroupDisplayName
Nama tampilan grup target.

```yaml
Type: System.String
Parameter Sets: DisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupObject
Objek grup target, dapat digunakan sebagai input saluran.
Untuk membuat, lihat bagian CATATAN untuk properti GROUPOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup
Parameter Sets: GroupObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GroupObjectId
Id objek grup target.

```yaml
Type: System.String
Parameter Sets: ObjectIdParameterSet
Aliases: Id, ObjectId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Orderby
Item pesanan menurut nilai properti

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

### -Pencarian
Mencari item menurut frasa pencarian

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

### -Pilih
Pilih properti yang akan dikembalikan

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

### -Lewati
Mengabaikan objek 'n' pertama, lalu mendapatkan objek yang tersisa.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First
Hanya mendapatkan objek 'n' pertama.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


GROUPOBJECT <IMicrosoftGraphGroup>: Objek grup target, dapat digunakan sebagai input saluran.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AppRoleAssignment <IMicrosoftGraphAppRoleAssignmentAutoGenerated[]>]`: Menunjukkan peran aplikasi yang telah diberikan grup untuk sebuah aplikasi. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
    - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan sebagai pokok aplikasi. Peran aplikasi ini harus diekspos dalam properti appRoles pada prinsipal layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default dari 00000000-0000-0000-000000000000 bisa ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan untuk aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan pada saat membuat.
    - `[CreatedDateTime <DateTime?>]`: Waktu ketika penetapan peran aplikasi dibuat. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja.
    - `[PrincipalDisplayName <String>]`: Nama tampilan pengguna, grup, atau prinsipal layanan yang diberikan tugas peran aplikasi. Baca-saja. Mendukung $filter (eq dan startswith).
    - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup atau prinsipal layanan yang diberikan peran aplikasi. Diperlukan pada saat membuat.
    - `[PrincipalType <String>]`: Tipe pokok yang ditetapkan. Bisa berupa User, Group atau ServicePrincipal. Baca-saja.
    - `[ResourceDisplayName <String>]`: Nama tampilan prinsipal layanan aplikasi sumber daya tempat penetapan dilakukan.
    - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk prinsipal layanan sumber daya tempat penetapan dilakukan. Diperlukan pada saat membuat. Mendukung $filter (eq saja).
  - `[Classification <String>]`: Menjelaskan klasifikasi untuk grup (seperti dampak bisnis rendah, sedang, atau tinggi). Nilai yang valid untuk properti ini ditetapkan dengan membuat nilai pengaturan ClassificationList, berdasarkan definisi templat. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith).
  - `[CreatedOnBehalfOf <IMicrosoftGraphDirectoryObject>]`: Mewakili Azure Active Directory objek. Tipe directoryObject adalah tipe dasar untuk banyak tipe entitas direktori lainnya.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional untuk grup. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[GroupType <String[]>]`: Menentukan tipe grup dan keanggotaannya.  Jika kumpulan berisi Terpadu, grup merupakan Microsoft 365 grup; jika tidak, itu adalah grup keamanan atau grup distribusi. Untuk detailnya, lihat gambaran umum grup. Jika koleksi menyertakan DynamicMembership, grup memiliki keanggotaan dinamis; jika tidak, keanggotaan statis.  Dikembalikan secara default. Mendukung $filter (eq, NOT).
  - `[HasMembersWithLicenseError <Boolean?>]`: Menunjukkan apakah ada anggota dalam grup ini yang memiliki kesalahan lisensi dari penetapan lisensi berbasis grup tersebut. Properti ini tidak akan pernah dikembalikan pada operasi GET. Anda bisa menggunakannya sebagai argumen $filter untuk mendapatkan grup yang memiliki anggota dengan kesalahan lisensi (jadi, filter untuk properti ini benar).  Mendukung $filter (eq).
  - `[IsArchived <Boolean?>]`: 
  - `[IsAssignableToRole <Boolean?>]`: Menunjukkan apakah grup ini dapat ditetapkan untuk Azure Active Directory peran baru. Properti ini hanya dapat diatur saat membuat grup dan dapat terus dilakukan. Jika diatur ke true, properti securityEnabled juga harus diatur ke true dan grup tidak dapat menjadi grup dinamis (groupTypes tidak dapat memuat DynamicMembership). Hanya penelepon dalam peran Administrator global dan Administrator peran istimewa yang dapat mengatur properti ini. Penelepon juga harus diberi izin Directory.AccessAsUser.All untuk mengatur properti ini. Untuk selengkapnya, lihat Menggunakan grup untuk mengelola penetapan peran Azure ADReturned secara default. Mendukung $filter (eq, ne, NOT).
  - `[MailEnabled <Boolean?>]`: Menentukan apakah grup diaktifkan email. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT).
  - `[MailNickname <String>]`: Alias email untuk grup, unik dalam organisasi. Properti ini harus ditentukan saat grup dibuat. Karakter ini tidak dapat digunakan dalam mailNickName: @()/[]';:.<>,SPACE. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[MembershipRule <String>]`: Aturan yang menentukan anggota untuk grup ini jika grup adalah grup dinamis (groupTypes berisi DynamicMembership). Untuk informasi selengkapnya tentang sintaks aturan keanggotaan, lihat sintaks Aturan Keanggotaan. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith).
  - `[MembershipRuleProcessingState <String>]`: Menunjukkan apakah pemrosesan keanggotaan dinamis aktif atau jeda. Kemungkinan nilai Di tempat atau Dijeda. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, in).
  - `[PermissionGrant <IMicrosoftGraphResourceSpecificPermissionGrant[]>]`: Izin yang telah diberikan untuk grup ke aplikasi tertentu. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
    - `[ClientAppId <String>]`: ID prinsipal layanan aplikasi Azure AD yang telah diberi akses. Baca-saja.
    - `[ClientId <String>]`: ID aplikasi Azure AD yang telah diberikan akses. Baca-saja.
    - `[Permission <String>]`: Nama izin khusus sumber daya. Baca-saja.
    - `[PermissionType <String>]`: Tipe izin. Nilai yang mungkin adalah: Aplikasi, Didelegasikan. Baca-saja.
    - `[ResourceAppId <String>]`: ID aplikasi Azure AD yang menjadi hosting sumber daya. Baca-saja.
  - `[PreferredDataLocation <String>]`: Lokasi data pilihan untuk grup. Untuk informasi selengkapnya, lihat OneDrive Online Multi-Geo. Dikembalikan secara default.
  - `[PreferredLanguage <String>]`: Bahasa pilihan untuk Microsoft 365 grup. Harus mengikuti Kode ISO 639-1; misalnya 'en-US'. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[SecurityEnabled <Boolean?>]`: Menentukan apakah grup adalah grup keamanan. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, in).
  - `[SecurityIdentifier <String>]`: Pengidentifikasi keamanan grup, digunakan dalam Windows kata kunci. Dikembalikan secara default.
  - `[Theme <String>]`: Menentukan Microsoft 365 warna grup. Nilai yang mungkin adalah Teal, Ungu, Hijau, Biru, Merah Muda, Oranye atau Merah. Dikembalikan secara default.
  - `[Visibility <String>]`: Menentukan kebijakan bergabung dalam grup dan visibilitas konten grup untuk grup. Nilai yang mungkin adalah: Pribadi, Publik, atau Tersembunyi. Fitur tersembunyi hanya dapat diatur untuk anggota Microsoft 365 baru, ketika grup tersebut dibuat. Pembaruan tidak dapat diperbarui nanti. Nilai visibilitas lainnya dapat diperbarui setelah pembuatan grup. Jika nilai visibilitas tidak ditentukan selama pembuatan grup di Microsoft Graph, grup keamanan dibuat sebagai Pribadi secara default dan grup Microsoft 365 diatur menjadi Publik. Lihat opsi visibilitas grup untuk mempelajari selengkapnya. Dikembalikan secara default.

## RELATED LINKS
