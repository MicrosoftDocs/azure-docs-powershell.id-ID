---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 4C40DAC9-5C0B-4AFD-9BDB-D407E0B9F701
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/new-Azkeyvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/New-AzKeyVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/New-AzKeyVault.md
ms.openlocfilehash: 9d452c888fd0fe302fd57792830c5bb2bf5ee8c0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142057745"
---
# New-AzKeyVault

## SYNOPSIS
Membuat kubah kunci.

## SYNTAX

```
New-AzKeyVault [-VaultName] <String> [-ResourceGroupName] <String> [-Location] <String>
 [-EnabledForDeployment] [-EnabledForTemplateDeployment] [-EnabledForDiskEncryption] [-EnableSoftDelete]
 [-Sku <SkuName>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzKeyVault** membuat kubah kunci dalam grup sumber daya yang ditentukan. Cmdlet ini juga memberikan izin kepada pengguna yang saat ini masuk untuk menambahkan, menghapus, atau mencantumkan kunci dan rahasia dalam kubah kunci.

Catatan: Jika Anda melihat kesalahan **Langganan tidak terdaftar untuk menggunakan ruang nama 'Microsoft.KeyVault'** saat Anda mencoba membuat kubah kunci baru, **jalankan Register-AzResourceProvider -ProviderNamespace "Microsoft.KeyVault"** lalu jalankan kembali perintah **New-AzKeyVault** Anda. Untuk informasi selengkapnya, lihat Register-AzResourceProvider.

## EXAMPLES

### Contoh 1: Membuat kubah kunci Standar
```
PS C:\>New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US'
```

Perintah ini membuat kubah kunci bernama Contoso03Vault, di kawasan Azure AS Timur. Perintah menambahkan kubah kunci ke grup sumber daya bernama Group14. Karena perintah tidak menentukan nilai untuk parameter *SKU* , perintah akan membuat kubah kunci Standar.

### Contoh 2: Membuat kubah kunci Premium
```
PS C:\>New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US' -Sku 'Premium'
```

Perintah ini membuat kubah kunci, sama seperti contoh sebelumnya. Namun, parameter ini menentukan nilai Premium untuk parameter *SKU* untuk membuat kubah kunci Premium.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Memungkinkan penyedia sumber daya Microsoft.Compute untuk mengambil rahasia dari kubah kunci ini ketika kubah kunci ini dirujuk dalam pembuatan sumber daya, misalnya saat membuat mesin virtual.

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
Memungkinkan layanan enkripsi disk Azure untuk mendapatkan rahasia dan menghapus kunci dari kubah kunci ini.

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
Memungkinkan Azure Resource Manager untuk mendapatkan rahasia dari kubah kunci ini ketika kubah kunci ini dirujuk dalam penyebaran templat.

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
Menentukan bahwa fungsionalitas penghapusan-lunak diaktifkan untuk kubah kunci ini. Saat penghapusan lunak diaktifkan, untuk masa tenggang, Anda dapat memulihkan kubah kunci ini dan kontennya setelah dihapus.

Untuk informasi selengkapnya tentang fungsionalitas ini, lihat [Azure Key Vault gambaran umum penghapusan lembut](https://docs.microsoft.com/azure/key-vault/key-vault-ovw-soft-delete). Untuk instruksi cara penggunaan, lihat [Cara menggunakan Key Vault penghapusan lembut dengan PowerShell](https://docs.microsoft.com/azure/key-vault/key-vault-soft-delete-powershell).

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
Menentukan kawasan Azure untuk membuat kubah kunci. Gunakan perintah [Get-AzLocation](/powershell/module/az.resources/get-azlocation) untuk melihat pilihan Anda.

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
Menentukan nama grup sumber daya yang sudah ada untuk membuat kubah kunci.

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
Menentukan SKU instans kubah kunci. Untuk informasi tentang fitur mana yang tersedia untuk setiap SKU, lihat situs web Azure Key Vault Harga (https://go.microsoft.com/fwlink/?linkid=512521).

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
Menentukan nama kubah kunci untuk dibuat. Nama dapat berupa kombinasi huruf, digit, atau tanda hubung apa pun. Nama harus dimulai dan diakhiri dengan huruf atau digit. Nama harus unik secara universal.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

## CATATAN

## RELATED LINKS

[Get-AzKeyVault](./Get-AzKeyVault.md)

[Hapus-AzKeyVault](./Remove-AzKeyVault.md)
