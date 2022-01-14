---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 9EE192A5-4E3F-41ED-A539-8E0A5D5EA4C9
online version: https://docs.microsoft.com/powershell/module/az.compute/update-azvmss
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Update-AzVmss.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Update-AzVmss.md
ms.openlocfilehash: 170d0677ed86887cf63eb84a89302cde5e1ec9f3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "136039618"
---
# Update-AzVmss

## SYNOPSIS
Memperbarui status VMSS.

## SYNTAX

### DefaultParameter (Default)
```
Update-AzVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String>
 [[-VirtualMachineScaleSet] <PSVirtualMachineScaleSet>] [-AutomaticOSUpgrade <Boolean>]
 [-AutomaticRepairGracePeriod <String>] [-BootDiagnosticsEnabled <Boolean>]
 [-BootDiagnosticsStorageUri <String>] [-CustomData <String>] [-DisableAutoRollback <Boolean>]
 [-DisablePasswordAuthentication <Boolean>] [-EnableAutomaticRepair <Boolean>]
 [-EnableAutomaticUpdate <Boolean>] [-ImageReferenceId <String>] [-ImageReferenceOffer <String>]
 [-ImageReferencePublisher <String>] [-ImageReferenceSku <String>] [-ImageReferenceVersion <String>]
 [-ImageUri <String>] [-LicenseType <String>] [-ManagedDiskStorageAccountType <String>]
 [-MaxBatchInstancePercent <Int32>] [-MaxPrice <Double>] [-MaxUnhealthyInstancePercent <Int32>]
 [-MaxUnhealthyUpgradedInstancePercent <Int32>] [-OsDiskCaching <CachingTypes>]
 [-OsDiskWriteAccelerator <Boolean>] [-Overprovision <Boolean>] [-PauseTimeBetweenBatches <String>]
 [-PlanName <String>] [-PlanProduct <String>] [-PlanPromotionCode <String>] [-PlanPublisher <String>]
 [-ProvisionVMAgent <Boolean>] [-ProximityPlacementGroupId <String>] [-ScaleInPolicy <String[]>]
 [-SinglePlacementGroup <Boolean>] [-SkipExtensionsOnOverprovisionedVMs <Boolean>] [-SkuCapacity <Int32>]
 [-SkuName <String>] [-SkuTier <String>] [-Tag <Hashtable>]
 [-TerminateScheduledEventNotBeforeTimeoutInMinutes <Int32>] [-TerminateScheduledEvents <Boolean>]
 [-TimeZone <String>] [-UltraSSDEnabled <Boolean>] [-UpgradePolicyMode <UpgradeMode>]
 [-VhdContainer <String[]>] [-AsJob] [-EncryptionAtHost <Boolean>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ExplicitIdentityParameterSet
```
Update-AzVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String>
 [[-VirtualMachineScaleSet] <PSVirtualMachineScaleSet>] [-AutomaticOSUpgrade <Boolean>]
 [-AutomaticRepairGracePeriod <String>] [-BootDiagnosticsEnabled <Boolean>]
 [-BootDiagnosticsStorageUri <String>] [-CustomData <String>] [-DisableAutoRollback <Boolean>]
 [-DisablePasswordAuthentication <Boolean>] [-EnableAutomaticRepair <Boolean>]
 [-EnableAutomaticUpdate <Boolean>] [-IdentityId <String[]>] -IdentityType <ResourceIdentityType>
 [-ImageReferenceId <String>] [-ImageReferenceOffer <String>] [-ImageReferencePublisher <String>]
 [-ImageReferenceSku <String>] [-ImageReferenceVersion <String>] [-ImageUri <String>] [-LicenseType <String>]
 [-ManagedDiskStorageAccountType <String>] [-MaxBatchInstancePercent <Int32>] [-MaxPrice <Double>]
 [-MaxUnhealthyInstancePercent <Int32>] [-MaxUnhealthyUpgradedInstancePercent <Int32>]
 [-OsDiskCaching <CachingTypes>] [-OsDiskWriteAccelerator <Boolean>] [-Overprovision <Boolean>]
 [-PauseTimeBetweenBatches <String>] [-PlanName <String>] [-PlanProduct <String>] [-PlanPromotionCode <String>]
 [-PlanPublisher <String>] [-ProvisionVMAgent <Boolean>] [-ProximityPlacementGroupId <String>]
 [-ScaleInPolicy <String[]>] [-SinglePlacementGroup <Boolean>] [-SkipExtensionsOnOverprovisionedVMs <Boolean>]
 [-SkuCapacity <Int32>] [-SkuName <String>] [-SkuTier <String>] [-Tag <Hashtable>]
 [-TerminateScheduledEventNotBeforeTimeoutInMinutes <Int32>] [-TerminateScheduledEvents <Boolean>]
 [-TimeZone <String>] [-UltraSSDEnabled <Boolean>] [-UpgradePolicyMode <UpgradeMode>]
 [-VhdContainer <String[]>] [-AsJob] [-EncryptionAtHost <Boolean>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzVmss** memperbarui status Virtual Machine Scale Set (VMSS) ke keadaan objek VMSS lokal.

## EXAMPLES

### Contoh 1: Update the state of a VMSS to the state of a local VMSS object.
```
PS C:\> Update-AzVmss -ResourceGroupName "Group001" -Name "VMSS001" -VirtualMachineScaleSet $LocalVMSS
```

Perintah ini memperbarui status VMSS bernama VMSS001 yang dimiliki oleh grup sumber daya yang bernama Group001 ke keadaan objek VMSS lokal, $LocalVMSS.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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

### -AutomaticOSUpgrade
Mengatur apakah pemutakhiran OS akan secara otomatis diterapkan pada instans kumpulan skala dengan mode berputar ketika versi gambar yang lebih baru telah tersedia.

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

### -AutomaticRepairGracePeriod
Jumlah waktu perbaikan otomatis ditangguhkan karena perubahan status pada VM. Waktu tenggang dimulai setelah perubahan status telah selesai. Ini membantu menghindari perbaikan prematur atau tidak disengaja. Durasi waktu harus ditentukan dalam format ISO 8601. Masa tenggang minimum yang diperbolehkan adalah 30 menit (PT30M), yang juga merupakan nilai default. Masa tenggang maksimum yang diperbolehkan adalah 90 menit (PT90M).

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

### -BootDiagnosticsEnabled
Apakah diagnostik boot harus diaktifkan pada kumpulan skala komputer virtual.

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

### -BootDiagnosticsStorageUri
URI akun penyimpanan yang dapat digunakan untuk menempatkan output konsol dan tangkapan layar.

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

### -CustomData
Menentukan string berkode basis 64 dari data kustom.
Ini dikodekan ke array biner yang disimpan sebagai file pada mesin virtual.
Panjang maksimum array biner adalah 65535 byte. <br>
Untuk menggunakan cloud-init untuk VM, lihat [Menggunakan cloud-init untuk mengustomisasi VM Linux selama pembuatan.](/azure/virtual-machines/linux/tutorial-automate-vm-deployment)

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
Menonaktifkan Rollback Otomatis untuk Kebijakan Pemutakhiran Auto OS

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

### -DisablePasswordAuthentication
Menunjukkan bahwa cmdlet ini menonaktifkan autentikasi kata sandi untuk Linux OS.

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

### -EnableAutomaticRepair
Mengaktifkan atau menonaktifkan perbaikan otomatis pada kumpulan skala mesin virtual.

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

### -EnableAutomaticUpdate
Menunjukkan apakah Windows virtual pada VMSS diaktifkan untuk pembaruan otomatis.

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

### -EncryptionAtHost
Parameter ini bisa digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk kumpulan skala mesin virtual.

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

### -IdentityId
Menentukan daftar identitas pengguna yang terkait dengan kumpulan skala mesin virtual.
Referensi identitas pengguna akan menjadi ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

```yaml
Type: System.String[]
Parameter Sets: ExplicitIdentityParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Menentukan tipe identitas yang digunakan untuk kumpulan skala mesin virtual.
Tipe 'SystemAssignedUserAssigned' menyertakan identitas yang dibuat secara implisit dan kumpulan identitas yang ditetapkan pengguna.
Tipe 'Tidak Ada' akan menghapus identitas apa pun dari kumpulan skala mesin virtual.
Nilai yang dapat diterima untuk parameter ini adalah:
- SystemAssigned
- UserAssigned
- SystemAssignedUserAssigned
- Tidak ada

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.ResourceIdentityType]
Parameter Sets: ExplicitIdentityParameterSet
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssignedUserAssigned, None

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageReferenceId
Menentukan ID referensi gambar.

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
Menentukan tipe penawaran gambar mesin virtual (VMImage).
Untuk mendapatkan penawaran gambar, gunakan cmdlet Get-AzVMImageOffer.

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
Menentukan nama penerbit VMImage.
Untuk mendapatkan penerbit, gunakan cmdlet Get-AzVMImagePublisher.

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
Menentukan VMImage SKU.
Untuk mendapatkan SKU, gunakan cmdlet Get-AzVMImageSku cmdlet.

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
Menentukan versi VMImage.
Untuk menggunakan versi terbaru, tentukan nilai terbaru dan bukan versi tertentu.

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

### -ImageUri
Menentukan URI blob untuk gambar pengguna.
VMSS membuat disk sistem operasi dalam wadah gambar pengguna yang sama.

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

### -LicenseType
Tentukan tipe lisensi, yang akan membuat skenario lisensi Anda sendiri.

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

### -ManagedDiskStorageAccountType
Menentukan tipe akun penyimpanan untuk disk terkelola.
Nilai yang dapat diterima untuk parameter ini adalah:
- StandardLRS
- PremiumLRS

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

### -MaxBatchInstancePercent
Persentase maksimum instans mesin virtual total yang akan dimutakhirkan secara bersamaan dengan pemutakhiran bertahap dalam satu kumpulan.
Karena ini adalah contoh maksimum yang tidak sehat pada kumpulan sebelumnya atau yang akan datang dapat menyebabkan persentase contoh dalam batch berkurang untuk memastikan keandalan yang lebih tinggi.
Jika nilai tidak ditentukan, nilai diatur ke 20.

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

### -MaxPrice
Menentukan harga maksimum yang Anda bersedia untuk membayar VM/VMSS berprioritas rendah. Harga ini dalam Dolar AS. Harga ini akan dibandingkan dengan harga berprioritas rendah saat ini untuk ukuran VM. Selain itu, harga dibandingkan pada saat pembuatan/pembaruan VM/VMSS berprioritas rendah dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga prioritas rendah saat ini. MaxPrice juga akan digunakan untuk membatalkan vm/VMSS prioritas rendah jika harga berprioritas rendah saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang mungkin adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0,01538.  -1 menunjukkan bahwa VM/VMSS berprioritas rendah tidak boleh disederhkan untuk alasan harga. Selain itu, harga maks default adalah -1 jika tidak diberikan oleh Anda.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxUnhealthyInstancePercent
Persentase maksimum instans mesin virtual total dalam kumpulan skala yang dapat secara bersamaan tidak sehat, baik sebagai akibat pemutakhiran, atau dengan ditemukan dalam keadaan tidak sehat oleh pemeriksaan kesehatan mesin virtual sebelum peluncuran peningkatan.
Batasan ini akan dicentang sebelum memulai kumpulan apa pun.
Jika nilai tidak ditentukan, nilai diatur ke 20.

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

### -MaxUnhealthyUpgradedInstancePercent
Persentase maksimum dari mesin virtual yang dimutakhirkan yang dapat ditemukan dalam keadaan tidak sehat.
Pemeriksaan ini akan terjadi setelah setiap kumpulan ditakhirkan.
Jika persentase ini pernah melebihi, pembaruan diluncurkan pada pembaruan terkini.
Jika nilai tidak ditentukan, nilai diatur ke 20.

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

### -OsDiskCaching
Menentukan mode cache dari disk sistem operasi.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- ReadOnly
- ReadWrite Nilai defaultnya adalah ReadWrite.
Jika Anda mengubah nilai cache, cmdlet akan memulai ulang mesin virtual.
Pengaturan ini mempengaruhi konsistensi dan kinerja disk.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.CachingTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OsDiskWriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan di disk OS.

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

### -Overprovision
Menunjukkan apakah cmdlet overprovisions VMSS.

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

### -PauseTimeBetweenBatches
Waktu tunggu antara menyelesaikan pembaruan untuk semua mesin virtual dalam satu kumpulan dan memulai kumpulan berikutnya.
Durasi waktu harus ditentukan dalam format ISO 8601.
Nilai defaultnya adalah 0 detik (PT0S).

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

### -PlanName
Menentukan nama rencana.

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

### -PlanProduct
Menentukan produk paket.

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

### -PlanPromotionCode
Menentukan kode promosi paket.

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

### -PlanPublisher
Menentukan penerbit paket.

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

### -ProvisionVMAgent
Menunjukkan apakah agen mesin virtual harus disediakan pada Windows virtual dalam VMSS.

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

### -ProximityPlacementGroupId
Id sumber daya dari Grup Penempatan Kedekatan untuk digunakan dengan kumpulan skala ini.

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang dimiliki VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleInPolicy
Aturan yang akan diikuti saat skala di dalam kumpulan skala mesin virtual.  Nilai yang memungkinkan adalah: 'Default', 'OldestVM' dan 'NewestVM'.  'Default' ketika kumpulan skala mesin virtual diskalakan, kumpulan skala akan diimbangi terlebih dahulu di seluruh zona jika merupakan kumpulan skala zonal.  Lalu, solusi ini akan menyeimbangkan seluruh Domain Kesalahan sesegera mungkin.  Dalam setiap Domain Kesalahan, komputer virtual yang dipilih untuk penghapusan akan menjadi komputer terbaru yang tidak dilindungi skala masuk.  'OldestVM' saat kumpulan skala mesin virtual diskalakan, mesin virtual paling lama yang tidak dilindungi skala masuk akan dipilih untuk penghapusan.  Untuk kumpulan skala mesin virtual zonal, kumpulan skala terlebih dahulu akan diimbangi di seluruh zona.  Di dalam setiap zona, mesin virtual paling lama yang tidak terlindungi akan dipilih untuk penghapusan.  'NewestVM' saat kumpulan skala mesin virtual diskalakan, mesin virtual terbaru yang tidak dilindungi skala masuk akan dipilih untuk dihapus.  Untuk kumpulan skala mesin virtual zonal, kumpulan skala terlebih dahulu akan diimbangi di seluruh zona.  Di dalam setiap zona, mesin virtual terbaru yang tidak terlindungi akan dipilih untuk penghapusan.

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

### -SinglePlacementGroup
Menentukan grup penempatan tunggal.

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

### -SkipExtensionsOnOverprovisionedVMs
Menentukan bahwa ekstensi tidak berjalan pada VM berlebihan tambahan.

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

### -SkuCapacity
Menentukan jumlah instans dalam VMSS.

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

### -SkuName
Menentukan ukuran semua instans VMSS.

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
Menentukan tingkatan VMSS.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standar
- Dasar

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
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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

### -TerminateScheduledEventNotBeforeTimeoutInMinutes
Lama waktu yang dapat dikonfigurasi (dalam menit) Mesin Virtual yang dihapus mungkin harus menyetujui Akhiri Acara Terjadwal sebelum acara disetujui secara otomatis (waktu habis).

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
Menentukan apakah Hentikan Acara Terjadwal diaktifkan atau dinonaktifkan.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona Waktu
Menentukan zona waktu untuk Windows OS. misalnya Waktu Standar \" \" Pasifik. <br>
Nilai yang mungkin dapat [TimeZoneInfo.Id](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.id?#System_TimeZoneInfo_Id) nilai dari zona waktu yang dikembalikan oleh [Zona WaktuInfo.GetSystemTimeZones.](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.getsystemtimezones)

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

### -UltraSSDEnabled
Bendera yang mengaktifkan atau menonaktifkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan tipe akun UltraSSD_LRS penyimpanan pada kumpulan skala mesin virtual.
Disk terkelola dengan tipe akun penyimpanan UltraSSD_LRS dapat ditambahkan ke VMSS hanya jika properti ini diaktifkan.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UpgradePolicyMode
Tentukan mode pemutakhiran ke mesin virtual dalam kumpulan skala.
Nilai yang dapat diterima untuk parameter ini adalah:
- Otomatis
- Manual
- Berputar

```yaml
Type: Microsoft.Azure.Management.Compute.Models.UpgradeMode
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Rolling

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdContainer
Menentukan URL kontainer yang digunakan untuk menyimpan disk sistem operasi untuk VMSS.

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

### -VirtualMachinescaleSet
Menentukan objek VMSS lokal.
Untuk mendapatkan objek VMSS, gunakan Get-AzVmss cmdlet.
Objek mesin virtual ini berisi status yang diperbarui untuk VMSS.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMScaleSetName
Menentukan nama VMSS yang dibuat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS

[Get-AzVmss](./Get-AzVmss.md)

[New-AzVmss](./New-AzVmss.md)

[Remove-AzVmss](./Remove-AzVmss.md)

[Mulai Ulang AzVmss](./Restart-AzVmss.md)

[Set-AzVmss](./Set-AzVmss.md)

[Start-AzVmss](./Start-AzVmss.md)

[Stop-AzVmss](./Stop-AzVmss.md)


