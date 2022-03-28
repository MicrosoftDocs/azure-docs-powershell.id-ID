---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 50B64FFE-8277-4DAA-805A-271123B35355
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmadditionalunattendcontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMAdditionalUnattendContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMAdditionalUnattendContent.md
ms.openlocfilehash: 023c592e91ac31db716253cc3af883d2b52b2b90
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139978701"
---
# Add-AzVMAdditionalUnattendContent

## SYNOPSIS
Menambahkan informasi ke file jawaban Windows Tanpa Windows.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/add-azvmadditionalunattendcontent) untuk informasi terkini.

## SYNTAX

```
Add-AzVMAdditionalUnattendContent [-VM] <PSVirtualMachine> [[-Content] <String>]
 [[-SettingName] <SettingNames>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVMAdditionalUnattendContent** menambahkan informasi ke file jawaban Windows Tanpa Pengawasan.
Tentukan informasi berformat .xml berkode basis 64 tambahan yang ditambahkan cmdlet unattend.xml file.

## EXAMPLES

### Contoh 1: Tambahkan konten ke unattend.xml
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $AucContent = "<UserAccounts><AdministratorPassword><Value>" + "Password" + "</Value><PlainText>true</PlainText></AdministratorPassword></UserAccounts>";
PS C:\> $VirtualMachine = Add-AzVMAdditionalUnattendContent -VM $VirtualMachine -Content $AucContent -SettingName "AutoLogon"
```

Perintah pertama mendapatkan ketersediaan yang diatur bernama AvailabilitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah kedua membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari kumpulan ketersediaan yang disimpan di $AvailabilitySet.
Perintah ketiga membuat objek kredensial dengan menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya dalam $Credential variabel.
Perintah akan meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential`.
Perintah keempat menggunakan cmdlet **Set-AzVMOperatingSystem** untuk mengonfigurasi mesin virtual yang disimpan di $VirtualMachine.
Perintah kelima menetapkan konten ke $AucContent baru.
Konten menyertakan kata sandi.
Perintah terakhir menambahkan konten yang disimpan di $AucContent ke unattend.xml file.

## PARAMETERS

### -Content
Menentukan konten yang diformat XML berkode 64.
Cmdlet ini menambahkan konten ke unattend.xml file.
Konten XML harus kurang dari 4 KB dan harus menyertakan elemen akar untuk pengaturan atau fitur yang disisipkan cmdlet ini.

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

### -SettingName
Menentukan nama pengaturan untuk menerapkan konten.
Nilai yang dapat diterima untuk parameter ini adalah:
- FirstLogonCommands
- AutoLogon

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.SettingNames]
Parameter Sets: (All)
Aliases:
Accepted values: AutoLogon, FirstLogonCommands

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual yang telah dimodifikasi cmdlet ini.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Buat objek mesin virtual menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) .

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

### System.Nullable'1[[Microsoft.Azure.Management.Compute.Models.SettingNames, Microsoft.Azure.Management.Compute, Version=23.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)

[Set-AzvMOperatingSystem](./Set-AzVMOperatingSystem.md)

[New-azvmConfig](./New-AzVMConfig.md)
