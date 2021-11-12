---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 50B64FFE-8277-4DAA-805A-271123B35355
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/add-azurermvmadditionalunattendcontent
schema: 2.0.0
ms.openlocfilehash: e1441178898f675d0ccc5e654d3020212e532d90
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422014"
---
# Add-AzureRmVMAdditionalUnattendContent

## SYNOPSIS
Menambahkan informasi ke file jawaban Windows Tanpa Windows.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVMAdditionalUnattendContent [-VM] <PSVirtualMachine> [[-Content] <String>]
 [[-SettingName] <SettingNames>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVMAdditionalUnattendContent** menambahkan informasi ke file jawaban Windows Setup tanpa Windows.
Tentukan informasi berformat .xml berkode basis 64 tambahan yang ditambahkan cmdlet unattend.xml file.

## EXAMPLES

### Contoh 1: Tambahkan konten ke unattend.xml
```
PS C:\> $AvailabilitySet = Get-AzureRmAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzureRmVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzureRmVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $AucContent = "<UserAccounts><AdministratorPassword><Value>" + "Password" + "</Value><PlainText>true</PlainText></AdministratorPassword></UserAccounts>";
PS C:\> $VirtualMachine = Add-AzureRmVMAdditionalUnattendContent -VM $VirtualMachine -Content $AucContent -SettingName "AutoLogon"
```

Perintah pertama mendapatkan kumpulan ketersediaan bernamaAblityAblitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut dalam $AvailabilitySet sumber daya.

Perintah kedua membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari ketersediaan yang telah diatur untuk $AvailabilitySet.

Perintah ketiga membuat objek kredensial dengan menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya di $Credential penerima.
Perintah akan meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .

Perintah keempat menggunakan cmdlet **Set-AzureRmVMOperatingSystem** untuk mengonfigurasi mesin virtual yang disimpan di $VirtualMachine.

Perintah kelima menetapkan konten ke $AucContent variabel.
Konten menyertakan kata sandi.

Perintah terakhir menambahkan konten yang disimpan di $AucContent ke unattend.xml file.

## PARAMETERS

### -Content
Menentukan konten yang diformat XML berkode 64.
Cmdlet ini menambahkan konten ke unattend.xml file.
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan nama pengaturan untuk menerapkan konten.
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
Menentukan objek mesin virtual yang telah dimodifikasi cmdlet ini.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzureRmVM.](./Get-AzureRmVM.md)
Buat objek mesin virtual menggunakan cmdlet [New-AzureRmVMConfig.](./New-AzureRmVMConfig.md)

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSVirtualMachine
Parameter 'VM' menerima nilai tipe 'PSVirtualMachine' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzureRmAvailabilitySet](./Get-AzureRmAvailabilitySet.md)

[Set-AzureRmVMOperatingSystem](./Set-AzureRmVMOperatingSystem.md)

[New-AzureRmVMConfig](./New-AzureRmVMConfig.md)
