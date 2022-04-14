---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 3E7B9EFA-8BC2-46EB-9AD7-43EAB7FF3891
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmssosprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssOsProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssOsProfile.md
ms.openlocfilehash: 609a11d8228ad598d9c24b74e83074117de87ded
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142088421"
---
# Set-AzVmssOsProfile

## SYNOPSIS
Mengatur properti profil sistem operasi VMSS.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmssosprofile) untuk informasi terbaru.

## SYNTAX

```
Set-AzVmssOsProfile [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-ComputerNamePrefix] <String>]
 [[-AdminUsername] <String>] [[-AdminPassword] <String>] [[-CustomData] <String>]
 [[-WindowsConfigurationProvisionVMAgent] <Boolean>] [-LinuxConfigurationProvisionVMAgent <Boolean>]
 [[-WindowsConfigurationEnableAutomaticUpdate] <Boolean>] [[-TimeZone] <String>]
 [[-AdditionalUnattendContent] <AdditionalUnattendContent[]>] [[-Listener] <WinRMListener[]>]
 [[-LinuxConfigurationDisablePasswordAuthentication] <Boolean>] [[-PublicKey] <SshPublicKey[]>]
 [[-Secret] <VaultSecretGroup[]>] [-WindowsConfigurationPatchMode <String>]
 [-LinuxConfigurationPatchMode <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVmssOsProfile** mengatur properti profil sistem operasi Set Skala Mesin Virtual.

## EXAMPLES

### Contoh 1: Mengatur properti profil sistem operasi untuk VMSS
```
PS C:\> $vmss = New-AzVmssConfig -Location $Loc -SkuCapacity 2 -SkuName "Standard_A0" -UpgradePolicyMode "Automatic" -NetworkInterfaceConfiguration $NetCfg
PS C:\> Set-AzVmssOSProfile -VirtualMachineScaleSet $vmss -ComputerNamePrefix "Test" -AdminUsername $AdminUsername -AdminPassword $AdminPassword
```

Perintah ini mengatur properti profil sistem operasi untuk objek $vmss.
Perintah mengatur prefiks nama komputer untuk semua instans mesin virtual dalam VMSS untuk Menguji dan menyediakan nama pengguna dan kata sandi administrator.

## PARAMETERS

### -AdditionalUnattendContent
Menentukan objek konten tanpa pengawas.
Anda dapat menggunakan Add-AzVMAdditionalUnattendContent untuk membuat objek.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.AdditionalUnattendContent[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdminPassword
Menentukan kata sandi administrator untuk digunakan untuk semua instans mesin virtual dalam VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdminUsername
Menentukan nama akun administrator untuk digunakan untuk semua instans mesin virtual dalam VMSS. <br>
**batasan Windows-saja:** Tidak dapat diakhiri dengan \".\" <br>
**Nilai yang tidak diperbolehkan:** \" administrator\", \"admin\", \"pengguna\", \"pengguna1\", \"uji\", \"user2\", \"uji1\", \"user3\", \"admin1\", \"1\", \"123\", \"a\", \"actuser\", adm\", \"\"admin2\", aspnet\", \"\"mencadangkan\", \"konsol\", \"david\", \"tamu\", \"john\", \"pemilik\", \"akar\", \"server\", \"sql\", \"mendukung \", \"support_388945a0\", \"sys\", \"test2\", \"test3\", \"user4\", \"user5\". <br>
**Panjang minimum (Linux):** 1 karakter <br>
**Panjang maks (Linux):** 64 karakter <br>
**Panjang maksimal (Windows):** 20 karakter  <br>
<li> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan dalam bidang ini, lihat [Memilih Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/devops/organizations/settings/naming-restrictions).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerNamePrefix
Menentukan prefiks nama komputer untuk semua instans mesin virtual dalam VMSS.
Nama komputer harus panjangnya 1 hingga 15 karakter.

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

### -CustomData
Menentukan string data kustom berkode basis 64.
Ini didekodekan ke array biner yang disimpan sebagai file di mesin virtual.
Panjang maksimum array biner adalah 65535 byte. <br>
Untuk menggunakan cloud-init untuk VM Anda, lihat [Menggunakan cloud-init untuk mengkustomisasi VM Linux selama pembuatan](/azure/virtual-machines/linux/tutorial-automate-vm-deployment).

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

### -LinuxConfigurationDisablePasswordAuthentication
Menunjukkan bahwa cmdlet ini menonaktifkan autentikasi kata sandi.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinuxConfigurationPatchMode
Menentukan mode VM Guest Patching ke mesin virtual IaaS atau mesin virtual yang terkait dengan skala mesin virtual yang diatur dengan OrchestrationMode sebagai Fleksibel.<br /><br /> Nilai yang memungkinkan adalah:<br /><br /> **ImageDefault** - Konfigurasi patch default mesin virtual digunakan. <br /><br /> **AutomaticByPlatform** - Mesin virtual akan diperbarui secara otomatis oleh platform. Ketentuan propertiVMAgent harus benar

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

### -LinuxConfigurationProvisionVMAgent
Menunjukkan apakah agen mesin virtual harus disediakan pada mesin virtual. <br><br> Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku default adalah mengaturnya ke true.  Ini akan memastikan bahwa Agen VM diinstal pada VM sehingga ekstensi dapat ditambahkan ke VM nanti

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

### -Pendengar
Menentukan pendengar Windows Remote Management (WinRM).
Ini memungkinkan Windows PowerShell jarak jauh.
Anda dapat menggunakan cmdlet Add-AzVmssWinRMListener untuk membuat pendengar.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.WinRMListener[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicKey
Menentukan objek kunci publik Secure Shell (SSH).
Anda dapat menggunakan cmdlet Add-AzVMSshPublicKey untuk membuat objek.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.SshPublicKey[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rahasia
Menentukan objek rahasia yang berisi referensi sertifikat untuk diletakkan di mesin virtual.
Anda dapat menggunakan cmdlet Add-AzVmssSecret untuk membuat objek rahasia.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VaultSecretGroup[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona Waktu
Menentukan zona waktu mesin maya. misalnya \"Waktu\" Standar Pasifik. <br>
Nilai yang memungkinkan dapat [berupa nilai TimeZoneInfo.Id](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.id?#System_TimeZoneInfo_Id) dari zona waktu yang dikembalikan oleh [TimeZoneInfo.GetSystemTimeZones](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.getsystemtimezones).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet New-AzVmssConfig untuk membuat objek.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WindowsConfigurationEnableAutomaticUpdate
Menunjukkan apakah mesin virtual dalam VMSS diaktifkan untuk pembaruan otomatis.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsConfigurationPatchMode
Menentukan mode VM Guest Patching ke mesin virtual IaaS atau mesin virtual yang terkait dengan skala mesin virtual yang diatur dengan OrchestrationMode sebagai Fleksibel.<br /><br /> Nilai yang memungkinkan adalah:<br /><br /> **Manual** - Anda mengontrol aplikasi patch ke mesin virtual. Anda melakukan ini dengan menerapkan patch secara manual di dalam VM. Dalam mode ini, pembaruan otomatis dinonaktifkan; properti WindowsConfiguration.enableAutomaticUpdates harus false<br /><br /> **AutomaticByOS** - Mesin virtual akan diperbarui secara otomatis oleh OS. Properti WindowsConfiguration.enableAutomaticUpdates harus true. <br /><br /> **AutomaticByPlatform** - mesin virtual akan diperbarui secara otomatis oleh platform. Provision propertiVMAgent dan WindowsConfiguration.enableAutomaticUpdates harus benar
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

### -WindowsConfigurationProvisionVMAgent
Menunjukkan apakah agen mesin virtual harus disediakan pada mesin virtual dalam VMSS.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.String

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Management.Compute.Models.AdditionalUnattendContent[]

### Microsoft.Azure.Management.Compute.Models.WinRMListener[]

### Microsoft.Azure.Management.Compute.Models.SshPublicKey[]

### Microsoft.Azure.Management.Compute.Models.VaultSecretGroup[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS

[Add-AzVMAdditionalUnattendContent](./Add-AzVMAdditionalUnattendContent.md)

[Add-AzVmssWinRMListener](./Add-AzVmssWinRMListener.md)

[Add-AzVMSshPublicKey](./Add-AzVMSshPublicKey.md)

[Add-AzVmssSecret](./Add-AzVmssSecret.md)

[New-AzVmssConfig](./New-AzVmssConfig.md)


