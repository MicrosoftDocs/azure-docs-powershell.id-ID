---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/new-azlabserviceslab
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesLab.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesLab.md
ms.openlocfilehash: 0b3465e9b7a6cc48e0908f63c6c68d4f8b880e68
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140571250"
---
# New-AzLabServicesLab

## SYNOPSIS
Operasi untuk membuat sumber daya lab.

## SYNTAX

```
New-AzLabServicesLab -Name <String> -ResourceGroupName <String> -Location <String> [-SubscriptionId <String>]
 [-AdditionalCapabilityInstallGpuDriver <EnableState>] [-AdminUserPassword <SecureString>]
 [-AdminUserUsername <String>] [-AutoShutdownProfileDisconnectDelay <TimeSpan>]
 [-AutoShutdownProfileIdleDelay <TimeSpan>] [-AutoShutdownProfileNoConnectDelay <TimeSpan>]
 [-AutoShutdownProfileShutdownOnDisconnect <EnableState>]
 [-AutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode>]
 [-AutoShutdownProfileShutdownWhenNotConnected <EnableState>]
 [-ConnectionProfileClientRdpAccess <ConnectionType>] [-ConnectionProfileClientSshAccess <ConnectionType>]
 [-ConnectionProfileWebRdpAccess <ConnectionType>] [-ConnectionProfileWebSshAccess <ConnectionType>]
 [-Description <String>] [-ImageReferenceId <String>] [-ImageReferenceOffer <String>]
 [-ImageReferencePublisher <String>] [-ImageReferenceSku <String>] [-ImageReferenceVersion <String>]
 [-LabPlanId <String>] [-NetworkProfileLoadBalancerId <String>] [-NetworkProfilePublicIPId <String>]
 [-NetworkProfileSubnetId <String>] [-NonAdminUserPassword <SecureString>] [-NonAdminUserUsername <String>]
 [-RosterProfileActiveDirectoryGroupId <String>] [-RosterProfileLmsInstance <String>]
 [-RosterProfileLtiClientId <String>] [-RosterProfileLtiContextId <String>]
 [-RosterProfileLtiRosterEndpoint <String>] [-SecurityProfileOpenAccess <EnableState>] [-SkuCapacity <Int32>]
 [-SkuFamily <String>] [-SkuName <String>] [-SkuSize <String>] [-SkuTier <SkuTier>] [-Tag <Hashtable>]
 [-Title <String>] [-VirtualMachineProfileCreateOption <CreateOption>]
 [-VirtualMachineProfileUsageQuota <TimeSpan>] [-VirtualMachineProfileUseSharedPassword <EnableState>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat sumber daya lab.

## EXAMPLES

### Contoh 1: Buat lab baru.
```powershell
PS C:\>  New-AzLabServicesLab `
        -Name "NewLab" `
        -ResourceGroupName $ENV:ResourceGroupName `
        -Location $ENV:Location `
        -AdditionalCapabilityInstallGpuDriver Disabled `
        -AdminUserPassword "PlaceholderPassword" `
        -AdminUserUsername "PlaceholderAccountName" `
        -AutoShutdownProfileShutdownOnDisconnect Disabled `
        -AutoShutdownProfileShutdownOnIdle None `
        -AutoShutdownProfileShutdownWhenNotConnected Disabled `
        -ConnectionProfileClientRdpAccess Public `
        -ConnectionProfileClientSshAccess None `
        -ConnectionProfileWebRdpAccess None `
        -ConnectionProfileWebSshAccess None `
        -Description "New lab description" `
        -ImageReferenceOffer "Windows-10" `
        -ImageReferencePublisher "MicrosoftWindowsDesktop" `
        -ImageReferenceSku "20h2-pro" `
        -ImageReferenceVersion "latest" `
        -SecurityProfileOpenAccess Disabled `
        -SkuCapacity 3 `
        -SkuName "Standard" `
        -Title $ENV:NewLabName `
        -VirtualMachineProfileCreateOption "TemplateVM" `
        -VirtualMachineProfileUseSharedPassword Enabled

Location Name
-------- ----
westus2  NewLab
```

Membuat Lab baru.

## PARAMETERS

### -AdditionalCapabilityInstallGpuDriver
Benderai untuk driver GPU khusus yang telah diinstal sebelumnya.

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

### -AdminUserPassword
Kata sandi untuk pengguna tersebut.
Ini diperlukan untuk TemplateVM createOption.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminUserUsername
Nama pengguna untuk digunakan saat masuk ke VM lab.

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

### -AutoShutdownProfileDisconnectDelay
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

### -AutoShutdownProfileIdleDelay
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

### -AutoShutdownProfileNoConnectDelay
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

### -AutoShutdownProfileShutdownOnDisconnect
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

### -AutoShutdownProfileShutdownOnIdle
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

### -AutoShutdownProfileShutdownWhenNotConnected
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

### -ConnectionProfileClientRdpAccess
Tingkat akses yang diaktifkan untuk Akses Klien melalui RDP.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionProfileClientSshAccess
Tingkat akses yang diaktifkan untuk Akses Klien melalui LYNC.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionProfileWebRdpAccess
Tingkat akses yang diaktifkan untuk Akses Web melalui RDP.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionProfileWebSshAccess
Tingkat akses yang diaktifkan untuk Akses Web melalui BLUETOOTH.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.ConnectionType
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

### -Deskripsi
Deskripsi lab.

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

### -ImageReferenceId
ID sumber daya gambar

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

### -ImageReferenceOffer
Penawaran gambar jika ada.

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

### -ImageReferencePublisher
Penerbit gambar

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

### -ImageReferenceSku
SKU gambar

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

### -ImageReferenceVersion
Versi gambar yang ditentukan pada saat pembuatan.

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

### -LabPlanId
ID rencana lab.
Digunakan selama pembuatan sumber daya untuk menyediakan default dan bertindak sebagai wadah izin saat membuat lab melalui labs.azure.com.
Mengatur labPlanId di lab yang sudah ada menyediakan organisasi..

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

### -Lokasi
Lokasi geo-location di mana sumber daya berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama lab yang secara unik mengidentifikasinya di dalam berisi akun lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LabName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkProfileLoadBalancerId
Id sumber daya penyeimbang muat eksternal

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

### -NetworkProfilePublicIPId
Id sumber daya IP publik eksternal

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

### -NetworkProfileSubnetId
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

### -NonAdminUserPassword
Kata sandi untuk pengguna tersebut.
Ini diperlukan untuk TemplateVM createOption.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonAdminUserUsername
Nama pengguna untuk digunakan saat masuk ke VM lab.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RosterProfileActiveDirectoryGroupId
Hasil AAD id grup tempat daftar lab terisi.
Setelah kumpulan ini mengaktifkan AAD mode sinkronisasi.

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

### -RosterProfileLmsInstance
URI dasar yang mengidentifikasi contoh lms.

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

### -RosterProfileLtiClientId
Id unik alat layanan lab azure dalam lms.

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

### -RosterProfileLtiContextId
Pengidentifikasi konteks yang unik untuk lab dalam lms.

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

### -RosterProfileLtiRosterEndpoint
Uri nama dan titik akhir layanan peran pada lms untuk kelas yang dilampirkan ke lab ini.

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

### -SecurityProfileOpenAccess
Apakah pengguna atau hanya pengguna tertentu yang dapat mendaftar ke sebuah lab.

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

### -SkuCapacity
Jika SKU mendukung skala keluar/masuk maka bilangan bulat kapasitas akan disertakan.
Jika skala/in tidak dimungkinkan untuk sumber daya, hal ini mungkin dihilangkan.

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

### -SkuFamily
Jika layanan memiliki beberapa generasi perangkat keras, untuk SKU yang sama, fitur tersebut dapat diambil di sini.

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

### -SkuName
Nama SKU.
Misalnya - P3.
Kode ini biasanya adalah kode huruf+angka

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

### -SkuSize
Ukuran SKU.
Jika bidang nama merupakan kombinasi tingkatan dan beberapa nilai lain, ini akan menjadi kode mandiri.

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

### -SkuTier
Bidang ini harus diterapkan oleh Penyedia Sumber Daya jika layanan memiliki lebih dari satu tingkatan, tetapi tidak diperlukan pada PUT.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.SkuTier
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

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Judul
Judul lab.

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

### -VirtualMachineProfileCreateOption
Menunjukkan mesin virtual lab dari mana mesin virtual dibuat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Support.CreateOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineProfileUsageQuota
Kuota awal disotot ke setiap pengguna lab.
Harus rentang waktu antara 0 dan 9999 jam.

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

### -VirtualMachineProfileUseSharedPassword
Mengaktifkan opsi ini akan menggunakan kata sandi yang sama untuk semua VM pengguna.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ILab

## CATATAN

ALIAS

## RELATED LINKS

