---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/update-azlabservicesplanimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesPlanImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesPlanImage.md
ms.openlocfilehash: de5af9d81fb1844e1f2b0ea53fa74c1890db17ab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141992118"
---
# Update-AzLabServicesPlanImage

## SYNOPSIS
Memperbarui sumber daya gambar.

## SYNTAX

### ResourceId (Default)
```
Update-AzLabServicesPlanImage -EnabledState <EnableState> -ResourceId <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [<CommonParameters>]
```

### LabPlan
```
Update-AzLabServicesPlanImage -LabPlan <LabPlan> -Name <String> -EnabledState <EnableState>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### UpdateExpanded
```
Update-AzLabServicesPlanImage -LabPlanName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-EnabledState <EnableState>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui sumber daya gambar.

## EXAMPLES

### Contoh 1: Memperbarui gambar rencana lab.
```powershell
Update-AzLabServicesPlanImage -ResourceGroupName "Group Name" -LabPlanName "LabPlan Name" -Name "Image Name" -EnabledState "Enabled"
```

```output
Name
----
Image Name
```

Contoh ini mengaktifkan gambar untuk digunakan di lab.

## PARAMETERS

### -AsJob


```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ResourceId
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

### -EnabledState
Apakah gambar diaktifkan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.EnableState
Parameter Sets: (All)
Aliases:

Required: True
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

### -LabPlanName
Nama rencana lab yang mengidentifikasinya secara unik di dalamnya berisi grup sumber daya.
Digunakan dalam URI sumber daya dan di UI.

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
Nama gambar.

```yaml
Type: System.String
Parameter Sets: LabPlan, UpdateExpanded
Aliases: ImageName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait


```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ResourceId
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.LabPlan

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IImage

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LABPLAN <LabPlan>: 
  - `Location <String>`: Lokasi geografis tempat sumber daya tinggal
  - `[AllowedRegion <String[]>]`: Kawasan yang diperbolehkan untuk digunakan oleh pembuat lab saat membuat lab menggunakan rencana lab ini.
  - `[DefaultAutoShutdownProfileDisconnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan setelah pengguna terputus jika perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileIdleDelay <TimeSpan?>]`: Jumlah waktu VM akan diam sebelum dimatikan jika perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileNoConnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan sebelum mematikan jika tidak ada koneksi yang dibuat dan perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileShutdownOnDisconnect <EnableState?>]`: Apakah pemutusan saat diputuskan diaktifkan
  - `[DefaultAutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode?>]`: Apakah VM akan dimatikan ketika diam selama periode waktu tertentu.
  - `[DefaultAutoShutdownProfileShutdownWhenNotConnected <EnableState?>]`: Apakah VM akan dimatikan saat VM belum tersambung setelah periode waktu tertentu.
  - `[DefaultConnectionProfileClientRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.
  - `[DefaultConnectionProfileClientSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui SSH.
  - `[DefaultConnectionProfileWebRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.
  - `[DefaultConnectionProfileWebSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui SSH.
  - `[DefaultNetworkProfileSubnetId <String>]`: Id sumber daya subnet eksternal
  - `[LinkedLmsInstance <String>]`: Url dasar contoh lms rencana lab ini dapat menautkan daftar nama lab terhadap.
  - `[SharedGalleryId <String>]`: ID sumber daya dari Shared Image Gallery yang dilampirkan ke rencana lab ini. Ketika menyimpan gambar mesin virtual templat lab, gambar itu akan tetap ada di galeri ini. Gambar bersama dari galeri dapat disediakan untuk digunakan saat membuat laboratorium baru.
  - `[SupportInfoEmail <String>]`: Mendukung alamat email kontak.
  - `[SupportInfoInstruction <String>]`: Instruksi dukungan.
  - `[SupportInfoPhone <String>]`: Nomor telepon kontak dukungan.
  - `[SupportInfoUrl <String>]`: Alamat web dukungan.
  - `[SystemDataCreatedAt <DateTime?>]`: Stempel waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Cap waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir mengubah sumber daya.
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

