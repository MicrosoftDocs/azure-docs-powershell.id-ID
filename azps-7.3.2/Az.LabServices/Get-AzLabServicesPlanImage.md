---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/get-azlabservicesplanimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesPlanImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesPlanImage.md
ms.openlocfilehash: c67f34974c144078d5464b36bb8097100025c76b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140549519"
---
# Get-AzLabServicesPlanImage

## SYNOPSIS
Mendapatkan sumber daya gambar.

## SYNTAX

### ResourceId (Default)
```
Get-AzLabServicesPlanImage -ResourceId <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzLabServicesPlanImage -LabPlanName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### LabPlan
```
Get-AzLabServicesPlanImage -LabPlan <LabPlan> [-Name <String>] [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzLabServicesPlanImage -LabPlanName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-Filter <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListByDisplayName
```
Get-AzLabServicesPlanImage -DisplayName <String> -LabPlanName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan sumber daya gambar.

## EXAMPLES

### Contoh 1: Dapatkan semua gambar di rencana lab.
```powershell
PS C:\> Get-AzLabServicesPlanImage -LabPlanName "Plan Name" -ResourceGroupName "Group Name"

Name
----
128technology.128t_networking_platform.128t_networking_platform
128technology.128technology_conductor_hourly.128technology_conductor_hourly_427
128technology.128technology_conductor_hourly.128technology_conductor_hourly_452
```

Mendapatkan semua gambar yang tersedia, ini biasanya daftar gambar yang panjang.

### Contoh 2: Dapatkan gambar spesifik di rencana lab.
```powershell
PS C:\> Get-AzLabServicesPlanImage -LabPlanName "Plan Name"  -ResourceGroupName "Group Name" -Name 'canonical.0001-com-ubuntu-server-focal.20_04-lts'

Name
----
canonical.0001-com-ubuntu-server-focal.20_04-lts
```

Mengembalikan gambar tertentu.

### Contoh 3: Dapatkan gambar tertentu menggunakan nama tampilan.
```powershell
PS C:\> Get-AzLabServicesPlanImage -LabPlanName "Plan Name" -ResourceGroupName "Group Name" -DisplayName 'Ubuntu Server 20.04 LTS'

Name
----
canonical.0001-com-ubuntu-server-focal.20_04-lts
```

Mengembalikan gambar tertentu dengan nama tampilan.

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

### -DisplayName


```yaml
Type: System.String
Parameter Sets: ListByDisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Filter yang akan diterapkan ke operasi.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

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

### -LabPlanName
Nama rencana lab yang mengidentifikasinya secara unik di dalam grup sumber daya.
Digunakan dalam URI sumber daya dan dalam UI.

```yaml
Type: System.String
Parameter Sets: Get, List, ListByDisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama gambar.

```yaml
Type: System.String
Parameter Sets: Get, LabPlan
Aliases: ImageName

Required: True
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
Parameter Sets: Get, List, ListByDisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.LabPlan

### System.String

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

