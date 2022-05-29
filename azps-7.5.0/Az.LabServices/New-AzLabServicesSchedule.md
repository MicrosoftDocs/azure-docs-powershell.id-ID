---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/new-azlabservicesschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesSchedule.md
ms.openlocfilehash: caa2d53dc90a950ef512323f055cd3f66958e8cf
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145795211"
---
# New-AzLabServicesSchedule

## SYNOPSIS
Operasi untuk membuat atau memperbarui jadwal lab.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.labservices/new-azlabservicesschedule) untuk informasi terbaru.

## SYNTAX

### CreateExpanded (Default)
```
New-AzLabServicesSchedule -LabName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-Note <String>] [-RecurrencePatternExpirationDate <DateTime>]
 [-RecurrencePatternFrequency <RecurrenceFrequency>] [-RecurrencePatternInterval <Int32>]
 [-RecurrencePatternWeekDay <WeekDay[]>] [-StartAt <DateTime>] [-StopAt <DateTime>] [-TimeZoneId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Laboratorium
```
New-AzLabServicesSchedule -Lab <Lab> -Name <String> [-SubscriptionId <String>] [-Note <String>]
 [-RecurrencePatternExpirationDate <DateTime>] [-RecurrencePatternFrequency <RecurrenceFrequency>]
 [-RecurrencePatternInterval <Int32>] [-RecurrencePatternWeekDay <WeekDay[]>] [-StartAt <DateTime>]
 [-StopAt <DateTime>] [-TimeZoneId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat atau memperbarui jadwal lab.

## EXAMPLES

### Contoh 1: Buat jadwal baru di lab.
```powershell
New-AzLabServicesSchedule `
            -ResourceGroupName "Group Name" `
            -LabName "Lab Name" `
            -Name "Schedule Name" `
            -StartAt "$((Get-Date).AddHours(5))" `
            -StopAt "$((Get-Date).AddHours(6))" `
            -RecurrencePatternFrequency 'Weekly' `
            -RecurrencePatternInterval 1 `
            -RecurrencePatternWeekDay @($((Get-Date).DayOfWeek)) `
            -RecurrencePatternExpirationDate $((Get-Date).AddDays(20)) `
            -TimeZoneId 'America/Los_Angeles'
```

```output
Name
----
Schedule Name
```

Buat jadwal mingguan.

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

### -Lab
Untuk membuat, lihat bagian CATATAN untuk properti LAB dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.Lab
Parameter Sets: Lab
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LabName
Nama lab yang secara unik mengidentifikasinya dalam berisi akun lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama jadwal yang secara unik mengidentifikasinya di dalam lab yang berisi.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ScheduleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Catatan
Catatan untuk jadwal ini.

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

### -RecurrencePatternExpirationDate
Ketika pengulangan akan kedaluwarsa.
Tanggal ini inklusif.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrencePatternFrequency
Frekuensi pengulangan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.RecurrenceFrequency
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrencePatternInterval
Interval untuk memanggil jadwal.
Misalnya, interval = 2 dan RecurrenceFrequency.Daily akan berjalan setiap 2 hari.
Ketika tidak ada interval yang disediakan, interval 1 digunakan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrencePatternWeekDay
Hari dalam seminggu jadwal berjalan.
Digunakan saat Frekuensi diatur ke Mingguan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.WeekDay[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartAt
Ketika komputer virtual pengguna lab akan dimulai.
Offset tanda waktu akan diabaikan dan timeZoneId digunakan sebagai gantinya.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopAt
Ketika komputer virtual pengguna lab akan dihentikan.
Offset tanda waktu akan diabaikan dan timeZoneId digunakan sebagai gantinya.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeZoneId
Id zona waktu IANA untuk jadwal.

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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.Lab

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ISchedule

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LAB <Lab>: 
  - `Location <String>`: Lokasi geografis tempat sumber daya berada
  - `[AdditionalCapabilityInstallGpuDriver <EnableState?>]`: Benderai ke driver GPU khusus pra-instal.
  - `[AdminUserPassword <String>]`: Kata sandi untuk pengguna. Ini diperlukan untuk TemplateVM createOption.
  - `[AdminUserUsername <String>]`: Nama pengguna yang digunakan saat masuk ke VM lab.
  - `[AutoShutdownProfileDisconnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan setelah pengguna terputus jika perilaku ini diaktifkan.
  - `[AutoShutdownProfileIdleDelay <TimeSpan?>]`: Jumlah waktu VM akan menganggur sebelum dimatikan jika perilaku ini diaktifkan.
  - `[AutoShutdownProfileNoConnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan sebelum dimatikan jika tidak ada koneksi yang dibuat dan perilaku ini diaktifkan.
  - `[AutoShutdownProfileShutdownOnDisconnect <EnableState?>]`: Apakah pematian saat pemutusan sambungan diaktifkan
  - `[AutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode?>]`: Apakah VM akan dimatikan ketika telah menganggur untuk jangka waktu tertentu.
  - `[AutoShutdownProfileShutdownWhenNotConnected <EnableState?>]`: Apakah VM akan dimatikan ketika belum tersambung setelah jangka waktu tertentu.
  - `[ConnectionProfileClientRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.
  - `[ConnectionProfileClientSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui SSH.
  - `[ConnectionProfileWebRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.
  - `[ConnectionProfileWebSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui SSH.
  - `[Description <String>]`: Deskripsi lab.
  - `[ImageReferenceId <String>]`: ID sumber daya gambar
  - `[ImageReferenceOffer <String>]`: Penawaran gambar jika berlaku.
  - `[ImageReferencePublisher <String>]`: Penerbit gambar
  - `[ImageReferenceSku <String>]`: SKU gambar
  - `[ImageReferenceVersion <String>]`: Versi gambar yang ditentukan pada pembuatan.
  - `[NetworkProfileLoadBalancerId <String>]`: Id sumber daya load balancer eksternal
  - `[NetworkProfilePublicIPId <String>]`: Id sumber daya IP publik eksternal
  - `[NetworkProfileSubnetId <String>]`: Id sumber daya subnet eksternal
  - `[NonAdminUserPassword <String>]`: Kata sandi untuk pengguna. Ini diperlukan untuk TemplateVM createOption.
  - `[NonAdminUserUsername <String>]`: Nama pengguna yang digunakan saat masuk ke VM lab.
  - `[PlanId <String>]`: ID rencana lab. Digunakan selama pembuatan sumber daya untuk menyediakan default dan bertindak sebagai kontainer izin saat membuat lab melalui labs.azure.com. Mengatur labPlanId di lab yang ada menyediakan organisasi..
  - `[RosterProfileActiveDirectoryGroupId <String>]`: ID grup AAD tempat daftar lab ini diisi. Memiliki set ini memungkinkan mode sinkronisasi AAD.
  - `[RosterProfileLmsInstance <String>]`: URI dasar yang mengidentifikasi instans lms.
  - `[RosterProfileLtiClientId <String>]`: Id unik alat layanan lab azure di lms.
  - `[RosterProfileLtiContextId <String>]`: Pengidentifikasi konteks unik untuk lab di lms.
  - `[RosterProfileLtiRosterEndpoint <String>]`: Uri titik akhir layanan nama dan peran pada lms untuk kelas yang melekat pada lab ini.
  - `[SecurityProfileOpenAccess <EnableState?>]`: Apakah ada pengguna atau hanya pengguna tertentu yang dapat mendaftar ke lab.
  - `[SkuCapacity <Int32?>]`: Jika SKU mendukung peluasan skala/masuk, bilangan bulat kapasitas harus disertakan. Jika peluasan/masuk skala tidak dimungkinkan untuk sumber daya, ini dapat dihilangkan.
  - `[SkuFamily <String>]`: Jika layanan memiliki generasi perangkat keras yang berbeda, untuk SKU yang sama, maka itu dapat ditangkap di sini.
  - `[SkuName <String>]`: Nama SKU. Mantan - P3. Biasanya kode huruf+angka
  - `[SkuSize <String>]`: Ukuran SKU. Ketika bidang nama adalah kombinasi tingkat dan beberapa nilai lainnya, ini akan menjadi kode mandiri. 
  - `[SkuTier <SkuTier?>]`: Bidang ini diperlukan untuk diimplementasikan oleh Penyedia Sumber Jika layanan memiliki lebih dari satu tingkat, tetapi tidak diperlukan pada PUT.
  - `[SystemDataCreatedAt <DateTime?>]`: Tanda waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Jenis identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Tanda waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir memodifikasi sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Jenis identitas yang terakhir memodifikasi sumber daya.
  - `[Title <String>]`: Judul lab.
  - `[VirtualMachineProfileCreateOption <CreateOption?>]`: Menunjukkan dari komputer virtual lab mana yang dibuat.
  - `[VirtualMachineProfileUsageQuota <TimeSpan?>]`: Kuota awal yang dialokasikan untuk setiap pengguna lab. Harus rentang waktu antara 0 dan 9999 jam.
  - `[VirtualMachineProfileUseSharedPassword <EnableState?>]`: Mengaktifkan opsi ini akan menggunakan kata sandi yang sama untuk semua VM pengguna.
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

