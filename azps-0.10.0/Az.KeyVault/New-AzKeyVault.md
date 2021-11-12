---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 4C40DAC9-5C0B-4AFD-9BDB-D407E0B9F701
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/new-Azkeyvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/New-AzKeyVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/New-AzKeyVault.md
ms.openlocfilehash: 9d452c888fd0fe302fd57792830c5bb2bf5ee8c0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425020"
---
# New-AzKeyVault

## SYNOPSIS
Membuat kunci vault.

## SYNTAX

```
New-AzKeyVault [-VaultName] <String> [-ResourceGroupName] <String> [-Location] <String>
 [-EnabledForDeployment] [-EnabledForTemplateDeployment] [-EnabledForDiskEncryption] [-EnableSoftDelete]
 [-Sku <SkuName>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzKeyVault** membuat vault kunci dalam grup sumber daya yang ditentukan. Cmdlet ini juga memberikan izin ke pengguna yang saat ini masuk untuk menambahkan, menghapus, atau kunci daftar dan rahasia dalam kunci vault.

Catatan: Jika Anda melihat kesalahan Langganan tidak terdaftar untuk menggunakan ruang nama **'Microsoft.KeyVault'** ketika Anda mencoba membuat kunci vault baru, jalankan **Register-AzResourceProvider -ProviderNamespace "Microsoft.KeyVault"** lalu jalankan ulang perintah **New-AzKeyVault** Anda. Untuk informasi selengkapnya, lihat Register-AzResourceProvider.

## EXAMPLES

### Contoh 1: Membuat vault kunci Standar
```
PS C:\>New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US'
```

Perintah ini membuat kunci vault bernama Contoso03Vault, di kawasan Azure AS Timur. Perintah menambahkan kunci vault ke grup sumber daya bernama Group14. Karena tidak menentukan nilai untuk parameter *SKU,* perintah akan membuat kunci vault Standar.

### Contoh 2: Buat Premium key vault
```
PS C:\>New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US' -Sku 'Premium'
```

Perintah ini akan membuat kunci vault, seperti contoh sebelumnya. Namun, fungsi ini menentukan nilai Premium bagi parameter *SKU* untuk membuat Premium vault kunci.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnabledForDeployment
Memungkinkan penyedia sumber daya Microsoft.Compute untuk mendapatkan rahasia dari key vault ini saat key vault ini direferensikan dalam pembuatan sumber daya, misalnya saat membuat mesin virtual.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnabledForDiskEncryption
Memungkinkan layanan enkripsi disk Azure untuk mendapatkan kunci rahasia dan unwrap dari kunci vault ini.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnabledForTemplateDeployment
Memungkinkan Azure Resource Manager untuk mendapatkan rahasia dari key vault ini ketika key vault ini direferensikan dalam penyebaran templat.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableSoftDelete
Menentukan bahwa fungsi penghapusan sementara diaktifkan untuk vault kunci ini. Setelah penghapusan sementara diaktifkan, untuk masa tenggang, Anda dapat memulihkan key vault ini dan kontennya setelah dihapus.

Untuk informasi selengkapnya tentang fungsionalitas ini, lihat [Gambaran umum penghapusan sementara Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete). Untuk instruksi cara penggunaan, lihat [Cara menggunakan penghapusan sementara Key Vault dengan PowerShell](https://docs.microsoft.com/azure/key-vault/key-vault-soft-delete-powershell).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan kawasan Azure untuk membuat kunci vault. Gunakan perintah [Get-AzLocation](/powershell/module/az.resources/get-azlocation) untuk melihat pilihan Anda.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang ada untuk membuat kunci vault.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Menentukan SKU dari key vault instance. Untuk informasi tentang fitur yang tersedia untuk setiap SKU, lihat situs web Harga Azure Key Vault ( https://go.microsoft.com/fwlink/?linkid=512521) .

```yaml
Type: SkuName
Parameter Sets: (All)
Aliases:
Accepted values: Standard, Premium

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kunci vault untuk dibuat. Nama dapat kombinasi huruf, digit, atau tanda hubung apa pun. Nama harus diawali dan diakhiri dengan huruf atau digit. Nama harus unik secara universal.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

## CATATAN

## RELATED LINKS

[Get-AzKeyVault](./Get-AzKeyVault.md)

[Remove-AzKeyVault](./Remove-AzKeyVault.md)
