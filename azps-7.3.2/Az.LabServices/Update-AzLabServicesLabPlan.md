---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/update-azlabserviceslabplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesLabPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesLabPlan.md
ms.openlocfilehash: bbe3cb3462c41de0de24835570fccc55afe98ec8
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140393639"
---
# Update-AzLabServicesLabPlan

## SYNOPSIS
Operasi untuk memperbarui sumber daya Rencana Lab.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzLabServicesLabPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AllowedRegion <String[]>] [-DefaultAutoShutdownProfileDisconnectDelay <TimeSpan>]
 [-DefaultAutoShutdownProfileIdleDelay <TimeSpan>] [-DefaultAutoShutdownProfileNoConnectDelay <TimeSpan>]
 [-DefaultAutoShutdownProfileShutdownOnDisconnect <EnableState>]
 [-DefaultAutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode>]
 [-DefaultAutoShutdownProfileShutdownWhenNotConnected <EnableState>]
 [-DefaultConnectionProfileClientRdpAccess <ConnectionType>]
 [-DefaultConnectionProfileClientSshAccess <ConnectionType>]
 [-DefaultConnectionProfileWebRdpAccess <ConnectionType>]
 [-DefaultConnectionProfileWebSshAccess <ConnectionType>] [-DefaultNetworkProfileSubnetId <String>]
 [-LinkedLmsInstance <String>] [-SharedGalleryId <String>] [-SupportInfoEmail <String>]
 [-SupportInfoInstruction <String>] [-SupportInfoPhone <String>] [-SupportInfoUrl <String>] [-Tag <String[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### LabPlan
```
Update-AzLabServicesLabPlan -LabPlan <LabPlan> [-SubscriptionId <String>] [-AllowedRegion <String[]>]
 [-DefaultAutoShutdownProfileDisconnectDelay <TimeSpan>] [-DefaultAutoShutdownProfileIdleDelay <TimeSpan>]
 [-DefaultAutoShutdownProfileNoConnectDelay <TimeSpan>]
 [-DefaultAutoShutdownProfileShutdownOnDisconnect <EnableState>]
 [-DefaultAutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode>]
 [-DefaultAutoShutdownProfileShutdownWhenNotConnected <EnableState>]
 [-DefaultConnectionProfileClientRdpAccessEnabled <ConnectionType>]
 [-DefaultConnectionProfileClientSshAccessEnabled <ConnectionType>] [-DefaultNetworkProfileSubnetId <String>]
 [-LinkedLmsInstance <String>] [-SharedGalleryId <String>] [-SupportInfoEmail <String>]
 [-SupportInfoInstruction <String>] [-SupportInfoPhone <String>] [-SupportInfoUrl <String>] [-Tag <String[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk memperbarui sumber daya Rencana Lab.

## EXAMPLES

### Contoh 1: Rencana Update Lab
```powershell
PS C:\> Update-AzLabServicesLabPlan -ResourceGroupName "Group Name" -Name "LabPlan Name" -DefaultAutoShutdownProfileShutdownOnDisconnect 'Enabled' -DefaultAutoShutdownProfileDisconnectDelay "00:17:00"

Location Name
-------- ----
westus2  LabPlan Name
```

Contoh ini memperbarui rencana lab mengaktifkan Penutupan saat pemutusan dengan penundaan 17 menit.

## PARAMETERS

### -AllowedRegion
Wilayah yang diizinkan untuk digunakan oleh pembuat lab ketika membuat lab menggunakan rencana lab ini.

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

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -DefaultAutoShutdownProfileDisconnectDelay
Jumlah waktu VM akan tetap berjalan setelah pengguna memutuskan sambungan jika perilaku ini diaktifkan.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultAutoShutdownProfileIdleDelay
Jumlah waktu VM akan diam sebelum penutupan jika perilaku ini diaktifkan.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultAutoShutdownProfileNoConnectDelay
Jumlah waktu VM akan tetap berjalan sebelum penutupannya jika tidak ada koneksi yang dilakukan dan perilaku ini diaktifkan.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultAutoShutdownProfileShutdownOnDisconnect
Apakah penutupan saat pemutusan diaktifkan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.EnableState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultAutoShutdownProfileShutdownOnIdle
Apakah VM akan mengalami penutupan jika vm telah diam selama periode waktu tertentu.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ShutdownOnIdleMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultAutoShutdownProfileShutdownWhenNotConnected
Apakah VM akan mengalami penutupan saat belum tersambung setelah beberapa waktu.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.EnableState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConnectionProfileClientRdpAccess
Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConnectionProfileClientRdpAccessEnabled


```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: LabPlan
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConnectionProfileClientSshAccess
Tingkat akses yang diaktifkan untuk Akses Klien melalui LYNC.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConnectionProfileClientSshAccessEnabled


```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: LabPlan
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConnectionProfileWebRdpAccess
Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConnectionProfileWebSshAccess
Tingkat akses yang diaktifkan untuk Akses Web melalui BLUETOOTH.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultNetworkProfileSubnetId
Id sumber daya subnet eksternal

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

### -LabPlan
Untuk membuat, lihat bagian CATATAN untuk properti LABPLAN dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.LabPlan
Parameter Sets: LabPlan
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LinkedLmsInstance
Url Dasar contoh lms rencana lab ini bisa menautkan daftar nama lab terhadap.

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

### -Nama
Nama rencana lab yang mengidentifikasinya secara unik di dalam grup sumber daya.
Digunakan dalam URI sumber daya dan dalam UI.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: LabPlanName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -SharedGalleryId
ID Sumber Daya Galeri Gambar Bersama yang dilampirkan ke rencana lab ini.
Saat menyimpan gambar mesin virtual templat lab, gambar itu akan tetap ada di galeri ini.
Gambar yang dibagikan dari galeri dapat dibuat tersedia untuk digunakan saat membuat lab baru.

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

### -SupportInfoEmail
Alamat email kontak dukungan.

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

### -SupportInfoInstruction
Instruksi dukungan.

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

### -SupportInfoPhone
Nomor telepon kontak dukungan.

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

### -SupportInfoUrl
Alamat web dukungan.

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

### -Tag
Tag sumber daya.

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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.LabPlan

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ILabPlan

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LABPLAN <LabPlan>: 
  - `Location <String>`: Lokasi geo-lokasi tempat sumber daya berada
  - `[AllowedRegion <String[]>]`: Wilayah yang diizinkan untuk digunakan oleh pembuat lab ketika membuat lab menggunakan rencana lab ini.
  - `[DefaultAutoShutdownProfileDisconnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan setelah pengguna memutuskan sambungan jika perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileIdleDelay <TimeSpan?>]`: Jumlah waktu VM akan diam sebelum terjadinya penutupan jika perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileNoConnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan sebelum penutupan jika tidak ada koneksi yang dilakukan dan perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileShutdownOnDisconnect <EnableState?>]`: Apakah penutupan saat pemutusan terputus diaktifkan
  - `[DefaultAutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode?>]`: Baik saat vm akan terjadi penutupan jika vm telah diam selama suatu waktu.
  - `[DefaultAutoShutdownProfileShutdownWhenNotConnected <EnableState?>]`: Baik saat vm akan terjadi penutupan apabila belum tersambung setelah beberapa waktu.
  - `[DefaultConnectionProfileClientRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.
  - `[DefaultConnectionProfileClientSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui LYNC.
  - `[DefaultConnectionProfileWebRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.
  - `[DefaultConnectionProfileWebSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui MSDN.
  - `[DefaultNetworkProfileSubnetId <String>]`: Id sumber daya subnet eksternal
  - `[LinkedLmsInstance <String>]`: Url Dasar contoh lms rencana lab ini bisa menautkan daftar nama lab terhadap.
  - `[SharedGalleryId <String>]`: ID Sumber Daya dari Galeri Gambar Bersama yang dilampirkan ke rencana lab ini. Saat menyimpan gambar mesin virtual templat lab, gambar itu akan tetap ada di galeri ini. Gambar yang dibagikan dari galeri dapat dibuat tersedia untuk digunakan saat membuat lab baru.
  - `[SupportInfoEmail <String>]`: Alamat email kontak dukungan.
  - `[SupportInfoInstruction <String>]`: Petunjuk dukungan.
  - `[SupportInfoPhone <String>]`: Nomor telepon kontak dukungan.
  - `[SupportInfoUrl <String>]`: Alamat web dukungan.
  - `[SystemDataCreatedAt <DateTime?>]`: Timestamp pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Timestamp sumber daya modifikasi terakhir (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir diubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir diubah sumber daya.
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

