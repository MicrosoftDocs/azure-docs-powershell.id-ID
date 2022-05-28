---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 9EE192A5-4E3F-41ED-A539-8E0A5D5EA4C9
online version: https://docs.microsoft.com/powershell/module/az.compute/update-azvmss
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzVmss.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzVmss.md
ms.openlocfilehash: d77185e8ca4155aa1f2a850c763a5d2fe049c7da
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145499723"
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
 [-OsDiskWriteAccelerator <Boolean>] [-Overprovision <Boolean>] [-ScaleInPolicyForceDeletion <Boolean>]
 [-PauseTimeBetweenBatches <String>] [-PlanName <String>] [-PlanProduct <String>] [-PlanPromotionCode <String>]
 [-PlanPublisher <String>] [-ProvisionVMAgent <Boolean>] [-ProximityPlacementGroupId <String>]
 [-ScaleInPolicy <String[]>] [-SinglePlacementGroup <Boolean>] [-SkipExtensionsOnOverprovisionedVMs <Boolean>]
 [-SkuCapacity <Int32>] [-SkuName <String>] [-SkuTier <String>] [-Tag <Hashtable>]
 [-TerminateScheduledEventNotBeforeTimeoutInMinutes <Int32>] [-TerminateScheduledEvents <Boolean>]
 [-TimeZone <String>] [-UltraSSDEnabled <Boolean>] [-UpgradePolicyMode <UpgradeMode>]
 [-CapacityReservationGroupId <String>] [-VhdContainer <String[]>] [-AsJob] [-EncryptionAtHost <Boolean>]
 [-UserData <String>] [-AutomaticRepairAction <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
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
 [-ScaleInPolicyForceDeletion <Boolean>] [-PauseTimeBetweenBatches <String>] [-PlanName <String>]
 [-PlanProduct <String>] [-PlanPromotionCode <String>] [-PlanPublisher <String>] [-ProvisionVMAgent <Boolean>]
 [-ProximityPlacementGroupId <String>] [-ScaleInPolicy <String[]>] [-SinglePlacementGroup <Boolean>]
 [-SkipExtensionsOnOverprovisionedVMs <Boolean>] [-SkuCapacity <Int32>] [-SkuName <String>] [-SkuTier <String>]
 [-Tag <Hashtable>] [-TerminateScheduledEventNotBeforeTimeoutInMinutes <Int32>]
 [-TerminateScheduledEvents <Boolean>] [-TimeZone <String>] [-UltraSSDEnabled <Boolean>]
 [-UpgradePolicyMode <UpgradeMode>] [-CapacityReservationGroupId <String>] [-VhdContainer <String[]>] [-AsJob]
 [-EncryptionAtHost <Boolean>] [-UserData <String>] [-AutomaticRepairAction <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzVmss** memperbarui status Virtual Machine Scale Set (VMSS) ke status objek VMSS lokal.

## EXAMPLES

### Contoh 1: Perbarui status VMSS ke status objek VMSS lokal.
```powershell
Update-AzVmss -ResourceGroupName "Group001" -Name "VMSS001" -VirtualMachineScaleSet $LocalVMSS
```

Perintah ini memperbarui status VMSS bernama VMSS001 yang termasuk dalam grup sumber daya bernama Group001 ke status objek VMSS lokal, $LocalVMSS.

### Contoh 2

Memperbarui status VMSS. (dibuat otomatis)

<!-- Aladdin Generated Example -->


```powershell
Update-AzVmss -ResourceGroupName 'Group001' -VMScaleSetName 'VMSS001' -VirtualMachineScaleSet <PSVirtualMachineScaleSet> -IdentityType SystemAssigned
```

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
Mengatur apakah peningkatan OS harus secara otomatis diterapkan ke instans set skala secara bergulir saat versi gambar yang lebih baru tersedia.

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

### -AutomaticRepairAction
Jenis tindakan perbaikan (ganti, hidupkan ulang, reimage) yang akan digunakan untuk memperbaiki komputer virtual yang tidak sehat dalam set skala. Nilai defaultnya adalah ganti.

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

### -AutomaticRepairGracePeriod
Jumlah waktu di mana perbaikan otomatis ditangguhkan karena perubahan status pada VM. Waktu tenggang dimulai setelah perubahan status selesai. Ini membantu menghindari perbaikan dini atau tidak disengaja. Durasi waktu harus ditentukan dalam format ISO 8601. Masa tenggang minimum yang diizinkan adalah 30 menit (PT30M), yang juga merupakan nilai default. Masa tenggang maksimum yang diizinkan adalah 90 menit (PT90M).

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
Apakah diagnostik boot harus diaktifkan pada set skala komputer virtual.

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
URI akun penyimpanan yang digunakan untuk menempatkan output konsol dan cuplikan layar.

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

### -CapacityReservationGroupId
Id Grup reservasi kapasitas yang digunakan untuk mengalokasikan.

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
Menentukan string data kustom yang dikodekan base-64.
Ini didekodekan ke array biner yang disimpan sebagai file pada komputer virtual.
Panjang maksimum array biner adalah 65535 byte. <br>
Untuk menggunakan cloud-init untuk VM Anda, lihat [Menggunakan cloud-init untuk menyesuaikan VM Linux selama pembuatan](/azure/virtual-machines/linux/tutorial-automate-vm-deployment).

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
Nonaktifkan Putar Kembali Otomatis untuk Kebijakan Peningkatan OS Otomatis

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
Menunjukkan bahwa cmdlet ini menonaktifkan autentikasi kata sandi untuk OS Linux.

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
Aktifkan atau nonaktifkan perbaikan otomatis pada set skala komputer virtual.

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
Menunjukkan apakah komputer virtual Windows di VMSS diaktifkan untuk pembaruan otomatis.

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
Parameter ini dapat digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk set skala komputer virtual.

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
Menentukan daftar identitas pengguna yang terkait dengan set skala komputer virtual.
Referensi identitas pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Menentukan jenis identitas yang digunakan untuk set skala komputer virtual.
Jenis 'SystemAssignedUserAssigned' mencakup identitas yang dibuat secara implisit dan sekumpulan identitas yang ditetapkan pengguna.
Jenis 'Tidak Ada' akan menghapus identitas apa pun dari set skala komputer virtual.
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
Menentukan jenis penawaran gambar komputer virtual (VMImage).
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
Menentukan SKU VMImage.
Untuk mendapatkan SKU, gunakan cmdlet Get-AzVMImageSku.

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
Untuk menggunakan versi terbaru, tentukan nilai terbaru alih-alih versi tertentu.

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
VMSS membuat disk sistem operasi dalam kontainer gambar pengguna yang sama.

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
Tentukan jenis lisensi, yaitu untuk membawa skenario lisensi Anda sendiri.

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
Menentukan jenis akun penyimpanan untuk disk terkelola.
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
Persentase maksimum dari total instans komputer virtual yang akan ditingkatkan secara bersamaan dengan peningkatan bergulir dalam satu batch.
Karena ini adalah instans maksimum yang tidak sehat dalam batch sebelumnya atau di masa mendatang dapat menyebabkan persentase instans dalam batch berkurang untuk memastikan keandalan yang lebih tinggi.
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
Menentukan harga maksimum yang ingin Anda bayar untuk VM/VMSS berprioritas rendah. Harga ini dalam Dolar AS. Harga ini akan dibandingkan dengan harga prioritas rendah saat ini untuk ukuran VM. Selain itu, harga dibandingkan pada saat membuat/memperbarui VM/VMSS prioritas rendah dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga prioritas rendah saat ini. MaxPrice juga akan digunakan untuk mengusir VM/VMSS prioritas rendah jika harga prioritas rendah saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang mungkin adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0,01538.  -1 menunjukkan bahwa VM/VMSS prioritas rendah tidak boleh dikeluarkan karena alasan harga. Selain itu, harga maksimum default adalah -1 jika tidak disediakan oleh Anda.

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
Persentase maksimum dari total instans komputer virtual dalam set skala yang dapat secara bersamaan tidak sehat, baik sebagai akibat dari peningkatan, atau dengan ditemukan dalam keadaan tidak sehat oleh pemeriksaan kesehatan komputer virtual sebelum peningkatan bergulir dibatalkan.
Batasan ini akan diperiksa sebelum memulai batch apa pun.
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
Persentase maksimum instans komputer virtual yang ditingkatkan yang dapat ditemukan dalam keadaan tidak sehat.
Pemeriksaan ini akan terjadi setelah setiap batch ditingkatkan.
Jika persentase ini pernah terlampaui, pembaruan bergulir akan dibatalkan.
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
Menentukan mode penembolokan disk sistem operasi.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- ReadOnly
- ReadWrite Nilai defaultnya adalah ReadWrite.
Jika Anda mengubah nilai penembolokan, cmdlet akan memulai ulang komputer virtual.
Pengaturan ini memengaruhi konsistensi dan performa disk.

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
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan pada disk OS.

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

### -Provisi berlebih
Menunjukkan apakah cmdlet melakukan provisi berlebih pada VMSS.

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
Waktu tunggu antara menyelesaikan pembaruan untuk semua komputer virtual dalam satu batch dan memulai batch berikutnya.
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
Menentukan nama paket.

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
Menunjukkan apakah agen komputer virtual harus disediakan pada komputer virtual Windows di VMSS.

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
Id sumber daya Grup Penempatan Kedekatan untuk digunakan dengan set skala ini.

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
Menentukan nama grup sumber daya tempat VMSS berada.

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
Aturan yang harus diikuti saat menskalakan-dalam set skala komputer virtual.  Nilai yang mungkin adalah: 'Default', 'OldestVM' dan 'NewestVM'.  'Default' ketika set skala komputer virtual diskalakan, set skala akan terlebih dahulu diseimbangkan di seluruh zona jika merupakan set skala zona.  Kemudian, itu akan seimbang di seluruh Domain Kesalahan sejauh mungkin.  Dalam setiap Domain Kesalahan, komputer virtual yang dipilih untuk dihapus akan menjadi yang terbaru yang tidak dilindungi dari penyempurnaan skala.  'OldestVM' ketika set skala komputer virtual sedang diskalakan, komputer virtual terlama yang tidak terlindungi dari penyempurnaan skala akan dipilih untuk dihapus.  Untuk set skala komputer virtual zonal, set skala pertama-tama akan seimbang di seluruh zona.  Dalam setiap zona, komputer virtual terlama yang tidak dilindungi akan dipilih untuk dihapus.  'NewestVM' ketika set skala komputer virtual sedang diskalakan, komputer virtual terbaru yang tidak terlindungi dari penyempurnaan skala akan dipilih untuk dihapus.  Untuk set skala komputer virtual zonal, set skala pertama-tama akan seimbang di seluruh zona.  Dalam setiap zona, komputer virtual terbaru yang tidak dilindungi akan dipilih untuk dihapus.

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

### -ScaleInPolicyForceDeletion
Menerapkan Penghapusan Paksa saat menggunakan Kebijakan ScaleIn.

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
Menentukan bahwa ekstensi tidak berjalan pada VM ekstra yang terlalu provisi.

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
Menentukan tingkat VMSS.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard
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
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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
Durasi waktu yang dapat dikonfigurasi (dalam menit) Komputer Virtual yang dihapus harus berpotensi menyetujui Peristiwa Terjadwal Penghentian sebelum peristiwa disetujui secara otomatis (waktu habis).

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
Menentukan apakah peristiwa Hentikan Terjadwal diaktifkan atau dinonaktifkan.

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
Menentukan zona waktu untuk OS Windows. misalnya \"Waktu\" Standar Pasifik. <br>
Nilai yang mungkin dapat [TimeZoneInfo.Id](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.id?#System_TimeZoneInfo_Id) nilai dari zona waktu yang dikembalikan oleh [TimeZoneInfo.GetSystemTimeZones](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.getsystemtimezones).

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
Bendera yang memungkinkan atau menonaktifkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan jenis akun penyimpanan UltraSSD_LRS pada set skala komputer virtual.
Disk terkelola dengan jenis akun penyimpanan UltraSSD_LRS dapat ditambahkan ke VMSS hanya jika properti ini diaktifkan.

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
Menentukan mode peningkatan ke komputer virtual dalam set skala.
Nilai yang dapat diterima untuk parameter ini adalah:
- Otomatis
- Manual
- Bergulir

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

### -UserData
UserData untuk Vmss, yang akan dikodekan base-64. Pelanggan tidak boleh meneruskan rahasia apa pun di sini.

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

### -VirtualMachineScaleSet
Menentukan objek VMSS lokal.
Untuk mendapatkan objek VMSS, gunakan cmdlet Get-AzVmss.
Objek komputer virtual ini berisi status yang diperbarui untuk VMSS.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS

[Dapatkan-AzVmss](./Get-AzVmss.md)

[Baru-AzVmss](./New-AzVmss.md)

[Remove-AzVmss](./Remove-AzVmss.md)

[Mulai ulang-AzVmss](./Restart-AzVmss.md)

[Set-AzVmss](./Set-AzVmss.md)

[Start-AzVmss](./Start-AzVmss.md)

[Stop-AzVmss](./Stop-AzVmss.md)


