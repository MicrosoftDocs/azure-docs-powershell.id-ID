---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/get-azlabservicesplanimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesPlanImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesPlanImage.md
ms.openlocfilehash: af1546d06b8d694bba550f27846602d4e2dc3ed9
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146595660"
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

### Contoh 1: Dapatkan semua gambar dalam paket lab.
```powershell
Get-AzLabServicesPlanImage -LabPlanName "Plan Name" -ResourceGroupName "Group Name"
```

```output
Name
----
128technology.128t_networking_platform.128t_networking_platform
128technology.128technology_conductor_hourly.128technology_conductor_hourly_427
128technology.128technology_conductor_hourly.128technology_conductor_hourly_452
```

Mendapatkan semua gambar yang tersedia, ini biasanya merupakan daftar gambar yang panjang.

### Contoh 2: Dapatkan gambar tertentu dalam paket lab.
```powershell
Get-AzLabServicesPlanImage -LabPlanName "Plan Name"  -ResourceGroupName "Group Name" -Name 'canonical.0001-com-ubuntu-server-focal.20_04-lts'
```

```output
Name
----
canonical.0001-com-ubuntu-server-focal.20_04-lts
```

Mengembalikan gambar tertentu.

### Contoh 3: Dapatkan gambar tertentu menggunakan nama tampilan.
```powershell
Get-AzLabServicesPlanImage -LabPlanName "Plan Name" -ResourceGroupName "Group Name" -DisplayName 'Ubuntu Server 20.04 LTS'
```

```output
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
Untuk membuat, lihat bagian NOTES untuk properti LABPLAN dan buat tabel hash.

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
Nama paket lab yang secara unik mengidentifikasinya dalam grup sumber daya.
Digunakan dalam URI sumber daya dan di UI.

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

### -Name
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
Nama tidak peka huruf besar/kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.LabPlan

### System.String

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IImage

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LABPLAN `<LabPlan>`: 
  - `Location <String>`: Lokasi geografis tempat sumber daya berada
  - `[AllowedRegion <String[]>]`: Wilayah yang diizinkan untuk digunakan pembuat lab saat membuat lab menggunakan rencana lab ini.
  - `[DefaultAutoShutdownProfileDisconnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan setelah pengguna terputus jika perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileIdleDelay <TimeSpan?>]`: Jumlah waktu VM akan diam sebelum dimatikan jika perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileNoConnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan sebelum dimatikan jika tidak ada koneksi yang dibuat dan perilaku ini diaktifkan.
  - `[DefaultAutoShutdownProfileShutdownOnDisconnect <EnableState?>]`: Apakah matikan saat pemutusan sambungan diaktifkan
  - `[DefaultAutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode?>]`: Apakah VM akan dimatikan ketika telah menganggur untuk jangka waktu tertentu.
  - `[DefaultAutoShutdownProfileShutdownWhenNotConnected <EnableState?>]`: Apakah VM akan dimatikan saat belum tersambung setelah jangka waktu tertentu.
  - `[DefaultConnectionProfileClientRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.
  - `[DefaultConnectionProfileClientSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui SSH.
  - `[DefaultConnectionProfileWebRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.
  - `[DefaultConnectionProfileWebSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui SSH.
  - `[DefaultNetworkProfileSubnetId <String>]`: Id sumber daya subnet eksternal
  - `[LinkedLmsInstance <String>]`: Url Dasar instans lms rencana lab ini dapat menautkan daftar nama lab.
  - `[SharedGalleryId <String>]`: ID sumber daya dari Shared Image Gallery yang dilampirkan ke paket lab ini. Saat menyimpan citra komputer virtual templat lab, gambar tersebut akan bertahan di galeri ini. Gambar bersama dari galeri dapat digunakan saat membuat lab baru.
  - `[SupportInfoEmail <String>]`: Mendukung alamat email kontak.
  - `[SupportInfoInstruction <String>]`: Instruksi dukungan.
  - `[SupportInfoPhone <String>]`: Mendukung nomor telepon kontak.
  - `[SupportInfoUrl <String>]`: Alamat web dukungan.
  - `[SystemDataCreatedAt <DateTime?>]`: Tanda waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Jenis identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Tanda waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir memodifikasi sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Jenis identitas yang terakhir memodifikasi sumber daya.
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

