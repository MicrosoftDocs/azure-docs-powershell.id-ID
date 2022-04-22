---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/update-azlabservicesschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesSchedule.md
ms.openlocfilehash: fa713664f7ea2c728e20463df98ac0a9ebfa3b79
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142999703"
---
# Update-AzLabServicesSchedule

## SYNOPSIS
Operasi untuk memperbarui jadwal lab.

## SYNTAX

### ResourceId (Default)
```
Update-AzLabServicesSchedule -ResourceId <String> [-SubscriptionId <String>] [-Note <String>]
 [-RecurrencePatternExpirationDate <DateTime>] [-RecurrencePatternFrequency <RecurrenceFrequency>]
 [-RecurrencePatternInterval <Int32>] [-RecurrencePatternWeekDay <WeekDay[]>] [-StartAt <DateTime>]
 [-StopAt <DateTime>] [-TimeZoneId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Lab
```
Update-AzLabServicesSchedule -Lab <Lab> -Name <String> [-SubscriptionId <String>] [-Note <String>]
 [-RecurrencePatternExpirationDate <DateTime>] [-RecurrencePatternFrequency <RecurrenceFrequency>]
 [-RecurrencePatternInterval <Int32>] [-RecurrencePatternWeekDay <WeekDay[]>] [-StartAt <DateTime>]
 [-StopAt <DateTime>] [-TimeZoneId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### UpdateExpanded
```
Update-AzLabServicesSchedule -LabName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-Note <String>] [-RecurrencePatternExpirationDate <DateTime>]
 [-RecurrencePatternFrequency <RecurrenceFrequency>] [-RecurrencePatternInterval <Int32>]
 [-RecurrencePatternWeekDay <WeekDay[]>] [-StartAt <DateTime>] [-StopAt <DateTime>] [-TimeZoneId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk memperbarui jadwal lab.

## EXAMPLES

### Contoh 1: Perbarui jadwal yang sudah ada.
```powershell
Update-AzLabServicesSchedule -ResourceGroupName "Group Name" -LabName "Lab Name" -Name "Schedule Name" -Note "Update note."
```

```output
Name                   Type
----                   ----
Schedule Name          Microsoft.LabServices/labs/schedules
```

Memperbarui jadwal untuk menambahkan informasi catatan tambahan.

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
Untuk membangun, lihat bagian CATATAN untuk properti LAB dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.Lab
Parameter Sets: Lab
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LabName
Nama lab yang mengidentifikasinya secara unik di dalamnya berisi akun lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama jadwal yang mengidentifikasinya secara unik di dalam lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: Lab, UpdateExpanded
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
Saat pengulangan akan kedaluwarsa.
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
Interval untuk mengaktifkan jadwal.
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
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId


```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartAt
Ketika mesin virtual pengguna lab akan dimulai.
Offset stempel waktu akan diabaikan dan timeZoneId digunakan sebagai gantinya.

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
Ketika mesin virtual pengguna lab akan dihentikan.
Offset stempel waktu akan diabaikan dan timeZoneId digunakan sebagai gantinya.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ISchedule

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LAB <Lab>: 
  - `Location <String>`: Lokasi geografis tempat sumber daya tinggal
  - `[AdditionalCapabilityInstallGpuDriver <EnableState?>]`: Tandai ke driver GPU khusus pra-instal.
  - `[AdminUserPassword <String>]`: Kata sandi untuk pengguna. Ini diperlukan untuk CreateOption TemplateVM.
  - `[AdminUserUsername <String>]`: Nama pengguna yang digunakan saat masuk ke VM lab.
  - `[AutoShutdownProfileDisconnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan setelah pengguna terputus jika perilaku ini diaktifkan.
  - `[AutoShutdownProfileIdleDelay <TimeSpan?>]`: Jumlah waktu VM akan diam sebelum dimatikan jika perilaku ini diaktifkan.
  - `[AutoShutdownProfileNoConnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan sebelum mematikan jika tidak ada koneksi yang dibuat dan perilaku ini diaktifkan.
  - `[AutoShutdownProfileShutdownOnDisconnect <EnableState?>]`: Apakah pemutusan saat diputuskan diaktifkan
  - `[AutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode?>]`: Apakah VM akan dimatikan ketika diam selama periode waktu tertentu.
  - `[AutoShutdownProfileShutdownWhenNotConnected <EnableState?>]`: Apakah VM akan dimatikan saat VM belum tersambung setelah periode waktu tertentu.
  - `[ConnectionProfileClientRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.
  - `[ConnectionProfileClientSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui SSH.
  - `[ConnectionProfileWebRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.
  - `[ConnectionProfileWebSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui SSH.
  - `[Description <String>]`: Deskripsi lab.
  - `[ImageReferenceId <String>]`: ID sumber daya gambar
  - `[ImageReferenceOffer <String>]`: Penawaran gambar jika ada.
  - `[ImageReferencePublisher <String>]`: Penerbit gambar
  - `[ImageReferenceSku <String>]`: SKU gambar
  - `[ImageReferenceVersion <String>]`: Versi gambar yang ditentukan pada pembuatan.
  - `[NetworkProfileLoadBalancerId <String>]`: Id sumber daya penyeimbang beban eksternal
  - `[NetworkProfilePublicIPId <String>]`: Id sumber daya IP publik eksternal
  - `[NetworkProfileSubnetId <String>]`: Id sumber daya subnet eksternal
  - `[NonAdminUserPassword <String>]`: Kata sandi untuk pengguna. Ini diperlukan untuk CreateOption TemplateVM.
  - `[NonAdminUserUsername <String>]`: Nama pengguna yang digunakan saat masuk ke VM lab.
  - `[PlanId <String>]`: ID rencana lab. Digunakan selama pembuatan sumber daya untuk menyediakan default dan bertindak sebagai wadah izin saat membuat lab melalui labs.azure.com. Mengatur labPlanId di lab yang sudah ada menyediakan organisasi..
  - `[RosterProfileActiveDirectoryGroupId <String>]`: ID grup AAD tempat daftar lab ini diisi. Mengatur ini mengaktifkan mode sinkronisasi AAD.
  - `[RosterProfileLmsInstance <String>]`: URI dasar yang mengidentifikasi instans IM.
  - `[RosterProfileLtiClientId <String>]`: Id unik dari alat layanan lab azure di lms.
  - `[RosterProfileLtiContextId <String>]`: Pengidentifikasi konteks unik untuk laboratorium di lms.
  - `[RosterProfileLtiRosterEndpoint <String>]`: Uri dari titik akhir layanan nama dan peran di lms untuk kelas yang melekat pada lab ini.
  - `[SecurityProfileOpenAccess <EnableState?>]`: Apakah ada pengguna atau hanya pengguna tertentu yang dapat mendaftar ke lab.
  - `[SkuCapacity <Int32?>]`: Jika SKU mendukung penskalaan keluar/in maka bilangan bulat kapasitas harus disertakan. Jika skala keluar/masuk tidak dimungkinkan untuk sumber daya ini mungkin dihilangkan.
  - `[SkuFamily <String>]`: Jika layanan memiliki generasi perangkat keras yang berbeda, untuk SKU yang sama, maka yang dapat ditangkap di sini.
  - `[SkuName <String>]`: Nama SKU. Bekas - P3. Biasanya berupa kode huruf+angka
  - `[SkuSize <String>]`: Ukuran SKU. Ketika bidang nama adalah kombinasi tingkat dan beberapa nilai lainnya, ini akan menjadi kode mandiri. 
  - `[SkuTier <SkuTier?>]`: Bidang ini diperlukan untuk diterapkan oleh Penyedia Sumber Daya jika layanan memiliki lebih dari satu tingkat, tetapi tidak diperlukan pada PUT.
  - `[SystemDataCreatedAt <DateTime?>]`: Stempel waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Cap waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir mengubah sumber daya.
  - `[Title <String>]`: Judul lab.
  - `[VirtualMachineProfileCreateOption <CreateOption?>]`: Menunjukkan dari mesin virtual lab mana yang dibuat.
  - `[VirtualMachineProfileUsageQuota <TimeSpan?>]`: Kuota awal yang dialokasikan untuk setiap pengguna lab. Harus rentang waktu antara 0 dan 9999 jam.
  - `[VirtualMachineProfileUseSharedPassword <EnableState?>]`: Mengaktifkan opsi ini akan menggunakan kata sandi yang sama untuk semua VM pengguna.
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

