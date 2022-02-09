---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/get-azlabservicesuservm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesUserVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesUserVM.md
ms.openlocfilehash: 70a45115d69c43df5f8bcb152b1b15048b70667a
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138314812"
---
# Get-AzLabServicesUserVM

## SYNOPSIS
API untuk mendapatkan vm yang ditetapkan bagi pengguna.

## SYNTAX

### ResourceId (Default)
```
Get-AzLabServicesUserVM -ResourceId <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzLabServicesUserVM -Email <String> -LabName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Lab
```
Get-AzLabServicesUserVM -Email <String> -Lab <Lab> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Pengguna
```
Get-AzLabServicesUserVM -User <User> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
API untuk mendapatkan vm yang ditetapkan bagi pengguna.

## EXAMPLES

### Contoh 1: Dapatkan Mesin virtual ditetapkan untuk pengguna tertentu.
```powershell
PS C:\> Get-AzLabServicesUserVM -ResourceGroupName "Group Name" -LabName "Lab Name" -Email 'user@contoso.com'

Name
----
0
```

Mengembalikan mesin tertentu yang ditetapkan ke pengguna dalam lab.

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

### -Email


```yaml
Type: System.String
Parameter Sets: Get, Lab
Aliases:

Required: True
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -LabName


```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName


```yaml
Type: System.String
Parameter Sets: Get
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

### -Pengguna
Untuk membuat, lihat bagian CATATAN untuk properti USER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User
Parameter Sets: User
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IVirtualMachine

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LAB <Lab>: 
  - `Location <String>`: Lokasi geo-lokasi tempat sumber daya berada
  - `[AdditionalCapabilityInstallGpuDriver <EnableState?>]`: Benderai untuk driver GPU khusus yang telah diinstal sebelumnya.
  - `[AdminUserPassword <String>]`: Kata sandi untuk pengguna. Ini diperlukan untuk TemplateVM createOption.
  - `[AdminUserUsername <String>]`: Nama pengguna yang digunakan saat masuk ke LAB VM.
  - `[AutoShutdownProfileDisconnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan setelah pengguna memutuskan sambungan jika perilaku ini diaktifkan.
  - `[AutoShutdownProfileIdleDelay <TimeSpan?>]`: Jumlah waktu VM akan diam sebelum terjadinya penutupan jika perilaku ini diaktifkan.
  - `[AutoShutdownProfileNoConnectDelay <TimeSpan?>]`: Jumlah waktu VM akan tetap berjalan sebelum penutupan jika tidak ada koneksi yang dilakukan dan perilaku ini diaktifkan.
  - `[AutoShutdownProfileShutdownOnDisconnect <EnableState?>]`: Apakah penutupan saat pemutusan terputus diaktifkan
  - `[AutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode?>]`: Baik saat vm akan terjadi penutupan jika vm telah diam selama suatu waktu.
  - `[AutoShutdownProfileShutdownWhenNotConnected <EnableState?>]`: Baik saat vm akan terjadi penutupan apabila belum tersambung setelah beberapa waktu.
  - `[ConnectionProfileClientRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.
  - `[ConnectionProfileClientSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Klien melalui LYNC.
  - `[ConnectionProfileWebRdpAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.
  - `[ConnectionProfileWebSshAccess <ConnectionType?>]`: Tingkat akses yang diaktifkan untuk Akses Web melalui MSDN.
  - `[Description <String>]`: Deskripsi lab.
  - `[ImageReferenceId <String>]`: ID sumber daya gambar
  - `[ImageReferenceOffer <String>]`: Penawaran gambar jika ada.
  - `[ImageReferencePublisher <String>]`: Penerbit gambar
  - `[ImageReferenceSku <String>]`: SKU gambar
  - `[ImageReferenceVersion <String>]`: Versi gambar yang ditentukan pada saat pembuatan.
  - `[NetworkProfileLoadBalancerId <String>]`: Id sumber daya penyeimbang muat eksternal
  - `[NetworkProfilePublicIPId <String>]`: Id sumber daya IP publik eksternal
  - `[NetworkProfileSubnetId <String>]`: Id sumber daya subnet eksternal
  - `[NonAdminUserPassword <String>]`: Kata sandi untuk pengguna. Ini diperlukan untuk TemplateVM createOption.
  - `[NonAdminUserUsername <String>]`: Nama pengguna yang digunakan saat masuk ke LAB VM.
  - `[PlanId <String>]`: ID rencana lab. Digunakan selama pembuatan sumber daya untuk menyediakan default dan bertindak sebagai wadah izin saat membuat lab melalui labs.azure.com. Mengatur labPlanId di lab yang sudah ada menyediakan organisasi..
  - `[RosterProfileActiveDirectoryGroupId <String>]`: AAD pertama ID tempat daftar lab terisi. Setelah kumpulan ini mengaktifkan AAD mode sinkronisasi.
  - `[RosterProfileLmsInstance <String>]`: URI dasar yang mengidentifikasi contoh lms.
  - `[RosterProfileLtiClientId <String>]`: Id unik alat layanan lab azure dalam lms.
  - `[RosterProfileLtiContextId <String>]`: Pengidentifikasi konteks unik untuk lab dalam lms.
  - `[RosterProfileLtiRosterEndpoint <String>]`: Uri nama dan titik akhir layanan peran pada lms untuk kelas yang dilampirkan ke lab ini.
  - `[SecurityProfileOpenAccess <EnableState?>]`: Apakah pengguna atau hanya pengguna tertentu yang dapat mendaftar ke sebuah lab.
  - `[SkuCapacity <Int32?>]`: Jika SKU mendukung skala keluar/masuk, bilangan bulat kapasitas akan disertakan. Jika skala/in tidak dimungkinkan untuk sumber daya, hal ini mungkin dihilangkan.
  - `[SkuFamily <String>]`: Jika layanan memiliki beberapa generasi perangkat keras, untuk SKU yang sama, perangkat tersebut dapat diambil di sini.
  - `[SkuName <String>]`: Nama SKU. Misalnya - P3. Kode ini biasanya adalah kode huruf+angka
  - `[SkuSize <String>]`: Ukuran SKU. Jika bidang nama merupakan kombinasi tingkatan dan beberapa nilai lain, ini akan menjadi kode mandiri. 
  - `[SkuTier <SkuTier?>]`: Bidang ini diperlukan untuk diterapkan oleh Penyedia Sumber Daya jika layanan memiliki lebih dari satu tingkatan, tetapi tidak diperlukan pada PUT.
  - `[SystemDataCreatedAt <DateTime?>]`: Timestamp pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Timestamp sumber daya modifikasi terakhir (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir diubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir diubah sumber daya.
  - `[Title <String>]`: Judul lab.
  - `[VirtualMachineProfileCreateOption <CreateOption?>]`: Menunjukkan dari mesin virtual lab apa yang dibuat.
  - `[VirtualMachineProfileUsageQuota <TimeSpan?>]`: Kuota awal disedergapkan untuk setiap pengguna lab. Harus rentang waktu antara 0 dan 9999 jam.
  - `[VirtualMachineProfileUseSharedPassword <EnableState?>]`: Mengaktifkan opsi ini akan menggunakan kata sandi yang sama untuk semua VM pengguna.
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

PENGGUNA <User>: 
  - `Email <String>`: Alamat email pengguna.
  - `[AdditionalUsageQuota <TimeSpan?>]`: Jumlah waktu kuota penggunaan yang akan diberikan pengguna selain kuota penggunaan lab.
  - `[SystemDataCreatedAt <DateTime?>]`: Timestamp pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Timestamp sumber daya modifikasi terakhir (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir diubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir diubah sumber daya.

## RELATED LINKS

