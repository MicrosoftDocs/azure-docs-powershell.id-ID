---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/add-azadgroupmember
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADGroupMember.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADGroupMember.md
ms.openlocfilehash: 8e9cf8c9f1aa14f7e257b1cf63345f085ddeb9bf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142342097"
---
# Add-AzADGroupMember

## SYNOPSIS
Menambahkan anggota ke grup.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/add-azadgroupmember) untuk informasi terbaru.

## SYNTAX

### MemberObjectIdWithGroupObjectIdParameterSet (Default)
```
Add-AzADGroupMember -TargetGroupObjectId <String> -MemberObjectId <String[]> [-DefaultProfile <PSObject>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MemberUPNWithGroupObjectIdParameterSet
```
Add-AzADGroupMember -TargetGroupObjectId <String> -MemberUserPrincipalName <String[]>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MemberObjectIdWithGroupObjectParameterSet
```
Add-AzADGroupMember -MemberObjectId <String[]> -TargetGroupObject <MicrosoftGraphGroup>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MemberObjectIdWithGroupDisplayNameParameterSet
```
Add-AzADGroupMember -MemberObjectId <String[]> -TargetGroupDisplayName <String> [-DefaultProfile <PSObject>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MemberUPNWithGroupObjectParameterSet
```
Add-AzADGroupMember -MemberUserPrincipalName <String[]> -TargetGroupObject <MicrosoftGraphGroup>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MemberUPNWithGroupDisplayNameParameterSet
```
Add-AzADGroupMember -MemberUserPrincipalName <String[]> -TargetGroupDisplayName <String>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menambahkan anggota ke grup.

## EXAMPLES

### Contoh 1: Menambahkan anggota ke grup
```powershell
PS C:\> $groupid=(Get-AzADGroup -DisplayName $gname).Id
PS C:\> $members=@()
PS C:\> $members+=(Get-AzADUser -DisplayName $uname).Id
PS C:\> $members+=(Get-AzADServicePrincipal -ApplicationId $appid).Id
PS C:\> Add-AzADGroupMember -TargetGroupObjectId $groupid MemberObjectId $members
```

Menambahkan anggota ke grup

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

### -MemberObjectId
Id objek anggota untuk ditambahkan ke grup target.

```yaml
Type: System.String[]
Parameter Sets: MemberObjectIdWithGroupObjectIdParameterSet, MemberObjectIdWithGroupObjectParameterSet, MemberObjectIdWithGroupDisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberUserPrincipalName
Nama utama pengguna anggota untuk ditambahkan ke grup target.

```yaml
Type: System.String[]
Parameter Sets: MemberUPNWithGroupObjectIdParameterSet, MemberUPNWithGroupObjectParameterSet, MemberUPNWithGroupDisplayNameParameterSet
Aliases:

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

### -TargetGroupDisplayName
Nama tampilan grup target.

```yaml
Type: System.String
Parameter Sets: MemberObjectIdWithGroupDisplayNameParameterSet, MemberUPNWithGroupDisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetGroupObject
Objek grup target, dapat digunakan sebagai input saluran.
Untuk membangun, lihat bagian CATATAN untuk properti TARGETGROUPOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.MicrosoftGraphGroup
Parameter Sets: MemberObjectIdWithGroupObjectParameterSet, MemberUPNWithGroupObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetGroupObjectId
Id objek grup target.

```yaml
Type: System.String
Parameter Sets: MemberObjectIdWithGroupObjectIdParameterSet, MemberUPNWithGroupObjectIdParameterSet
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.MicrosoftGraphGroup

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TARGETGROUPOBJECT <MicrosoftGraphGroup>: Objek grup target, dapat digunakan sebagai input pipeline.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AppRoleAssignment <IMicrosoftGraphAppRoleAssignmentAutoGenerated[]>]`: Mewakili peran aplikasi sebuah grup telah diberikan untuk sebuah aplikasi. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan ke prinsipal. Peran aplikasi ini harus diekspos dalam properti appRoles pada prinsipal layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default 00000000-0000-0000-00000000000000 dapat ditentukan untuk mengisyaratkan bahwa prinsipal ditetapkan ke aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan untuk membuat.
    - `[CreatedDateTime <DateTime?>]`: Waktu ketika penetapan peran aplikasi dibuat. Tipe Cap waktu menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja.
    - `[PrincipalDisplayName <String>]`: Nama tampilan pengguna, grup, atau prinsipal layanan yang diberi penetapan peran aplikasi. Baca-saja. Mendukung $filter (eq dan startswith).
    - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup, atau prinsipal layanan yang diberi peran aplikasi. Diperlukan untuk membuat.
    - `[PrincipalType <String>]`: Tipe pokok yang ditetapkan. Ini bisa berupa Pengguna, Grup, atau ServicePrincipal. Baca-saja.
    - `[ResourceDisplayName <String>]`: Nama tampilan dari prinsipal layanan aplikasi sumber daya tempat tugas dibuat.
    - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk prinsipal layanan sumber daya tempat penugasan dibuat. Diperlukan untuk membuat. Mendukung $filter (eq saja).
  - `[Classification <String>]`: Menjelaskan klasifikasi untuk grup (seperti dampak bisnis rendah, menengah, atau tinggi). Nilai yang valid untuk properti ini ditentukan dengan membuat nilai pengaturan ClassificationList, berdasarkan definisi templat. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith).
  - `[CreatedOnBehalfOf <IMicrosoftGraphDirectoryObject>]`: Mewakili objek Azure Active Directory. Tipe directoryObject adalah tipe dasar untuk banyak tipe entitas direktori lainnya.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional untuk grup. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[GroupType <String[]>]`: Menentukan tipe grup dan keanggotaannya.  Jika kumpulan berisi Terpadu, grup adalah grup Microsoft 365; jika tidak, grup tersebut merupakan grup keamanan atau grup distribusi. Untuk detailnya, lihat gambaran umum grup. Jika koleksi menyertakan DynamicMembership, grup memiliki keanggotaan dinamis; jika tidak, keanggotaan statis.  Dikembalikan secara default. Mendukung $filter (eq, NOT).
  - `[HasMembersWithLicenseError <Boolean?>]`: Menunjukkan apakah ada anggota dalam grup ini yang memiliki kesalahan lisensi dari penetapan lisensi berbasis grup. Properti ini tidak pernah dikembalikan pada operasi GET. Anda bisa menggunakannya sebagai argumen $filter untuk mendapatkan grup yang memiliki anggota dengan kesalahan lisensi (yaitu, filter untuk properti ini menjadi benar).  Mendukung $filter (eq).
  - `[IsArchived <Boolean?>]`: 
  - `[IsAssignableToRole <Boolean?>]`: Menunjukkan apakah grup ini dapat ditetapkan ke peran Azure Active Directory. Properti ini hanya dapat diatur saat membuat grup dan tidak dapat berubah. Jika diatur ke true, properti securityEnabled juga harus diatur ke true dan grup tidak dapat berupa grup dinamis (yaitu, groupTypes tidak boleh berisi DynamicMembership). Hanya penelepon dalam peran administrator peran Administrator Global dan Istimewa yang dapat mengatur properti ini. Penelepon juga harus diberi izin Directory.AccessAsUser.All untuk mengatur properti ini. Untuk selengkapnya, lihat Menggunakan grup untuk mengelola Azure AD penetapan peran Dikembalikan secara default. Mendukung $filter (eq, ne, NOT).
  - `[MailEnabled <Boolean?>]`: Menentukan apakah grup diaktifkan melalui email. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT).
  - `[MailNickname <String>]`: Alias email untuk grup, unik dalam organisasi. Properti ini harus ditentukan ketika grup dibuat. Karakter ini tidak dapat digunakan dalam mailNickName: @()/[]';:.<>,SPACE. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, in, in, startsWith).
  - `[MembershipRule <String>]`: Aturan yang menentukan anggota untuk grup ini jika grup adalah grup dinamis (groupTypes berisi DynamicMembership). Untuk informasi selengkapnya tentang sintaks aturan keanggotaan, lihat Sintaks Aturan Keanggotaan. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith).
  - `[MembershipRuleProcessingState <String>]`: Menunjukkan apakah pemrosesan keanggotaan dinamis aktif atau dijeda. Nilai yang memungkinkan adalah Aktif atau Dijeda. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, in).
  - `[PermissionGrant <IMicrosoftGraphResourceSpecificPermissionGrant[]>]`: Izin yang telah diberikan untuk grup ke aplikasi tertentu. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[ClientAppId <String>]`: ID prinsipal layanan aplikasi Azure AD yang telah diberi akses. Baca-saja.
    - `[ClientId <String>]`: ID aplikasi Azure AD yang telah diberi akses. Baca-saja.
    - `[Permission <String>]`: Nama izin khusus sumber daya. Baca-saja.
    - `[PermissionType <String>]`: Tipe izin. Nilai yang memungkinkan adalah: Aplikasi, Didelegasikan. Baca-saja.
    - `[ResourceAppId <String>]`: ID aplikasi Azure AD yang menghosting sumber daya. Baca-saja.
  - `[PreferredDataLocation <String>]`: Lokasi data pilihan untuk grup. Untuk informasi selengkapnya, lihat OneDrive Multi-Geo Online. Dikembalikan secara default.
  - `[PreferredLanguage <String>]`: Bahasa pilihan untuk grup Microsoft 365. Harus mengikuti Kode ISO 639-1; misalnya 'en-US'. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, in, in, startsWith).
  - `[SecurityEnabled <Boolean?>]`: Menentukan apakah grup tersebut merupakan grup keamanan. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, in).
  - `[SecurityIdentifier <String>]`: Pengidentifikasi keamanan grup, digunakan dalam skenario Windows. Dikembalikan secara default.
  - `[Theme <String>]`: Menentukan tema warna grup Microsoft 365. Nilai yang mungkin adalah Teal, Ungu, Hijau, Biru, Merah Muda, Oranye atau Merah. Dikembalikan secara default.
  - `[Visibility <String>]`: Menentukan kebijakan gabungan grup dan visibilitas konten grup untuk grup. Nilai yang memungkinkan adalah: Privat, Publik, atau Hiddenmembership. Hiddenmembership dapat diatur hanya untuk grup Microsoft 365, ketika grup dibuat. Tidak dapat diperbarui nanti. Nilai visibilitas lainnya dapat diperbarui setelah pembuatan grup. Jika nilai visibilitas tidak ditentukan selama pembuatan grup di Microsoft Graph, grup keamanan dibuat sebagai Privat secara default dan grup Microsoft 365 adalah Publik. Lihat opsi visibilitas grup untuk mempelajari selengkapnya. Dikembalikan secara default.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

## RELATED LINKS
