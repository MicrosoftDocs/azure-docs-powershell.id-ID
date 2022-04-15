---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/new-azlabserviceslabplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesLabPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/New-AzLabServicesLabPlan.md
ms.openlocfilehash: bb01bfbb5972c78955eaf1958fd264d8f9e455bd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142319657"
---
# New-AzLabServicesLabPlan

## SYNOPSIS
Operasi untuk membuat atau memperbarui sumber daya Rencana Lab.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.labservices/new-azlabserviceslabplan) untuk informasi terbaru.

## SYNTAX

```
New-AzLabServicesLabPlan -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-AllowedRegion <String[]>]
 [-DefaultAutoShutdownProfileDisconnectDelay <TimeSpan>] [-DefaultAutoShutdownProfileIdleDelay <TimeSpan>]
 [-DefaultAutoShutdownProfileNoConnectDelay <TimeSpan>]
 [-DefaultAutoShutdownProfileShutdownOnDisconnect <EnableState>]
 [-DefaultAutoShutdownProfileShutdownOnIdle <ShutdownOnIdleMode>]
 [-DefaultAutoShutdownProfileShutdownWhenNotConnected <EnableState>]
 [-DefaultConnectionProfileClientRdpAccess <ConnectionType>]
 [-DefaultConnectionProfileClientSshAccess <ConnectionType>]
 [-DefaultConnectionProfileWebRdpAccess <ConnectionType>]
 [-DefaultConnectionProfileWebSshAccess <ConnectionType>] [-DefaultNetworkProfileSubnetId <String>]
 [-LinkedLmsInstance <String>] [-SharedGalleryId <String>] [-SupportInfoEmail <String>]
 [-SupportInfoInstruction <String>] [-SupportInfoPhone <String>] [-SupportInfoUrl <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat atau memperbarui sumber daya Rencana Lab.

## EXAMPLES

### Contoh 1: Buat paket Lab baru.
```powershell
PS C:\> New-AzLabServicesLabPlan `
    -LabPlanName "testplan" `
    -ResourceGroupName "Group Name" `
    -Location "westus2" `
    -AllowedRegion @('westus2', 'eastus2') `
    -DefaultAutoShutdownProfileShutdownOnDisconnect Disabled `
    -DefaultAutoShutdownProfileShutdownOnIdle None `
    -DefaultAutoShutdownProfileShutdownWhenNotConnected Disabled `
    -DefaultConnectionProfileClientRdpAccess Public `
    -DefaultConnectionProfileClientSshAccess None `
    -SupportInfoEmail 'test@contoso.com' `
    -SupportInfoInstruction 'test information' `
    -SupportInfoPhone '123-456-7890' `
    -SupportInfoUrl 'https:\\test.com' `
    -DefaultConnectionProfileWebRdpAccess None `
    -DefaultConnectionProfileWebSshAccess None

Location Name
-------- ----
westus2  testplan
```

Buat rencana lab.

## PARAMETERS

### -AllowedRegion
Kawasan yang diperbolehkan untuk digunakan oleh pembuat lab saat membuat lab menggunakan rencana lab ini.

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

### -DefaultAutoShutdownProfileIdleDelay
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

### -DefaultAutoShutdownProfileNoConnectDelay
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

### -DefaultAutoShutdownProfileShutdownOnDisconnect
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

### -DefaultAutoShutdownProfileShutdownOnIdle
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

### -DefaultAutoShutdownProfileShutdownWhenNotConnected
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

### -DefaultConnectionProfileClientRdpAccess
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

### -DefaultConnectionProfileClientSshAccess
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

### -DefaultConnectionProfileWebRdpAccess
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

### -DefaultConnectionProfileWebSshAccess
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

### -LinkedLmsInstance
Url dasar contoh lms rencana lab ini dapat menautkan daftar nama lab terhadap.

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
Nama rencana lab yang mengidentifikasinya secara unik di dalamnya berisi grup sumber daya.
Digunakan dalam URI sumber daya dan di UI.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LabPlanName

Required: True
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

### -SharedGalleryId
ID sumber daya dari Shared Image Gallery yang dilampirkan ke paket lab ini.
Ketika menyimpan gambar mesin virtual templat lab, gambar itu akan tetap ada di galeri ini.
Gambar bersama dari galeri dapat disediakan untuk digunakan saat membuat laboratorium baru.

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
Type: System.Collections.Hashtable
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ILabPlan

## CATATAN

ALIAS

## RELATED LINKS

