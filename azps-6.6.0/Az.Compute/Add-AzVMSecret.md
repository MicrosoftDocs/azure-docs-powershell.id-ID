---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 5008F83F-AF3E-47CF-99A3-55129E654128
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMSecret.md
ms.openlocfilehash: b6423b7dd3c4ffed5a73f3f0e1dfc2452be82b17
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136368029"
---
# Add-AzVMSecret

## SYNOPSIS
Menambahkan rahasia ke mesin virtual.

## SYNTAX

```
Add-AzVMSecret [-VM] <PSVirtualMachine> [[-SourceVaultId] <String>] [[-CertificateStore] <String>]
 [[-CertificateUrl] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Add-AzVMSecret** menambahkan rahasia ke mesin virtual.
Nilai ini memungkinkan Anda menambahkan sertifikat ke komputer virtual.
Rahasia harus disimpan di Key Vault.
Untuk informasi selengkapnya tentang Key Vault, lihat [Apa itu Azure Key Vault?](https://azure.microsoft.com/documentation/articles/key-vault-whatis/).
Untuk informasi selengkapnya tentang cmdlet, lihat [Cmdlet Azure Key Vault atau](/powershell/module/az.keyvault) cmdlet [Set-AzKeyVaultSecret.](/powershell/module/az.keyvault/set-azkeyvaultsecret)

> [!NOTE] 
> Untuk menginstal sertifikat di mesin virtual, disarankan untuk menggunakan ekstensi mesin [virtual Azure Key Vault](https://docs.microsoft.com/azure/virtual-machines/extensions/key-vault-linux) untuk Linux atau ekstensi mesin virtual Azure Key Vault untuk [Windows,](https://docs.microsoft.com/azure/virtual-machines/extensions/key-vault-windows) bukan `Add-AzVMSecret` .

## EXAMPLES

### Contoh: Add a secret to a virtual machine using Add-AzVMSecret
```powershell
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $SourceVaultId = "/subscriptions/46f8cea4-2de6-4179-8ab1-365da4211af4/resourceGroups/vault/providers/Microsoft.KeyVault/vaults/keyvault"
PS C:\> $CertificateStore01 = "My"
PS C:\> $CertificateUrl01 = "https://contosovault.vault.azure.net/secrets/514ceb769c984379a7e0230bdd703272"
PS C:\> $VirtualMachine = Add-AzVMSecret -VM $VirtualMachine -SourceVaultId $SourceVaultId -CertificateStore $CertificateStore01 -CertificateUrl $CertificateUrl01
```

Perintah pertama membuat objek mesin virtual, lalu menyimpannya dalam $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Perintah kedua membuat objek kredensial dengan menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya dalam $Credential variabel.
Perintah akan meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .
Perintah ketiga menggunakan cmdlet **Set-AzVMOperatingSystem** untuk mengonfigurasi mesin virtual yang disimpan di $VirtualMachine.
Perintah keempat menetapkan ID penyimpanan sumber ke variabel $SourceVaultId digunakan nanti.
Perintah mengasumsikan bahwa variabel $SubscriptionId memiliki nilai yang sesuai.
Perintah kelima menetapkan nilai ke variabel $CertificateStore 01 untuk digunakan nanti.
Perintah keenam menetapkan URL untuk penyimpanan sertifikat.
Perintah ketujuh menambahkan rahasia ke mesin virtual yang disimpan di $VirtualMachine.
Parameter SourceVaultId menentukan Key Vault.
Perintah menentukan nama penyimpanan sertifikat dan URL sertifikat.
Anda bisa menjalankan **Add-AzVMSecret berulang** kali untuk menambahkan rahasia untuk sertifikat lain.

## PARAMETERS

### -CertificateStore
Menentukan nama penyimpanan sertifikat pada komputer virtual yang menjalankan sistem Windows operasi.
Cmdlet ini menambahkan sertifikat ke penyimpanan yang ditentukan parameter ini.
Anda hanya dapat menentukan parameter ini untuk mesin virtual yang menjalankan Windows sistem operasi.

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

### -CertificateUrl
Menentukan URL yang menunjukkan rahasia Key Vault yang berisi sertifikat.
Sertifikatnya adalah pengodean Base64 dari objek JavaScript Object Notation (JSON) berikut, yang dikodekan dalam UTF-8: { "data": " \<Base64-encoded-file\> ", "dataType": " \<file-format\> ", "password": " } Saat ini, tipedata hanya menerima \<pfx-file-password\> file .pfx.

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

### -SourceVaultId
Menentukan ID sumber daya Kunci Vault yang berisi sertifikat yang dapat ditambahkan ke komputer virtual.
Nilai ini juga bertindak sebagai kunci untuk menambahkan beberapa sertifikat.
Artinya, Anda dapat menggunakan nilai yang sama untuk *SourceVaultId* ketika menambahkan beberapa sertifikat dari Key Vault yang sama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual yang telah dimodifikasi cmdlet ini.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzVM.](./Get-AzVM.md)
Anda dapat menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) untuk membuat objek mesin virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-azvm](./Get-AzVM.md)

[New-azvmConfig](./New-AzVMConfig.md)

[Set-AzvMOperatingSystem](./Set-AzVMOperatingSystem.md)
