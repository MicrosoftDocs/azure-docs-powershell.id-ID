---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 5008F83F-AF3E-47CF-99A3-55129E654128
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/add-azvmsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVMSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVMSecret.md
ms.openlocfilehash: f17da705ed65484e789a803308bcaddb60e409f3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142847728"
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
Nilai ini memungkinkan Anda menambahkan sertifikat ke mesin virtual.
Rahasia itu harus disimpan dalam Key Vault.
Untuk informasi selengkapnya tentang Key Vault, lihat [Apa itu Azure Key Vault?](https://azure.microsoft.com/en-us/documentation/articles/key-vault-whatis/).
Untuk informasi selengkapnya tentang cmdlet, lihat [Cmdlet Azure Key Vault](/powershell/module/az.keyvault) atau cmdlet [Set-AzKeyVaultSecret](/powershell/module/az.keyvault/set-azkeyvaultsecret).

## EXAMPLES

### Contoh 1: Menambahkan rahasia ke mesin virtual
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
PS C:\> $Credential = Get-Credential
PS C:\> $VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine  -Windows -ComputerName "Contoso26" -Credential $Credential
PS C:\> $SourceVaultId = "/subscriptions/46f8cea4-2de6-4179-8ab1-365da4211af4/resourceGroups/vault/providers/Microsoft.KeyVault/vaults/keyvault"
PS C:\> $CertificateStore01 = "My"
PS C:\> $CertificateUrl01 = "https://contosovault.vault.azure.net/secrets/514ceb769c984379a7e0230bdd703272"
PS C:\> $VirtualMachine = Add-AzVMSecret -VM $VirtualMachine -SourceVaultId $SourceVaultId -CertificateStore $CertificateStore01 -CertificateUrl $CertificateUrl01
```

Perintah pertama membuat objek mesin virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.

Perintah kedua membuat objek kredensial dengan menggunakan cmdlet Get-Credential, lalu menyimpan hasilnya dalam variabel $Credential.
Perintah meminta nama pengguna dan kata sandi Anda.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Credential`

Perintah ketiga menggunakan cmdlet **Set-AzVMOperatingSystem** untuk mengonfigurasi mesin virtual yang disimpan di $VirtualMachine.

Perintah keempat menetapkan ID kubah sumber ke variabel $SourceVaultId untuk digunakan nanti.
Perintah mengasumsikan bahwa variabel $SubscriptionId memiliki nilai yang sesuai.

Perintah kelima menetapkan nilai ke variabel $CertificateStore 01 untuk digunakan nanti.

Perintah keenam menetapkan URL untuk penyimpanan sertifikat.

Perintah ketujuh menambahkan rahasia ke mesin virtual yang disimpan di $VirtualMachine.
Parameter SourceVaultId menentukan Key Vault.
Perintah menentukan nama penyimpanan sertifikat dan URL sertifikat.
Anda dapat menjalankan **Add-AzVMSecret** berulang kali untuk menambahkan rahasia untuk sertifikat lain.

## PARAMETERS

### -CertificateStore
Menentukan nama penyimpanan sertifikat pada mesin virtual yang menjalankan sistem operasi Windows.
Cmdlet ini menambahkan sertifikat ke bursa yang ditentukan parameter ini.
Anda hanya dapat menentukan parameter ini untuk mesin virtual yang menjalankan sistem operasi Windows.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateUrl
Menentukan URL yang mengarah ke rahasia Key Vault yang berisi sertifikat.

Sertifikat adalah pengodean Base64 dari objek JavaScript Object Notation (JSON) berikut, yang dikodekan dalam UTF-8:

{ "data": "\<Base64-encoded-file\>", "dataType": "\<file-format\>", "password": "\<pfx-file-password\>" }


Saat ini, dataType hanya menerima file .pfx.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -SourceVaultId
Menentukan ID sumber daya dari Key Vault yang berisi sertifikat yang bisa Anda tambahkan ke mesin virtual.
Nilai ini juga bertindak sebagai kunci untuk menambahkan beberapa sertifikat.
Artinya, Anda dapat menggunakan nilai yang sama untuk *SourceVaultId* ketika menambahkan beberapa sertifikat dari Key Vault yang sama.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual yang diubah cmdlet ini.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Anda dapat menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) untuk membuat objek mesin virtual.

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

[Get-AzVM](./Get-AzVM.md)

[New-AzVMConfig](./New-AzVMConfig.md)

[Set-AzVMOperatingSystem](./Set-AzVMOperatingSystem.md)
