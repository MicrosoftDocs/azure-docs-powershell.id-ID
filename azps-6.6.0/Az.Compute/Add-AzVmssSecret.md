---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 656BE930-E778-40B0-8A75-BFE52DE386CE
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmsssecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssSecret.md
ms.openlocfilehash: a1a868a33b954f58a86190d51b7aa058d8628a79
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141871538"
---
# Add-AzVmssSecret

## SYNOPSIS
Menambahkan rahasia ke VMSS.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvmsssecret) untuk informasi terbaru.

## SYNTAX

```
Add-AzVmssSecret [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-SourceVaultId] <String>]
 [[-VaultCertificate] <VaultCertificate[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVmssSecret** menambahkan rahasia ke Kumpulan Skala Mesin Virtual (VMSS).
Rahasia harus disimpan di Key Vault Azure.
Untuk informasi selengkapnya terkait Key Vault, lihat [Apa itu Azure Key Vault?](https://docs.microsoft.com/azure/key-vault/general/basic-concepts) (https://docs.microsoft.com/azure/key-vault/general/basic-concepts).
Untuk informasi selengkapnya tentang cmdlet, lihat [Cmdlet Azure Key Vault](/powershell/module/az.keyvault) atau cmdlet [Set-AzKeyVaultSecret](/powershell/module/az.keyvault/set-azkeyvaultsecret).

## EXAMPLES

### Contoh 1: Menambahkan rahasia ke VMSS menggunakan azure Key Vault ekstensi mesin virtual

```powershell
# Build settings
PS C:\> $settings = @{
    secretsManagementSettings = @{
        pollingIntervalInS       = "<pollingInterval>"
        certificateStoreName     = "<certStoreName>"
        certificateStoreLocation = "<certStoreLoc>"
        observedCertificates     = @("<observedCert1>", "<observedCert2>")
    } 
} | ConvertTo-Json
PS C:\> $extName = "KeyVaultForLinux"
PS C:\> $extPublisher = "Microsoft.Azure.KeyVault"
PS C:\> $extType = "KeyVaultForLinux"
# Add Extension to VMSS
PS C:\> $vmss = Get-AzVmss -ResourceGroupName <ResourceGroupName> -VMScaleSetName <VmssName>
PS C:\> Add-AzVmssExtension -VirtualMachineScaleSet $vmss  -Name $extName -Publisher $extPublisher -Type $extType -TypeHandlerVersion "2.0" -Setting $settings
# Start the deployment
PS C:\> Update-AzVmss -ResourceGroupName <ResourceGroupName> -VMScaleSetName <VmssName> -VirtualMachineScaleSet $vmss
```

Untuk menginstal sertifikat di mesin virtual, disarankan untuk menggunakan [ekstensi mesin virtual Azure Key Vault untuk Linux](https://docs.microsoft.com/azure/virtual-machines/extensions/key-vault-linux) atau [azure Key Vault ekstensi mesin virtual untuk Windows](https://docs.microsoft.com/azure/virtual-machines/extensions/key-vault-windows). 

### Contoh 2: Menambahkan rahasia ke VMSS menggunakan Add-AzVmssSecret
```powershell
PS C:\> $Vault = Get-AzKeyVault -VaultName "ContosoVault"
PS C:\> $CertConfig = New-AzVmssVaultCertificateConfig -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion" -CertificateStore "Certificates"
PS C:\> $VMSS = New-AzVmssConfig
PS C:\> Add-AzVmssSecret -VirtualMachineScaleSet $VMSS -SourceVaultId $Vault.ResourceId -VaultCertificate $CertConfig
```

Contoh ini menambahkan rahasia ke VMSS.
Perintah pertama menggunakan cmdlet Get-AzKeyVault untuk mendapatkan rahasia kubah dari kubah bernama ContosoVault dan menyimpan hasilnya dalam variabel bernama $Vault.
Perintah kedua menggunakan cmdlet **New-AzVmsVaultCertificateConfig** untuk membuat konfigurasi sertifikat Key Vault menggunakan URL sertifikat tertentu dari penyimpanan sertifikat bernama Sertifikat dan menyimpan hasil dalam variabel bernama $CertConfig.
Perintah ketiga menggunakan cmdlet **New-AzVmsConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel bernama $VMSS.
Perintah keempat menambahkan rahasia ke VMSS menggunakan rahasia kubah menggunakan ID sumber daya utama dan sertifikat kubah yang disimpan dalam variabel $Vault dan $CertConfig.

## PARAMETERS

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

### -SourceVaultId
Menentukan ID sumber daya dari Key Vault yang berisi sertifikat yang bisa Anda tambahkan ke mesin virtual.
Nilai ini juga bertindak sebagai kunci untuk menambahkan beberapa sertifikat.
Artinya, Anda dapat menggunakan nilai yang sama untuk parameter *SourceVaultId* ketika menambahkan beberapa sertifikat dari Key Vault yang sama.

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

### -VaultCertificate
Menentukan objek **Sertifikat** Vault yang berisi URL sertifikat dan nama sertifikat.
Anda dapat menggunakan cmdlet [New-AzVmssVaultCertificateConfig](./New-AzVmssVaultCertificateConfig.md) untuk membuat objek ini.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VaultCertificate[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet [New-AzVmsConfig](./New-AzVmssConfig.md) untuk membuat objek ini.

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

### Microsoft.Azure.Management.Compute.Models.VaultCertificate[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS

[New-AzVmssVaultCertificateConfig](./New-AzVmssVaultCertificateConfig.md)

[New-AzVmssConfig](./New-AzVmssConfig.md)
