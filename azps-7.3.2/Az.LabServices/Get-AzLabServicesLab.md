---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/get-azlabserviceslab
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesLab.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesLab.md
ms.openlocfilehash: 4bcef8e5513718e81a69ae2b25712a919ca51d8a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142887868"
---
# Get-AzLabServicesLab

## SYNOPSIS
API untuk mendapatkan lab.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.labservices/get-azlabserviceslab) untuk informasi terbaru.

## SYNTAX

### ListBySubscription (Default)
```
Get-AzLabServicesLab [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### LabPlan
```
Get-AzLabServicesLab -LabPlan <LabPlan> [-Name <String>] [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ListByLabName
```
Get-AzLabServicesLab -Name <String> [-SubscriptionId <String[]>] [-ResourceGroupName <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListByResourceGroup
```
Get-AzLabServicesLab -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### ResourceId
```
Get-AzLabServicesLab -ResourceId <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
API untuk mendapatkan lab.

## EXAMPLES

### Contoh 1: Dapatkan semua lab
```powershell
PS C:\> Get-AzLab

Location      Name                                               Type
--------      ----                                               ----
westus2       Lab1                                               Microsoft.LabServices/labs
westus2       Lab2                                               Microsoft.LabServices/labs
westus2       Lab3                                               Microsoft.LabServices/labs
westus2       Lab4                                               Microsoft.LabServices/labs
```

Mengembalikan semua lab untuk langganan saat ini.

### Contoh 2: Dapatkan lab tertentu
```powershell
PS C:\> Get-AzLab -ResourceGroupName 'yourgroupname' -Name 'yourlabname'

Location      Name                                               Type
--------      ----                                               ----
westus2       yourlabName                                        Microsoft.LabServices/labs
```

Dapatkan lab tertentu menggunakan nama grup sumber daya dan nama lab.

### Contoh 3: Membuat semua lab dengan rencana lab
```powershell
PS C:\> $plan = Get-AzLabPlan -LabPlanName 'lab plan name'
PS C:\> $plan | Get-AzLab -Name 'lab name'

Location      Name                                               Type
--------      ----                                               ----
westus2       lab Name                                        Microsoft.LabServices/labs
```

Dapatkan laboratorium tertentu dalam rencana lab menggunakan objek rencana lab dan nama laboratorium.

### Contoh 4: Dapatkan lab menggunakan wildcard dalam nama lab.
```powershell
PS C:\> Get-AzLab -ResourceGroupName 'group name' -Name '*lab name'

Location      Name                                               Type
--------      ----                                               ----
westus2       yourlab Name                                        Microsoft.LabServices/labs
westus2       anotherlab Name                                     Microsoft.LabServices/labs
```

Menggunakan parameter Nama dan wildcard semua lab dalam grup sumber daya seperti nama yang dikembalikan.

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

### -Nama


```yaml
Type: System.String
Parameter Sets: LabPlan, ListByLabName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResourceGroupName


```yaml
Type: System.String
Parameter Sets: ListByLabName, ListByResourceGroup
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
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ILab

## NOTES

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

