---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azadgroupmember
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADGroupMember.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzADGroupMember.md
ms.openlocfilehash: 03ac7db4e9f602e52cdfc1b62c20e0d0b936b760
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144639780"
---
# Get-AzADGroupMember

## SYNOPSIS
Mencantumkan anggota dari grup.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azadgroupmember) untuk informasi terbaru.

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

> [!IMPORTANT]
> Karena keterbatasan dengan API Graph saat ini, perwakilan layanan tidak dikembalikan oleh Get-AzAdGroupMember di Az 7.x. Untuk solusi sementara, lihat [Memecahkan masalah modul Azure Az PowerShell](/powershell/azure/troubleshooting#get-azadgroupmember-doesnt-return-service-principals).

## EXAMPLES

### Contoh 1: Mencantumkan anggota menurut nama tampilan grup
```powershell
Get-AzADGroupMember -GroupDisplayName $name
```

Mencantumkan anggota menurut nama tampilan grup

### Contoh 2: Mencantumkan anggota menurut input alur
```powershell
Get-AzADGroup -DisplayName $name | Get-AzADGroupMember
```

Mencantumkan anggota menurut input alur

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
Objek grup target, dapat digunakan sebagai input alur.
Untuk membuat, lihat bagian CATATAN untuk properti GROUPOBJECT dan buat tabel hash.

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
Mengurutkan item menurut nilai properti

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

### -Cari
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
Mengabaikan objek 'n' pertama lalu mendapatkan objek yang tersisa.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


GROUPOBJECT <IMicrosoftGraphGroup>: Objek grup target, dapat digunakan sebagai input alur.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AppRoleAssignment <IMicrosoftGraphAppRoleAssignmentAutoGenerated[]>]`: Mewakili peran aplikasi yang telah diberikan grup untuk aplikasi. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan ke prinsipal. Peran aplikasi ini harus diekspos di properti appRoles pada perwakilan layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default 00000000-0000-0000-0000-000000000000 dapat ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan ke aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan untuk membuat.
    - `[CreatedDateTime <DateTime?>]`: Waktu saat penetapan peran aplikasi dibuat. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja.
    - `[PrincipalDisplayName <String>]`: Nama tampilan pengguna, grup, atau perwakilan layanan yang diberikan penetapan peran aplikasi. Baca-saja. Mendukung $filter (eq dan startswith).
    - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup, atau perwakilan layanan yang diberikan peran aplikasi. Diperlukan untuk membuat.
    - `[PrincipalType <String>]`: Jenis prinsipal yang ditetapkan. Ini bisa berupa Pengguna, Grup, atau ServicePrincipal. Baca-saja.
    - `[ResourceDisplayName <String>]`: Nama tampilan perwakilan layanan aplikasi sumber daya tempat penugasan dibuat.
    - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk perwakilan layanan sumber daya tempat penugasan dibuat. Diperlukan untuk membuat. Mendukung $filter (eq saja).
  - `[Classification <String>]`: Menjelaskan klasifikasi untuk grup (seperti dampak bisnis rendah, menengah, atau tinggi). Nilai yang valid untuk properti ini ditentukan dengan membuat nilai pengaturan ClassificationList, berdasarkan definisi templat. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith).
  - `[CreatedOnBehalfOf <IMicrosoftGraphDirectoryObject>]`: Mewakili objek Azure Active Directory. Jenis directoryObject adalah jenis dasar untuk banyak jenis entitas direktori lainnya.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional untuk grup. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[GroupType <String[]>]`: Menentukan jenis grup dan keanggotaannya.  Jika koleksi berisi Terpadu, grup adalah grup Microsoft 365; jika tidak, itu adalah grup keamanan atau grup distribusi. Untuk detailnya, lihat gambaran umum grup. Jika koleksi menyertakan DynamicMembership, grup memiliki keanggotaan dinamis; jika tidak, keanggotaan bersifat statis.  Dikembalikan secara default. Mendukung $filter (eq, NOT).
  - `[HasMembersWithLicenseError <Boolean?>]`: Menunjukkan apakah ada anggota dalam grup ini yang memiliki kesalahan lisensi dari penetapan lisensi berbasis grupnya. Properti ini tidak pernah dikembalikan pada operasi GET. Anda dapat menggunakannya sebagai argumen $filter untuk mendapatkan grup yang memiliki anggota dengan kesalahan lisensi (yaitu, filter untuk properti ini menjadi benar).  Mendukung $filter (eq).
  - `[IsArchived <Boolean?>]`: 
  - `[IsAssignableToRole <Boolean?>]`: Menunjukkan apakah grup ini dapat ditetapkan ke peran Azure Active Directory. Properti ini hanya dapat diatur saat membuat grup dan tidak dapat diubah. Jika diatur ke true, properti securityEnabled juga harus diatur ke true dan grup tidak dapat menjadi grup dinamis (yaitu, groupTypes tidak boleh berisi DynamicMembership). Hanya penelepon dalam peran administrator peran Administrator Global dan Istimewa yang dapat mengatur properti ini. Pemanggil juga harus diberi izin Directory.AccessAsUser.All untuk mengatur properti ini. Untuk informasi selengkapnya, lihat Menggunakan grup untuk mengelola Azure AD penetapan peranReturned secara default. Mendukung $filter (eq, ne, NOT).
  - `[MailEnabled <Boolean?>]`: Menentukan apakah grup diaktifkan melalui email. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT).
  - `[MailNickname <String>]`: Alias email untuk grup, unik dalam organisasi. Properti ini harus ditentukan ketika grup dibuat. Karakter ini tidak dapat digunakan dalam mailNickName: @()/[]';:.<>,SPACE. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[MembershipRule <String>]`: Aturan yang menentukan anggota untuk grup ini jika grup adalah grup dinamis (groupTypes berisi DynamicMembership). Untuk informasi selengkapnya tentang sintaks aturan keanggotaan, lihat Sintaks Aturan Keanggotaan. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith).
  - `[MembershipRuleProcessingState <String>]`: Menunjukkan apakah pemrosesan keanggotaan dinamis aktif atau dijeda. Nilai yang mungkin adalah Aktif atau Dijeda. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, in).
  - `[PermissionGrant <IMicrosoftGraphResourceSpecificPermissionGrant[]>]`: Izin yang telah diberikan untuk grup ke aplikasi tertentu. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[ClientAppId <String>]`: ID perwakilan layanan aplikasi Azure AD yang telah diberikan akses. Baca-saja.
    - `[ClientId <String>]`: ID aplikasi Azure AD yang telah diberikan akses. Baca-saja.
    - `[Permission <String>]`: Nama izin khusus sumber daya. Baca-saja.
    - `[PermissionType <String>]`: Jenis izin. Nilai yang mungkin adalah: Aplikasi, Didelegasikan. Baca-saja.
    - `[ResourceAppId <String>]`: ID aplikasi Azure AD yang menghosting sumber daya. Baca-saja.
  - `[PreferredDataLocation <String>]`: Lokasi data pilihan untuk grup. Untuk informasi selengkapnya, lihat OneDrive Multi-Geo Online. Dikembalikan secara default.
  - `[PreferredLanguage <String>]`: Bahasa pilihan untuk grup Microsoft 365. Harus mengikuti Kode ISO 639-1; misalnya 'en-US'. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[SecurityEnabled <Boolean?>]`: Menentukan apakah grup tersebut adalah grup keamanan. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, in).
  - `[SecurityIdentifier <String>]`: Pengidentifikasi keamanan grup, digunakan dalam skenario Windows. Dikembalikan secara default.
  - `[Theme <String>]`: Menentukan tema warna grup Microsoft 365. Nilai yang mungkin adalah Teal, Ungu, Hijau, Biru, Merah Muda, Oranye atau Merah. Dikembalikan secara default.
  - `[Visibility <String>]`: Menentukan kebijakan gabungan grup dan visibilitas konten grup untuk grup. Nilai yang mungkin adalah: Privat, Publik, atau Hiddenmembership. Hiddenmembership hanya dapat diatur untuk grup Microsoft 365, saat grup dibuat. Ini tidak dapat diperbarui nanti. Nilai visibilitas lainnya dapat diperbarui setelah pembuatan grup. Jika nilai visibilitas tidak ditentukan selama pembuatan grup di Microsoft Graph, grup keamanan dibuat sebagai Privat secara default dan grup Microsoft 365 adalah Publik. Lihat opsi visibilitas grup untuk mempelajari selengkapnya. Dikembalikan secara default.

## RELATED LINKS
