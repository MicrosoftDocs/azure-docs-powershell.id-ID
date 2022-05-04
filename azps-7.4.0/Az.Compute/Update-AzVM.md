---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 38917534-49C6-47EA-B815-240F794EE655
online version: https://docs.microsoft.com/powershell/module/az.compute/update-azvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzVM.md
ms.openlocfilehash: 70613ec9379cfa1d6bb818b051a7ec391bcf3473
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144629598"
---
# Update-AzVM

## SYNOPSIS
Memperbarui status komputer virtual Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/update-azvm) untuk informasi terbaru.

## SYNTAX

### ResourceGroupNameParameterSetName (Default)
```
Update-AzVM [-ResourceGroupName] <String> -VM <PSVirtualMachine> [-Tag <Hashtable>]
 [-OsDiskWriteAccelerator <Boolean>] [-UltraSSDEnabled <Boolean>] [-MaxPrice <Double>]
 [-EncryptionAtHost <Boolean>] [-ProximityPlacementGroupId <String>] [-HostId <String>]
 [-CapacityReservationGroupId <String>] [-AsJob] [-NoWait] [-UserData <String>] [-HibernationEnabled]
 [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ExplicitIdentityParameterSet
```
Update-AzVM [-ResourceGroupName] <String> -VM <PSVirtualMachine> [-Tag <Hashtable>]
 -IdentityType <ResourceIdentityType> [-IdentityId <String[]>] [-OsDiskWriteAccelerator <Boolean>]
 [-UltraSSDEnabled <Boolean>] [-MaxPrice <Double>] [-EncryptionAtHost <Boolean>]
 [-ProximityPlacementGroupId <String>] [-HostId <String>] [-CapacityReservationGroupId <String>] [-AsJob]
 [-NoWait] [-UserData <String>] [-HibernationEnabled] [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdParameterSetName
```
Update-AzVM [-Id] <String> -VM <PSVirtualMachine> [-Tag <Hashtable>] [-OsDiskWriteAccelerator <Boolean>]
 [-UltraSSDEnabled <Boolean>] [-MaxPrice <Double>] [-EncryptionAtHost <Boolean>]
 [-ProximityPlacementGroupId <String>] [-HostId <String>] [-CapacityReservationGroupId <String>] [-AsJob]
 [-NoWait] [-UserData <String>] [-HibernationEnabled] [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzVM** memperbarui status komputer virtual Azure ke status objek komputer virtual.

## EXAMPLES

### Contoh 1: Memperbarui komputer virtual
```powershell
Update-AzVM -ResourceGroupName "ResourceGroup11" -VM $VirtualMachine
```

Perintah ini memperbarui komputer virtual, $VirtualMachine, di ResourceGroup11.
Perintah memperbaruinya dengan menggunakan objek komputer virtual yang disimpan dalam variabel $VirtualMachine.
Untuk mendapatkan objek komputer virtual, gunakan cmdlet **Get-AzVM** .

### Contoh 2: Perbarui komputer virtual untuk menonaktifkan hyperthreading.
```powershell
$resourceGroupName = <Resource Group Name>;
$vmname = <Virtual Machine Name>;
$domainNameLabel = "d1" + $rgname;
$vCPUsCoreInitial = 2;
$vCPUsAvailableInitial = 4;
$vCPUsCore1 = 1;
$vCPUsAvailable1 = 1;
$vmSize = 'Standard_D4s_v4';

$securePassword = <Password> | ConvertTo-SecureString -AsPlainText -Force;  
$user = "user";
$cred = New-Object System.Management.Automation.PSCredential ($user, $securePassword);
$vm = New-AzVM -ResourceGroupName $rgname -Name $vmname -Credential $cred -DomainNameLabel $domainNameLabel -Size $vmSize -vCPUsPerCore $vCPUsCoreInitial -vCPUsAvailable $vCPUsAvailableInitial;
# The $vm.HardwareProfile.VmSizeProperties.VCPUsPerCore property is 2, and the $vm.HardwareProfile.VmSizeProperties.VCPUsAvailable property is 4.

Update-AzVm -ResourceGroupName $rgname -VM $vm -vCPUsAvailable $vCPUsAvailable1 -vCPUsPerCore $vCPUsCore1;
# The $vm.HardwareProfile.VmSizeProperties.VCPUsPerCore property is 1, and the $vm.HardwareProfile.VmSizeProperties.VCPUsAvailable property is 1. 
# Hyperthreading is now disabled for this VM.
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

### -EncryptionAtHost
Properti EncryptionAtHost dapat digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk komputer virtual atau set skala komputer virtual. Ini akan mengaktifkan enkripsi untuk semua disk termasuk disk Resource/Temp di host itu sendiri. 

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -HibernationEnabled
Bendera yang mengaktifkan atau menonaktifkan kemampuan hibernasi pada VM.

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

### -HostId
The Id of Host

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

### -Id
Menentukan ID sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: IdParameterSetName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityId
Menentukan daftar identitas pengguna yang terkait dengan komputer virtual.
Referensi identitas pengguna adalah ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Jenis identitas yang digunakan untuk komputer virtual. Nilai yang valid adalah SystemAssigned, UserAssigned, SystemAssignedUserAssigned, dan None.

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

### -MaxPrice
Menentukan harga maksimum yang ingin Anda bayar untuk VM/VMSS berprioritas rendah. Harga ini dalam Dolar AS. Harga ini akan dibandingkan dengan harga prioritas rendah saat ini untuk ukuran VM. Selain itu, harga dibandingkan pada saat membuat/memperbarui VM/VMSS prioritas rendah dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga prioritas rendah saat ini. MaxPrice juga akan digunakan untuk mengusir VM/VMSS prioritas rendah jika harga prioritas rendah saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang mungkin adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0,01538.  -1 menunjukkan bahwa VM/VMSS prioritas rendah tidak boleh dikeluarkan karena alasan harga. Selain itu, harga maksimum default adalah -1 jika tidak disediakan oleh Anda.

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

### -NoWait
Memulai operasi dan segera kembali, sebelum operasi selesai. Untuk menentukan apakah operasi telah berhasil diselesaikan, gunakan beberapa mekanisme lain.

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

### -ProximityPlacementGroupId
Id sumber daya Grup Penempatan Kedekatan untuk digunakan dengan komputer virtual ini.

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
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSetName, ExplicitIdentityParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Menentukan sumber daya dan grup sumber daya dapat ditandai dengan sekumpulan pasangan nama-nilai.
Menambahkan tag ke sumber daya memungkinkan Anda mengelompokkan sumber daya bersama-sama di seluruh grup sumber daya dan membuat tampilan Anda sendiri.
Setiap sumber daya atau grup sumber daya dapat memiliki maksimal 15 tag.

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

### -UltraSSDEnabled
Bendera yang memungkinkan atau menonaktifkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan jenis akun penyimpanan UltraSSD_LRS pada VM.
Disk terkelola dengan jenis akun penyimpanan UltraSSD_LRS dapat ditambahkan ke komputer virtual hanya jika properti ini diaktifkan.

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

### -UserData
UserData untuk VM, yang akan dikodekan base-64. Pelanggan tidak boleh meneruskan rahasia apa pun di sini.

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

### -vCPUCountAvailable
Menentukan jumlah vCPU yang tersedia untuk VM. Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku defaultnya adalah mengaturnya ke nilai vCPU yang tersedia untuk ukuran VM yang diekspos dalam respons api daftar [semua ukuran komputer virtual yang tersedia di suatu wilayah](https://docs.microsoft.com/en-us/rest/api/compute/resource-skus/list).

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

### -vCPUCountPerCore
Menentukan rasio vCPU ke inti fisik. Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku default diatur ke nilai vCPUsPerCore untuk Ukuran VM yang diekspos dalam respons api daftar [semua ukuran komputer virtual yang tersedia di suatu wilayah](https://docs.microsoft.com/en-us/rest/api/compute/resource-skus/list). Mengatur properti ini ke 1 juga berarti bahwa hyper-threading dinonaktifkan.

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

### -VM
Menentukan objek komputer virtual lokal.
Untuk mendapatkan objek komputer virtual, gunakan cmdlet Get-AzVM.
Objek komputer virtual ini berisi status yang diperbarui untuk komputer virtual.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Dapatkan-AzVM](./Get-AzVM.md)

[New-AzVM](./New-AzVM.md)

[Hapus-AzVM](./Remove-AzVM.md)

[Hidupkan ulang-AzVM](./Restart-AzVM.md)

[Start-AzVM](./Start-AzVM.md)

[Stop-AzVM](./Stop-AzVM.md)

[New-AzVMConfig](./New-AzVMConfig.md)


