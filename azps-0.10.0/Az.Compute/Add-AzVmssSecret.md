---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 656BE930-E778-40B0-8A75-BFE52DE386CE
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/add-azvmsssecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVmssSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVmssSecret.md
ms.openlocfilehash: 908810f658cdd4083bd24356eaab4e52d4dd5158
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424462"
---
# Add-AzVmssSecret

## SYNOPSIS
Menambahkan rahasia pada VMSS.

## SYNTAX

```
Add-AzVmssSecret [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-SourceVaultId] <String>]
 [[-VaultCertificate] <VaultCertificate[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVmssSecret** menambahkan rahasia pada Virtual Machine Scale Set (VMSS).
Rahasia harus disimpan di Key Vault Azure.
Untuk informasi selengkapnya tentang Key Vault, lihat [Apa itu Azure Key Vault?](https://azure.microsoft.com/en-us/documentation/articles/key-vault-whatis/) (https://azure.microsoft.com/en-us/documentation/articles/key-vault-whatis/).
Untuk informasi selengkapnya tentang cmdlet, lihat [Cmdlet Azure Key Vault atau](/powershell/module/az.keyvault) cmdlet [Set-AzKeyVaultSecret.](/powershell/module/az.keyvault/set-azkeyvaultsecret)

## EXAMPLES

### Contoh 1: Add a secret to the VMSS
```
PS C:\> $Vault = Get-AzKeyVault -VaultName "ContosoVault"
PS C:\> $CertConfig = New-AzVmssVaultCertificateConfig -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion" -CertificateStore "Certificates"
PS C:\> $VMSS = New-AzVmssConfig
PS C:\> Add-AzVmssSecret -VirtualMachineScaleSet $VMSS -SourceVaultId $Vault.ResourceId -VaultCertificate $CertConfig
```

Contoh ini menambahkan rahasia VMSS.
Perintah pertama menggunakan cmdlet Get-AzKeyVault cmdlet untuk mendapatkan rahasia vault dari vault bernama ContosoVault dan menyimpan hasilnya dalam variabel bernama $Vault.
Perintah kedua menggunakan cmdlet **New-AzVmssVaultCertificateConfig** untuk membuat konfigurasi sertifikat Key Vault menggunakan URL sertifikat yang ditentukan dari penyimpanan sertifikat yang bernama Sertifikat dan menyimpan hasilnya dalam variabel yang bernama $CertConfig.
Perintah ketiga menggunakan cmdlet **New-AzVmssConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel yang bernama $VMSS.
Perintah keempat menambahkan rahasia VMSS menggunakan rahasia vault menggunakan ID sumber daya kunci dan sertifikat vault yang disimpan di variabel $Vault $CertConfig.

## PARAMETERS

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

### -SourceVaultId
Menentukan ID sumber daya Kunci Vault yang berisi sertifikat yang dapat ditambahkan ke komputer virtual.
Nilai ini juga bertindak sebagai kunci untuk menambahkan beberapa sertifikat.
Ini berarti bahwa Anda dapat menggunakan nilai yang sama untuk parameter *SourceVaultId* ketika Anda menambahkan beberapa sertifikat dari Key Vault yang sama.

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

### -VaultCertificate
Menentukan objek **Sertifikat** Vault yang berisi URL sertifikat dan nama sertifikat.
Anda dapat menggunakan cmdlet [New-AzVmssVaultCertificateConfig](./New-AzVmssVaultCertificateConfig.md) untuk membuat objek ini.

```yaml
Type: VaultCertificate[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachinescaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet [New-AzVmssConfig](./New-AzVmssConfig.md) untuk membuat objek ini.

```yaml
Type: PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### VirtualMachinescaleSet
Parameter 'VirtualMachineScaleSet' menerima nilai tipe 'VirtualMachineScaleSet' dari saluran

## OUTPUTS

### Tidak ada
Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN

## RELATED LINKS

[New-AzVmssVaultCertificateConfig](./New-AzVmssVaultCertificateConfig.md)

[New-AzVmssConfig](./New-AzVmssConfig.md)
