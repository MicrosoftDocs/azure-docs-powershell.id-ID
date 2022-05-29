---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 50B64FFE-8277-4DAA-805A-271123B35355
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmadditionalunattendcontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMAdditionalUnattendContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMAdditionalUnattendContent.md
ms.openlocfilehash: 6e8be3d178c51c1185ba6f31db57b4f1a8db97bc
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145770258"
---
# Add-AzVMAdditionalUnattendContent

## SYNOPSIS
Menambahkan informasi ke file jawaban Penyetelan Windows yang tidak dijaga.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvmadditionalunattendcontent) untuk informasi terbaru.

## SYNTAX

```
Add-AzVMAdditionalUnattendContent [-VM] <PSVirtualMachine> [[-Content] <String>]
 [[-SettingName] <SettingNames>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Add-AzVMAdditionalUnattendContent** menambahkan informasi ke file jawaban Penyiapan Windows tanpa pengawasan.
Tentukan informasi berformat .xml yang dikodekan dasar 64 tambahan yang ditambahkan cmdlet ini ke file unattend.xml.

## EXAMPLES

### Contoh 1: Menambahkan konten ke unattend.xml
```powershell
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
$Credential = Get-Credential
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
$AucContent = "<UserAccounts><AdministratorPassword><Value>" + "Password" + "</Value><PlainText>true</PlainText></AdministratorPassword></UserAccounts>";
$VirtualMachine = Add-AzVMAdditionalUnattendContent -VM $VirtualMachine -Content $AucContent -SettingName "AutoLogon"
```

Perintah pertama mendapatkan set ketersediaan bernama AvailabilitySet03 di grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $AvailabilitySet.
Perintah kedua membuat objek komputer virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Komputer virtual milik set ketersediaan yang disimpan di $AvailabilitySet.
Perintah ketiga membuat objek kredensial dengan menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya dalam variabel $Credential.
Perintah meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential`.
Perintah keempat menggunakan cmdlet **Set-AzVMOperatingSystem** untuk mengonfigurasi komputer virtual yang disimpan di $VirtualMachine.
Perintah kelima menetapkan konten ke variabel $AucContent.
Konten menyertakan kata sandi.
Perintah akhir menambahkan konten yang disimpan dalam $AucContent ke file unattend.xml.

## PARAMETERS

### -Isi
Menentukan konten berformat XML dasar 64 yang dikodekan.
Cmdlet ini menambahkan konten ke file unattend.xml.
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

### -SettingName
Menentukan nama pengaturan tempat konten diterapkan.
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
Menentukan objek komputer virtual yang dimodifikasi cmdlet ini.
Untuk mendapatkan objek komputer virtual, gunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Buat objek komputer virtual dengan menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

### System.Nullable'1[[Microsoft.Azure.Management.Compute.Models.SettingNames, Microsoft.Azure.Management.Compute, Version=23.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)

[Set-AzVMOperatingSystem](./Set-AzVMOperatingSystem.md)

[New-AzVMConfig](./New-AzVMConfig.md)
