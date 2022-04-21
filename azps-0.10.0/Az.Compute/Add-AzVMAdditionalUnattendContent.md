---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 50B64FFE-8277-4DAA-805A-271123B35355
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/add-azvmadditionalunattendcontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVMAdditionalUnattendContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVMAdditionalUnattendContent.md
ms.openlocfilehash: e4359629da6f4df4c8da26e5ade2b2652c0762e4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142721459"
---
# Add-AzVMAdditionalUnattendContent

## SYNOPSIS
Menambahkan informasi ke file jawaban penyetelan Windows tanpa pengawas.

## SYNTAX

```
Add-AzVMAdditionalUnattendContent [-VM] <PSVirtualMachine> [[-Content] <String>]
 [[-SettingName] <SettingNames>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Add-AzVMAdditionalUnattendContent** menambahkan informasi ke file jawaban penyiapan Windows tanpa pengawasan.
Tentukan informasi .xml berkode dasar tambahan 64 yang ditambahkan cmdlet ini ke file unattend.xml.

## EXAMPLES

### Contoh 1: Menambahkan konten ke unattend.xml
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $AucContent = "<UserAccounts><AdministratorPassword><Value>" + "Password" + "</Value><PlainText>true</PlainText></AdministratorPassword></UserAccounts>";
PS C:\> $VirtualMachine = Add-AzVMAdditionalUnattendContent -VM $VirtualMachine -Content $AucContent -SettingName "AutoLogon"
```

Perintah pertama mendapatkan kumpulan ketersediaan bernama AvailablitySet03 dalam grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $AvailabilitySet.

Perintah kedua membuat objek mesin virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.
Mesin virtual termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.

Perintah ketiga membuat objek kredensial menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya dalam variabel $Credential.
Perintah meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Credential`

Perintah keempat menggunakan cmdlet **Set-AzVMOperatingSystem** untuk mengonfigurasi mesin virtual yang disimpan di $VirtualMachine.

Perintah kelima menetapkan konten ke variabel $AucContent.
Konten tersebut menyertakan kata sandi.

Perintah akhir menambahkan konten yang disimpan di $AucContent ke file unattend.xml.

## PARAMETERS

### -Konten
Menentukan konten berformat XML dasar 64 yang dikodekan.
Cmdlet ini menambahkan konten ke file unattend.xml.
Konten XML harus kurang dari 4 KB dan harus menyertakan elemen akar untuk pengaturan atau fitur yang disisipkan cmdlet ini.

```yaml
Type: String
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Type: SettingNames
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
Menentukan objek mesin virtual yang diubah cmdlet ini.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Buat objek mesin virtual menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) .

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSVirtualMachine
Parameter 'VM' menerima nilai tipe 'PSVirtualMachine' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)

[Set-AzVMOperatingSystem](./Set-AzVMOperatingSystem.md)

[New-AzVMConfig](./New-AzVMConfig.md)
