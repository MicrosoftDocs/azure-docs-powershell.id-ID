---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 50B64FFE-8277-4DAA-805A-271123B35355
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/add-azurermvmadditionalunattendcontent
schema: 2.0.0
ms.openlocfilehash: e1441178898f675d0ccc5e654d3020212e532d90
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141972105"
---
# Add-AzureRmVMAdditionalUnattendContent

## SYNOPSIS
Menambahkan informasi ke file jawaban penyetelan Windows tanpa pengawas.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVMAdditionalUnattendContent [-VM] <PSVirtualMachine> [[-Content] <String>]
 [[-SettingName] <SettingNames>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Add-AzureRmVMAdditionalUnattendContent** menambahkan informasi ke file jawaban penyiapan Windows tanpa pengawasan.
Tentukan informasi .xml berkode dasar tambahan 64 yang ditambahkan cmdlet ini ke file unattend.xml.

## EXAMPLES

### Contoh 1: Menambahkan konten ke unattend.xml
```
PS C:\> $AvailabilitySet = Get-AzureRmAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzureRmVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzureRmVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $AucContent = "<UserAccounts><AdministratorPassword><Value>" + "Password" + "</Value><PlainText>true</PlainText></AdministratorPassword></UserAccounts>";
PS C:\> $VirtualMachine = Add-AzureRmVMAdditionalUnattendContent -VM $VirtualMachine -Content $AucContent -SettingName "AutoLogon"
```

Perintah pertama mendapatkan kumpulan ketersediaan bernama AvailablitySet03 dalam grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $AvailabilitySet.

Perintah kedua membuat objek mesin virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.
Mesin virtual termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.

Perintah ketiga membuat objek kredensial menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya dalam variabel $Credential.
Perintah meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Credential`

Perintah keempat menggunakan cmdlet **Set-AzureRmVMOperatingSystem** untuk mengonfigurasi mesin virtual yang disimpan di $VirtualMachine.

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
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzureRmVM](./Get-AzureRmVM.md) .
Buat objek mesin virtual menggunakan cmdlet [New-AzureRmVMConfig](./New-AzureRmVMConfig.md) .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSVirtualMachine
Parameter 'VM' menerima nilai tipe 'PSVirtualMachine' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzureRmAvailabilitySet](./Get-AzureRmAvailabilitySet.md)

[Set-AzureRmVMOperatingSystem](./Set-AzureRmVMOperatingSystem.md)

[AzureRmVMConfig Baru](./New-AzureRmVMConfig.md)
