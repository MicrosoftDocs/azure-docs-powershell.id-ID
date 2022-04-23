---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/new-azlabserviceslab
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesLab.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesLab.md
ms.openlocfilehash: 0f5e04ab5b9ab633fe1e4777b806add167b9b12f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143226395"
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

### Contoh 1: Membuat lab baru.
```powershell
New-AzLabServicesLab `
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
```

```output
Location Name
-------- ----
westus2  NewLab
```

Membuat Lab baru.

## PARAMETERS

### -AdditionalCapabilityInstallGpuDriver
Tandai ke driver GPU khusus pra-instal.

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
Kata sandi untuk pengguna.
Ini diperlukan untuk CreateOption TemplateVM.

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
Nama pengguna yang digunakan saat masuk ke VM lab.

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
Jumlah waktu VM akan tetap berjalan setelah pengguna terputus jika perilaku ini diaktifkan.

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
Jumlah waktu VM akan diam sebelum dimatikan jika perilaku ini diaktifkan.

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
Jumlah waktu VM akan tetap berjalan sebelum mati jika tidak ada koneksi yang dibuat dan perilaku ini diaktifkan.

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
Apakah mematikan sambungan saat diputus diaktifkan

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
Apakah VM akan dimatikan ketika diam selama periode waktu tertentu.

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
Apakah VM akan dimatikan ketika belum tersambung setelah periode waktu tertentu.

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
Tingkat akses yang diaktifkan untuk Akses Klien melalui SSH.

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
Tingkat akses yang diaktifkan untuk Akses Web melalui SSH.

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
Penjabaran dari lab.

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

### -ImageReferencesku
Gambar SKU

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
Versi gambar yang ditentukan pada pembuatan.

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
Lokasi geografis tempat sumber daya berada

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
Nama lab yang mengidentifikasinya secara unik di dalamnya berisi akun lab.
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
Id sumber daya penyeimbang beban eksternal

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
Kata sandi untuk pengguna.
Ini diperlukan untuk CreateOption TemplateVM.

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
Nama pengguna yang digunakan saat masuk ke VM lab.

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
Jalankan perintah secara asinkron

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
Nama ini tidak peka huruf besar kecil.

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
ID grup AAD tempat daftar lab ini diisi.
Mengatur ini mengaktifkan mode sinkronisasi AAD.

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
Basis URI yang mengidentifikasi instans IM.

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
Id unik dari alat layanan lab azure di lms.

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
Pengidentifikasi konteks yang unik untuk lab di lms.

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
Uri dari nama dan peran titik akhir layanan pada lms untuk kelas yang melekat pada lab ini.

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

### -SecurityProfileOpenAccesss
Apakah setiap pengguna atau hanya pengguna tertentu yang dapat mendaftar ke lab.

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
Jika SKU mendukung penskalaan keluar/masuk maka bilangan bulat kapasitas harus disertakan.
Jika skala keluar/masuk tidak dimungkinkan untuk sumber daya ini mungkin dihilangkan.

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
Jika layanan memiliki generasi perangkat keras yang berbeda, untuk SKU yang sama, maka yang dapat ditangkap di sini.

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
Bekas - P3.
Biasanya berupa kode huruf+angka

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

### -Skusize
Ukuran SKU.
Ketika bidang nama adalah kombinasi tingkat dan beberapa nilai lainnya, ini akan menjadi kode mandiri.

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
Bidang ini diperlukan untuk diterapkan oleh Penyedia Sumber Daya jika layanan memiliki lebih dari satu tingkat, tetapi tidak diperlukan pada PUT.

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
Judul laboratorium.

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
Menunjukkan dari mesin virtual lab mana yang dibuat.

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
Kuota awal yang dialokasikan untuk setiap pengguna lab.
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ILab

## NOTES

ALIAS

## RELATED LINKS

