---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/update-azlabservicesplanimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesPlanImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Update-AzLabServicesPlanImage.md
ms.openlocfilehash: c8f207ac3bfdbef61c2ba0fda9943af262f0394d
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138272651"
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

### Contoh 1: Perbarui lab gambar rencana.
```powershell
PS C:\> Update-AzLabServicesPlanImage -ResourceGroupName "Group Name" -LabPlanName "LabPlan Name" -Name "Image Name" -EnabledState "Enabled"

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
Nama rencana lab yang mengidentifikasinya secara unik di dalam grup sumber daya.
Digunakan dalam URI sumber daya dan dalam UI.

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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IImage

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

