---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: CE32F620-8DB2-4004-8012-F1C4AA235B60
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmssconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmssConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmssConfig.md
ms.openlocfilehash: 72ad8383f9c24158aee3d00ba8ab6a2583c0bf60
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141913755"
---
# New-AzVmssConfig

## SYNOPSIS
Membuat objek konfigurasi VMSS.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvmssconfig) untuk informasi terbaru.

## SYNTAX

### DefaultParameterSet (Default)
```
New-AzVmssConfig [[-Overprovision] <Boolean>] [[-Location] <String>] [-EdgeZone <String>] [[-Tag] <Hashtable>]
 [[-SkuName] <String>] [[-SkuTier] <String>] [[-SkuCapacity] <Int32>] [[-UpgradePolicyMode] <UpgradeMode>]
 [[-OsProfile] <VirtualMachineScaleSetOSProfile>] [[-StorageProfile] <VirtualMachineScaleSetStorageProfile>]
 [[-NetworkInterfaceConfiguration] <VirtualMachineScaleSetNetworkConfiguration[]>]
 [[-Extension] <PSVirtualMachineScaleSetExtension[]>] [-SkipExtensionsOnOverprovisionedVMs]
 [-SinglePlacementGroup <Boolean>] [-ZoneBalance] [-PlatformFaultDomainCount <Int32>] [-Zone <String[]>]
 [-PlanName <String>] [-PlanPublisher <String>] [-PlanProduct <String>] [-PlanPromotionCode <String>]
 [-RollingUpgradePolicy <RollingUpgradePolicy>] [-EnableAutomaticRepair] [-AutomaticRepairGracePeriod <String>]
 [-AutoOSUpgrade] [-DisableAutoRollback <Boolean>] [-EnableUltraSSD] [-HealthProbeId <String>]
 [-BootDiagnostic <BootDiagnostics>] [-LicenseType <String>] [-Priority <String>] [-EnableSpotRestore]
 [-SpotRestoreTimeout <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-TerminateScheduledEvents]
 [-TerminateScheduledEventNotBeforeTimeoutInMinutes <Int32>] [-ProximityPlacementGroupId <String>]
 [-ScaleInPolicy <String[]>] [-EncryptionAtHost] [-OrchestrationMode <String>]
 [-CapacityReservationGroupId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ExplicitIdentityParameterSet
```
New-AzVmssConfig [[-Overprovision] <Boolean>] [[-Location] <String>] [-EdgeZone <String>] [[-Tag] <Hashtable>]
 [[-SkuName] <String>] [[-SkuTier] <String>] [[-SkuCapacity] <Int32>] [[-UpgradePolicyMode] <UpgradeMode>]
 [[-OsProfile] <VirtualMachineScaleSetOSProfile>] [[-StorageProfile] <VirtualMachineScaleSetStorageProfile>]
 [[-NetworkInterfaceConfiguration] <VirtualMachineScaleSetNetworkConfiguration[]>]
 [[-Extension] <PSVirtualMachineScaleSetExtension[]>] [-SkipExtensionsOnOverprovisionedVMs]
 [-SinglePlacementGroup <Boolean>] [-ZoneBalance] [-PlatformFaultDomainCount <Int32>] [-Zone <String[]>]
 [-PlanName <String>] [-PlanPublisher <String>] [-PlanProduct <String>] [-PlanPromotionCode <String>]
 [-RollingUpgradePolicy <RollingUpgradePolicy>] [-EnableAutomaticRepair] [-AutomaticRepairGracePeriod <String>]
 [-AutoOSUpgrade] [-DisableAutoRollback <Boolean>] [-EnableUltraSSD] [-HealthProbeId <String>]
 [-BootDiagnostic <BootDiagnostics>] [-LicenseType <String>] [-Priority <String>] [-EnableSpotRestore]
 [-SpotRestoreTimeout <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-TerminateScheduledEvents]
 [-TerminateScheduledEventNotBeforeTimeoutInMinutes <Int32>] [-ProximityPlacementGroupId <String>]
 [-ScaleInPolicy <String[]>] -IdentityType <ResourceIdentityType> [-IdentityId <String[]>] [-EncryptionAtHost]
 [-OrchestrationMode <String>] [-CapacityReservationGroupId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVmssConfig** membuat objek Virtual Manager Scale Set (VMSS) lokal yang dapat dikonfigurasi. Cmdlet lain diperlukan untuk mengonfigurasi objek VMSS. Cmdlet ini adalah:
- Set-AzVmssOsProfile
- Set-AzVmssStorageProfile
- Add-AzVmssNetworkInterfaceConfiguration
- Add-AzVmssExtension

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi VMSS
```powershell
PS C:\> $VMSS = New-AzVmssConfig -Location $Loc -SkuCapacity 2 -SkuName "Standard_A0" -UpgradePolicyMode "Automatic" -NetworkInterfaceConfiguration $NetCfg `
            | Add-AzVmssNetworkInterfaceConfiguration -Name "Test" -Primary $True -IPConfiguration $IPCfg `
            | Set-AzVmssOSProfile -ComputerNamePrefix "Test" -AdminUsername $adminUsername -AdminPassword $AdminPassword `
            | Set-AzVmssStorageProfile -Name "Test" -OsDiskCreateOption "FromImage" -OsDiskCaching "None" `
            -ImageReferenceOffer $ImgRef.Offer -ImageReferenceSku $ImgRef.Skus -ImageReferenceVersion $ImgRef.Version `
            -ImageReferencePublisher $ImgRef.PublisherName -VhdContainer $VHDContainer `
            | Add-AzVmssAdditionalUnattendContent -ComponentName  $AUCComponentName -Content  $AUCContent -PassName  $AUCPassName -SettingName  $AUCSetting `
            | Remove-AzVmssAdditionalUnattendContent -ComponentName  $AUCComponentName;

New-AzVmss -ResourceGroupName $RGName -Name $VMSSName -VirtualMachineScaleSet $VMSS;
```

Contoh ini membuat objek konfigurasi VMSS. Perintah pertama menggunakan cmdlet **New-AzVmsConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel bernama $VMSS. Perintah kedua menggunakan cmdlet **New-AzVmss** untuk membuat VMSS yang menggunakan objek konfigurasi VMSS yang dibuat dalam perintah pertama.

### Contoh 2

Membuat objek konfigurasi VMSS. (autogenerasi)

```powershell
<!-- Aladdin Generated Example --> 
New-AzVmssConfig -Location <String> -Overprovision $false -SkuCapacity 2 -SkuName 'Standard_A0' -Tag 'Sql' -UpgradePolicyMode Automatic
```

### Contoh 3

Membuat objek konfigurasi VMSS. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
New-AzVmssConfig -Location <String> -SkuCapacity 2 -SkuName 'Standard_A0' -UpgradePolicyMode Automatic -IdentityType SystemAssigned
```

## PARAMETERS

### -AutomaticRepairGracePeriod
Jumlah waktu perbaikan otomatis ditangguhkan karena perubahan status pada VM. Waktu tenggang dimulai setelah perubahan negara telah selesai. Ini membantu menghindari perbaikan prematur atau tidak disengaja. Durasi waktu harus ditentukan dalam format ISO 8601. Masa tenggang minimum yang diperbolehkan adalah 30 menit (PT30M), yang juga merupakan nilai default. Masa tenggang maksimum yang diizinkan adalah 90 menit (PT90M).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoOSUpgrade
Mengatur apakah peningkatan OS harus diterapkan secara otomatis ke instance kumpulan skala secara bergulir saat versi gambar yang lebih baru tersedia.

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

### -BootDiagnostic
Menentukan profil diagnostik boot kumpulan skala mesin virtual.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.BootDiagnostics
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CapacityReservationGroupId
Id grup reservasi kapasitas yang digunakan untuk mengalokasikan.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoRollback
Menonaktifkan Pembatalan Otomatis untuk Kebijakan Pemutakhiran OS Otomatis

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EdgeZone
Mengatur nama zona tepi. Jika diatur, kueri akan dirutekan ke zona tepi yang ditentukan, bukan kawasan utama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableAutomaticRepair
Mengaktifkan perbaikan otomatis pada kumpulan skala mesin virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableSpotRestore
Mengaktifkan fitur Spot-Try-Restore di mana instans SPOT VMSS yang diusir akan dicoba untuk dipulihkan secara oportunistik berdasarkan ketersediaan kapasitas dan batasan harga

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableUltrassd
Memungkinkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan tipe akun penyimpanan UltraSSD_LRS pada kumpulan skala mesin virtual.
Disk terkelola dengan tipe akun penyimpanan UltraSSD_LRS dapat ditambahkan ke VMSS hanya jika properti ini diaktifkan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionAtHost
Parameter ini akan mengaktifkan enkripsi untuk semua disk termasuk disk Sumber Daya/Temp di host itu sendiri. Default: Enkripsi di host akan dinonaktifkan kecuali properti ini diatur ke true untuk sumber daya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EvictionPolicy
Menentukan kebijakan penggulangan untuk mesin virtual dalam kumpulan skala.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ekstensi
Menentukan objek informasi ekstensi untuk VMSS. Anda dapat menggunakan cmdlet **Add-AzVmssExtension** untuk menambahkan objek ini.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetExtension[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthProbeId
Menentukan ID probe load balancer yang digunakan untuk menentukan kesehatan instans dalam kumpulan skala mesin virtual.
HealthProbeId berupa '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/probes/{probeName}'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityId
Menentukan daftar identitas pengguna yang terkait dengan kumpulan skala mesin virtual.
Referensi identitas pengguna akan berupa id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

```yaml
Type: System.String[]
Parameter Sets: ExplicitIdentityParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Menentukan tipe identitas yang digunakan untuk kumpulan skala mesin virtual.
Tipe 'SystemAssignedUserAssigned' mencakup identitas yang dibuat secara implisit dan sekumpulan identitas yang ditetapkan pengguna.
Tipe 'Tidak Ada' akan menghapus identitas apa pun dari kumpulan skala mesin virtual.
Nilai yang dapat diterima untuk parameter ini adalah:
- SystemAssigned
- UserAssigned
- SystemAssignedUserAssigned
- Tidak

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.ResourceIdentityType]
Parameter Sets: ExplicitIdentityParameterSet
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssignedUserAssigned, None

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LicenseType
Tentukan tipe lisensi, yang untuk membawa skenario lisensi Anda sendiri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi Azure tempat VMSS dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxPrice
Menentukan harga maksimum yang ingin Anda bayar untuk VM/VMSS Spot. Harga ini adalah dalam Dolar AS. Harga ini akan dibandingkan dengan harga Spot saat ini untuk ukuran VM. Juga, harga dibandingkan pada saat membuat / memperbarui Spot VM / VMSS dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga Spot saat ini. MaxPrice juga akan digunakan untuk meningkatkan VM/VMSS Spot jika harga Spot saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang memungkinkan adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0.01538.  -1 menunjukkan bahwa VM/VMSS Spot tidak boleh diusir karena alasan harga. Selain itu, harga maks default adalah -1 jika tidak disediakan oleh Anda.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkInterfaceConfiguration
Menentukan objek profil jaringan yang berisi properti jaringan untuk konfigurasi VMSS.
Anda dapat menggunakan cmdlet **Add-AzVmssNetworkInterfaceConfiguration** untuk menambahkan objek ini.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetNetworkConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OrchestrationMode
Menentukan mode orkestrasi untuk kumpulan skala mesin virtual. Nilai yang memungkinkan: Seragam, Fleksibel

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OsProfile
Menentukan objek profil sistem operasi yang berisi properti sistem operasi untuk konfigurasi VMSS.
Anda dapat menggunakan cmdlet **Set-AzVmssOsProfile** untuk mengatur objek ini.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetOSProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Overprovision
Menunjukkan apakah cmdlet melebihi provisi VMSS.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlanName
Menentukan nama rencana.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlanProduct
Menentukan produk paket.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlanPromotionCode
Menentukan kode promosi rencana.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlanPublisher
Menentukan penerbit rencana.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlatformFaultDomainCount
Jumlah Domain Kesalahan untuk setiap grup penempatan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prioritas
Prioritas untuk machien virtual dalam kumpulan skala.  Hanya nilai yang didukung adalah 'Reguler', 'Titik' dan 'Rendah'.
'Reguler' adalah untuk mesin virtual reguler.
'Spot' adalah untuk mesin virtual spot.
'Rendah' juga untuk mesin virtual spot tetapi digantikan dengan 'Spot'. Silakan gunakan 'Spot' dan bukan 'Rendah'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProximityPlacementGroupId
Id sumber daya dari Grup Penempatan Kedekatan untuk digunakan dengan kumpulan skala ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RollingUpgradePolicy
Menentukan kebijakan pemutakhiran bergulir.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.RollingUpgradePolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleInPolicy
Aturan yang harus diikuti ketika penskalakan-dalam kumpulan skala mesin virtual.  Nilai yang memungkinkan adalah: 'Default', 'OldestVM' dan 'NewestVM'.  'Default' ketika kumpulan skala mesin virtual diskalakan, kumpulan skala akan lebih dulu diseimbangkan di seluruh zona jika kumpulan skala zona.  Kemudian, ini akan seimbang di seluruh Domain Kesalahan sejauh mungkin.  Di dalam setiap Domain Kesalahan, mesin virtual yang dipilih untuk penghapusan akan menjadi yang terbaru yang tidak dilindungi dari scale-in.  'OldestVM' ketika kumpulan skala mesin virtual sedang diskalakan, mesin virtual tertua yang tidak dilindungi dari scale-in akan dipilih untuk penghapusan.  Untuk kumpulan skala mesin virtual zonal, kumpulan skala akan lebih dulu seimbang di seluruh zona.  Dalam setiap zona, mesin virtual tertua yang tidak dilindungi akan dipilih untuk penghapusan.  'NewestVM' ketika kumpulan skala mesin virtual sedang diskalakan, mesin virtual terbaru yang tidak dilindungi dari scale-in akan dipilih untuk penghapusan.  Untuk kumpulan skala mesin virtual zonal, kumpulan skala akan lebih dulu seimbang di seluruh zona.  Di dalam setiap zona, mesin virtual terbaru yang tidak dilindungi akan dipilih untuk penghapusan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SinglePlacementGroup
Menentukan grup penempatan tunggal.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipExtensionsOnOverprovisionedVMs
Menentukan bahwa ekstensi tidak berjalan pada VM ekstra overprovisioned.

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

### -SkuCapacity
Menentukan jumlah instans dalam VMSS.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuName
Menentukan ukuran semua contoh VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountType

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuTier
Menentukan tingkat VMSS. Nilai yang dapat diterima untuk parameter ini adalah:
- Standar
- Dasar

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SpotRestoreTimeout
Menentukan nilai batas waktu yang dinyatakan sebagai durasi waktu ISO 8601 setelah itu platform tidak akan mencoba memulihkan instans SPOT VMSS

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageProfile
Menentukan objek profil penyimpanan yang berisi properti disk untuk konfigurasi VMSS.
Anda dapat menggunakan cmdlet **Set-AzVmssStorageProfile** untuk mengatur objek ini.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetStorageProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TerminateScheduledEventNotBeforeTimeoutInMinutes
Durasi waktu yang dapat dikonfigurasi (dalam menit) Mesin Virtual yang dihapus harus berpotensi menyetujui Acara Terjadwal Berakhir sebelum acara disetujui otomatis (waktu habis).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TerminateScheduledEvents
Aktifkan acara Terhentikan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UpgradePolicyMode
Menentukan mode pemutakhiran ke mesin virtual dalam kumpulan skala.
Nilai yang dapat diterima untuk parameter ini adalah:
- Otomatis
- Manual

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.UpgradeMode]
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Rolling

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Menentukan daftar zona untuk kumpulan skala mesin virtual.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneBalance
Apakah akan memaksa distribusi Mesin Virtual yang benar-benar bahkan lintas zona x jika terjadi pemadaman zona.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.String

### System.Collections.Hashtable

### System.Int32

### System.Nullable'1[[Microsoft.Azure.Management.Compute.Models.UpgradeMode, Microsoft.Azure.Management.Compute, Version=23.0.0.0, Culture=netral, PublicKeyToken=31bf3856ad364e35]]

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetOSProfile

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetStorageProfile

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetNetworkConfiguration[]

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetExtension[]

### System.String[]

### Microsoft.Azure.Management.Compute.Models.RollingUpgradePolicy

### System.Management.Automation.SwitchParameter

### Microsoft.Azure.Management.Compute.Models.BootDiagnostics

### System.Nullable'1[[Microsoft.Azure.Management.Compute.Models.ResourceIdentityType, Microsoft.Azure.Management.Compute, Version=23.0.0.0, Culture=netral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS

[Set-AzVmssOsProfile](./Set-AzVmssOsProfile.md)

[Set-AzVmssStorageProfile](./Set-AzVmssStorageProfile.md)

[Add-AzVmssNetworkInterfaceConfiguration](./Add-AzVmssNetworkInterfaceConfiguration.md)

[Add-AzVmssExtension](./Add-AzVmssExtension.md)

[New-AzVmss](./New-AzVmss.md)
