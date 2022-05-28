---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/add-azadgroupmember
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADGroupMember.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Add-AzADGroupMember.md
ms.openlocfilehash: ee61636a70346baa6c16bd0e62c51987f3ab0703
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145643890"
---
# Add-AzADGroupMember

## SYNOPSIS
Menambahkan anggota ke grup.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/add-azadgroupmember) untuk informasi terbaru.

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
$groupid=(Get-AzADGroup -DisplayName $gname).Id
$members=@()
$members+=(Get-AzADUser -DisplayName $uname).Id
$members+=(Get-AzADServicePrincipal -ApplicationId $appid).Id
Add-AzADGroupMember -TargetGroupObjectId $groupid -MemberObjectId $members
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
Id objek anggota yang akan ditambahkan ke grup target.

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
Objek grup target, dapat digunakan sebagai input alur.
Untuk membuat, lihat bagian NOTES untuk properti TARGETGROUPOBJECT dan buat tabel hash.

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.MicrosoftGraphGroup

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TARGETGROUPOBJECT <MicrosoftGraphGroup>: Objek grup target, dapat digunakan sebagai input alur.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
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
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

## RELATED LINKS
